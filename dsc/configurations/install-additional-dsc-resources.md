---
ms.date: 12/12/2018
keywords: dsc, powershell, 리소스, 갤러리, 설치
title: 추가 DSC 리소스 설치
ms.openlocfilehash: ecaf176230ccd934b57b1c27d72ff83e6ba906e9
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402908"
---
# <a name="install-additional-dsc-resources"></a>추가 DSC 리소스 설치

PowerShell Desired State Configuration (DSC)에 대 한 몇 가지 기본 제공 리소스를 포함합니다. 합니다 **PSDesiredStateConfiguration** 모듈 PowerShell의 특정 인스턴스에서 사용 가능한 OOB DSC 리소스를 모두 포함 되어 있습니다.

PowerShell 4.0 및 리소스의 기능에 대 한 설명을 포함 된 OOB 리소스의 목록입니다.

> [!NOTE]
> 각 버전의 PowerShell 사용 하 여 OOB 리소스 수가 늘어날수록는 불완전 한 목록입니다.

|리소스  |설명  |
|---------|---------|
|**File**|파일 및 디렉터리의 상태를 제어합니다. 파일을 복사를 **원본** 에 **대상** 업데이트 하 고 때를 **원본** 날짜, 체크섬을 및 해시를 비교 하 여 변경 내용을.|
|**Archive**|지정된 된 위치 및 보관 압축을 풉니다. 지정 된 보관의 유효성을 검사 **체크섬**합니다.|
|**Environment**|환경 변수를 관리 합니다.|
|**그룹**|로컬 그룹을 관리 하 고 그룹 멤버 자격을 제어 합니다.|
|**Log**|메시지를 기록 합니다 `Microsoft-Windows-Desired State Configuration/Analytic` 이벤트 로그입니다.|
|**패키지**|설치 하거나 사용 하 여 패키지를 제거 **인수**, **LogPath**를 **ReturnCode**, 기타 설정 합니다.|
|**Registry**|레지스트리 키와 값을 관리합니다.|
|**Script**|사용 하면 디자인을 사용자 고유의 [get-테스트-집합](../resources/get-test-set.md) 스크립트 블록입니다.|
|**Service**|Windows 서비스를 구성합니다.|
|**User** |로컬 사용자 및 특성을 관리합니다.|
|**WindowsFeature**|역할 및 기능을 관리합니다.|
|**WindowsProcess**|Windows 프로세스를 구성합니다.|

OOB 리소스 일반적인 작업을 위한 좋은 출발점을 허용 합니다. OOB 리소스 요구를 충족 하지 않으면 작성할 수 있습니다 고유한 [사용자 지정 리소스](../resources/authoringResource.md)합니다. 문제를 해결 하기 위해 사용자 지정 리소스를 작성 하기 전에 다양 한 Microsoft와 PowerShell 커뮤니티에서 이미 만들어져 있는 DSC 리소스를 통해 같아야 합니다.

둘 다에서 DSC 리소스를 찾을 수 있습니다 합니다 [PowerShell 갤러리](https://www.powershellgallery.com/) 하 고 [GitHub](https://github.com/)합니다. DSC 리소스를 사용 하 여 PowerShell 콘솔에서 직접 설치할 수도 있습니다 [PowerShellGet](/powershell/module/powershellget/)합니다.

## <a name="installing-powershellget"></a>PowerShellGet 설치

이미 있는 경우 결정할 **PowerShell** 가져오기 또는 설치 도움말을 보려면 다음 가이드를 참조 하십시오. [PowerShellGet 설치](/powershell/gallery/installing-psget)

## <a name="finding-dsc-resources-using-powershellget"></a>PowerShellGet을 사용 하 여 DSC 리소스 찾기

한 번 **PowerShellGet** 되어 시스템에서 찾을 고에서 호스팅되는 DSC 리소스를 설치할 수 있습니다 합니다 [PowerShell 갤러리](https://www.powershellgallery.com/)합니다.

먼저 사용 하 여 합니다 [Find-dscresource](/powershell/module/powershellget/find-dscresource) cmdlet DSC 리소스를 찾을 수 있습니다. 실행할 때 `Find-DSCResource` 처음으로 "NuGet 공급자"를 설치 하려면 다음과 같은 메시지가 표시 됩니다.

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The
NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider
 by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to
install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

키를 눌러 'y' 후 "NuGet" 공급자가 설치 되어, PowerShell 갤러리에서 설치할 수 있는 DSC 리소스의 목록을 표시 합니다.

> [!NOTE]
> 목록에는 매우 큰 이기 때문에 표시 되지 않습니다.

지정할 수도 있습니다는 `-Name` 와일드 카드를 사용 하 여 매개 변수 또는 `-Filter` 검색 범위를 좁힐에 와일드 카드 없이 매개 변수입니다. 이 예제에서는 와일드 카드를 사용 하 여 "시간대" DSC 리소스를 찾으려고 시도 합니다.

> [!IMPORTANT]
> 현재는의 버그를 `Find-DSCResource` 둘 다에 와일드 카드 사용을 방지 하는 cmdlet의 `-Name` 및 `-Filter` 매개 변수. 아래 두 번째 예제에서는 사용 하 여 해결 방법을 보여 줍니다. `Where-Object`합니다.

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

사용할 수도 있습니다 `Where-Object` 보다 세분화 된 필터링 된 DSC 리소스를 찾을 수 있습니다. 이 방법은 기본 제공 매개 변수 필터링을 사용 하 여 보다 낮아집니다.

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

필터링에 대 한 자세한 내용은 참조 하세요. [Where-object](/powershell/module/microsoft.powershell.core/where-object)합니다.

## <a name="installing-dsc-resources-using-powershellget"></a>PowerShellGet을 사용 하 여 DSC 리소스를 설치 합니다.

DSC 리소스를 설치 하려면 사용 합니다 [Install-module](/powershell/module/PowershellGet/Install-Module) cmdlet을 아래에 표시 된 모듈의 이름을 지정 하 **모듈** 검색 결과의 이름.

"시간대" 리소스 이므로 즉 모듈이 예제 설치 "ComputerManagementDSC" 모듈에 있습니다.

> [!NOTE]
> PowerShell 갤러리를 신뢰할 수 있는 경우 확인을 묻는 아래 경고를 표시 하 고 설치에서 후속 프롬프트를 방지 하는 방법 하도록 지시 합니다.

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

모듈 설치를 계속 하려면 ' y'를 누릅니다. 설치 후 확인할 수 있습니다 새 리소스를 사용 하 여이 설치 되어 있는지 [Get-dscresource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)합니다.

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

지정 하 여 새로 설치 된 모듈의 다른 리소스를 볼 수도 있습니다는 `-ModuleName` 매개 변수입니다.

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a>참고 항목

- [리소스란?](../resources/resources.md)
