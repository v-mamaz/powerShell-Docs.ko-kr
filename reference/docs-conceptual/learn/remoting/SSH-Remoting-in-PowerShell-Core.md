---
title: SSH를 통한 PowerShell 원격
description: SSH를 사용하여 PowerShell Core에서 원격 작업
ms.date: 08/14/2018
ms.openlocfilehash: 1d7bcb69c7e784bf745cb5c2633106ea53f6226a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "58056535"
---
# <a name="powershell-remoting-over-ssh"></a>SSH를 통한 PowerShell 원격

## <a name="overview"></a>개요

PowerShell 원격 기능은 일반적으로 연결 협상 및 데이터 전송에 WinRM을 사용합니다. 이제 SSH를 Linux 및 Windows 플랫폼에서 사용할 수 있으며 진정한 다중 플랫폼 PowerShell 원격 기능이 지원됩니다.

WinRM은 PowerShell 원격 세션을 위한 강력한 호스팅 모델을 제공합니다. SSH 기반 원격 기능은 원격 엔드포인트 구성 및 JEA(Just Enough Administration)를 지원하지 않습니다.

SSH 원격 기능을 사용하면 Windows 및 Linux 컴퓨터 간에 기본적인 PowerShell 세션 원격 작업을 수행할 수 있습니다. SSH 원격 기능은 대상 컴퓨터에 SSH 하위 시스템으로 PowerShell 호스트 프로세스를 만듭니다.
앞으로는 엔드포인트 구성 및 JEA를 지원하기 위해 WinRM과 유사한 일반 호스팅 모델을 구현할 예정입니다.

`New-PSSession`, `Enter-PSSession` 및 `Invoke-Command` cmdlet에는 이제 이 새로운 원격 연결을 지원하기 위한 새로운 매개 변수가 설정됩니다.

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

원격 세션을 만들려면 `HostName` 매개 변수를 사용하여 대상 컴퓨터를 지정하고 `UserName`을 사용하여 사용자 이름을 제공합니다. cmdlet을 대화형으로 실행하면 암호를 묻는 메시지가 나타납니다. `KeyFilePath` 매개 변수와 함께 개인 키 파일을 사용하여 SSH 키 인증을 사용할 수도 있습니다.

## <a name="general-setup-information"></a>일반적인 설치 정보

SSH는 모든 컴퓨터에 설치해야 합니다. 컴퓨터에서 들어오고 나가는 원격 작업을 수행할 수 있도록 SSH 클라이언트(`ssh.exe`) 및 서버(`sshd.exe`)를 설치합니다. Windows용 OpenSSH는 이제 Windows 10 빌드 1809 및 Windows Server 2019에서 제공됩니다. 자세한 내용은 [Windows용 OpenSSH](/windows-server/administration/openssh/openssh_overview)를 참조하세요. Linux의 경우 플랫폼에 적합한 SSH(sshd 서버 포함)를 설치합니다. 또한 SSH 원격 기능을 가져오려면 GitHub에서 PowerShell Core를 설치해야 합니다. SSH 서버는 원격 컴퓨터에 PowerShell 프로세스를 호스트하기 위해 SSH 하위 시스템을 만들도록 구성되어야 합니다. 또한 암호 또는 키 기반 인증도 구성해야 합니다.

## <a name="set-up-on-windows-machine"></a>Windows 컴퓨터에 설치

1. 최신 버전의 [PowerShell Core for Windows](../../install/installing-powershell-core-on-windows.md#msi) 설치

   - `New-PSSession`의 매개 변수 집합을 확인하면 SSH 원격 기능이 지원되는지 알 수 있습니다.

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. 최신 Win32 OpenSSH를 설치합니다. 설치 지침은 [OpenSSH 설치](/windows-server/administration/openssh/openssh_install_firstuse)를 참조하세요.
3. `$env:ProgramData\ssh`에 있는 `sshd_config` 파일을 편집합니다.

   - 암호 인증이 활성화되었는지 확인합니다.

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > 하위 시스템 실행 파일 경로의 작업에서 공백을 방지하는 Windows용 OpenSSH에 버그가 있습니다. 자세한 내용은 [이 GitHub 문제](https://github.com/PowerShell/Win32-OpenSSH/issues/784)를 참조하세요.

     한 가지 해결 방법은 공백이 없는 PowerShell 설치 디렉터리에 symlink를 만드는 것입니다.

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6"
     ```

     그런 다음, 하위 시스템에 입력합니다.

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - 필요에 따라 키 인증을 활성화합니다.

     ```
     PubkeyAuthentication yes
     ```

4. sshd 서비스를 다시 시작합니다.

   ```powershell
   Restart-Service sshd
   ```

5. Path 환경 변수에 OpenSSH가 설치된 경로를 추가합니다. 정의합니다(예: `C:\Program Files\OpenSSH\`). 이 항목을 입력하면 ssh.exe를 찾을 수 있습니다.

## <a name="set-up-on-linux-ubuntu-1404-machine"></a>Linux(Ubuntu 14.04) 컴퓨터에 설치

1. GitHub에서 최신 [Linux용 PowerShell Core](../../install/installing-powershell-core-on-linux.md#ubuntu-1404) 빌드를 설치합니다.
2. 필요에 따라 [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)를 설치합니다.

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. /etc/ssh 위치에서 sshd_config 파일을 편집합니다.

   - 암호 인증이 활성화되었는지 확인합니다.

   ```
   PasswordAuthentication yes
   ```

   - PowerShell 하위 시스템 항목을 추가합니다.

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - 필요에 따라 키 인증을 활성화합니다.

   ```
   PubkeyAuthentication yes
   ```

4. sshd 서비스를 다시 시작합니다.

   ```bash
   sudo service sshd restart
   ```

## <a name="set-up-on-macos-machine"></a>MacOS 컴퓨터에 설치

1. 최신 [MacOS용 PowerShell Core](../../install/installing-powershell-core-on-macos.md) 빌드를 설치합니다.

   - 다음 단계를 수행하여 SSH 원격 기능이 활성화되어 있는지 확인합니다.
     - `System Preferences`를 엽니다.
     - `Sharing`을 클릭합니다.
     - `Remote Login`을 확인합니다(`Remote Login: On`이어야 함).
     - 적절한 사용자에게 액세스를 허용합니다.

2. `/private/etc/ssh/sshd_config` 위치에서 `sshd_config` 파일을 편집합니다.

   - 선호하는 편집기를 사용합니다. 또는

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - 암호 인증이 활성화되었는지 확인합니다.

     ```
     PasswordAuthentication yes
     ```

   - PowerShell 하위 시스템 항목을 추가합니다.

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - 필요에 따라 키 인증을 활성화합니다.

     ```
     PubkeyAuthentication yes
     ```

3. sshd 서비스를 다시 시작합니다.

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a>인증

SSH를 통한 PowerShell 원격 기능은 SSH 클라이언트 및 SSH 서비스 간에 인증 교환을 필요로 하며 어떤 인증 체계도 구현하지 않습니다.
즉, 다단계 인증을 비롯한 모든 구성된 인증 체계는 SSH에서 처리하며 PowerShell과는 독립적입니다.
예를 들어 보안 강화를 위해 일회용 암호뿐만 아니라 공개 키 인증이 필요하도록 SSH 서비스를 구성할 수 있습니다.
다단계 인증의 구성은 이 설명서의 범위를 벗어납니다.
PowerShell 원격 기능에서 다단계 인증을 사용하기 전에 올바르게 다단계 인증을 구성하고 PowerShell 외부에서 작동하는지 유효성 검사를 하는 방법은 SSH에 대한 설명서를 참조하세요.

## <a name="powershell-remoting-example"></a>PowerShell 원격 기능 예제

원격 기능을 테스트하는 가장 쉬운 방법은 단일 컴퓨터에서 사용해 보는 것입니다. 이 예제에서는 동일한 Linux 컴퓨터에 원격 세션을 다시 만듭니다. SSH에서 호스트 컴퓨터를 확인하도록 요구하고 암호를 묻는 메시지를 표시하도록 대화형으로 PowerShell cmdlet을 사용합니다. Windows 컴퓨터에서도 동일한 작업을 수행하여 원격 기능이 작동하는지 확인할 수 있습니다. 그런 다음, 호스트 이름을 변경하여 시스템 간을 원격으로 이동합니다.

```powershell
#
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~14.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName                    PSComputerName
-------  ------    -----      -----     ------     --  -- -----------                    --------------
      0       0        0         19       3.23  10635 635 powershell                     UbuntuVM1
      0       0        0         21       4.92  11033 017 powershell                     UbuntuVM1
      0       0        0         20       3.07  11076 076 powershell                     UbuntuVM1
```

```powershell
#
# Linux to Windows
#
Enter-PSSession -HostName WinVM1 -UserName PTestName
```

```output
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```output
[WinVM2]: PS C:\Users\PSRemoteUser\Documents> $PSVersionTable

Name                           Value
----                           -----
PSEdition                      Core
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
SerializationVersion           1.1.0.1
BuildVersion                   3.0.0.0
CLRVersion
PSVersion                      6.0.0-alpha
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
GitCommitId                    v6.0.0-alpha.17


[WinVM2]: PS C:\Users\PSRemoteUser\Documents>
```

### <a name="known-issues"></a>알려진 문제

sudo 명령은 Linux 컴퓨터에 대한 원격 세션에서 작동하지 않습니다.

## <a name="see-also"></a>참고 항목

[Windows용 PowerShell Core](../../install/installing-powershell-core-on-windows.md#msi)

[Linux용 PowerShell Core](../../install/installing-powershell-core-on-linux.md#ubuntu-1404)

[MacOS용 PowerShell Core](../../install/installing-powershell-core-on-macos.md)

[Windows용 OpenSSH](/windows-server/administration/openssh/openssh_overview)

[Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
