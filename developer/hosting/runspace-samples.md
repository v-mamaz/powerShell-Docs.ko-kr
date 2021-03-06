---
title: Runspace 샘플 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c92a6d3d-8d34-4a76-bdc3-dea923d9858e
caps.latest.revision: 17
ms.openlocfilehash: e24d40746da91f60aaf2af655ddcadc88ab6a4db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857339"
---
# <a name="runspace-samples"></a>Runspace 샘플

이 섹션에서는 다양 한 runspace 사용 하 여 동기적 및 비동기적으로 명령을 실행 하는 방법을 보여 주는 샘플 코드를 포함 합니다. 콘솔 응용 프로그램을 만들고 다음 호스트 응용 프로그램에이 섹션의 항목에서 코드를 복사 하려면 Microsoft Visual Studio를 사용할 수 있습니다.

## <a name="in-this-section"></a>이 섹션의 내용

> [!NOTE]
> 사용자 지정 호스트 인터페이스를 만드는 호스트 응용 프로그램의 샘플을 보려면 [사용자 지정 호스트 샘플](./custom-host-samples.md)합니다.

 [Runspace01 샘플](./runspace01-sample.md) 사용 하는 방법을이 보여 줍니다 합니다 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 실행 하는 클래스를 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet 동기적으로 고 해당 출력을 콘솔에 표시 창입니다.

 [Runspace02 샘플](./runspace02-sample.md) 이 샘플에 사용 하는 방법을 보여 줍니다 합니다 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 실행 하는 클래스를 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) 하 고 [Sort-object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlet 동기적으로 합니다. 이러한 명령의 결과 사용 하 여 표시 되는 [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) 제어 합니다.

 [Runspace03 샘플](./runspace03-sample.md) 사용 하는 방법을이 보여 줍니다 합니다 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 동기적으로 스크립트를 실행 하는 클래스 및 종료 되지 않는 오류를 처리 하는 방법입니다. 스크립트는 프로세스 이름 목록을 받은 다음 해당 프로세스를 검색합니다. 스크립트를 실행할 때 생성된 종료되지 않는 오류를 포함하여 스크립트의 결과가 콘솔 창에 표시됩니다.

 [Runspace04 샘플](./runspace04-sample.md) 사용 하는 방법을이 보여 줍니다 합니다 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 명령을 실행 하는 클래스 및 명령을 실행 하는 경우 throw 되는 종료 오류를 catch 하는 방법입니다. 두 개의 명령이 실행되는데, 마지막 명령은 유효하지 않은 매개 변수 인수를 전달받습니다. 결과적으로 개체가 반환 되지 및 종료 오류가 발생 합니다.

 [샘플 Runspace05](./runspace05-sample.md) 스냅인을 추가 하는 방법을이 보여 줍니다는 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) runspace를 열 때 스냅인의 cmdlet을 사용할 수 있도록 개체입니다. 스냅인 Get-proc cmdlet을 제공 합니다 (정의한 합니다 [GetProcessSample01 샘플](../cmdlet/getprocesssample01-sample.md)) 사용 하 여 동기적으로 실행 되는 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 개체입니다.

 [Runspace06 샘플](./runspace06-sample.md) 모듈을 추가 하는 방법을이 보여 줍니다는 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) runspace를 열 때 모듈이 로드 되도록 개체입니다. 모듈 제공 Get-proc cmdlet (정의한 합니다 [GetProcessSample02 샘플](../cmdlet/getprocesssample02-sample.md)) 사용 하 여 동기적으로 실행 되는 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 개체입니다.

 [샘플 Runspace07](./runspace07-sample.md) runspace를 만들고 해당 runspace를 사용 하 여 두 개의 cmdlet을 사용 하 여 동기적으로 실행 하는 방법을이 보여 줍니다는 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 개체입니다.

 [샘플 Runspace08](./runspace08-sample.md) 이 샘플의 파이프라인에 명령 및 인수를 추가 하는 방법을 보여 줍니다는 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 개체와 동기적으로 명령을 실행 하는 방법입니다.

 [샘플 Runspace09](./runspace09-sample.md) 이 샘플의 파이프라인에 스크립트를 추가 하는 방법을 보여 줍니다는 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 개체 및 스크립트를 비동기적으로 실행 하는 방법입니다. 이벤트는 스크립트의 출력을 처리하는 데 사용됩니다.

 [Runspace10 샘플](./runspace10-sample.md) 이 샘플에서는 기본 초기 세션 상태를 만드는 방법을 보여 줍니다. cmdlet을 추가 하는 방법을 합니다 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)를 사용 하는 runspace를 만드는 방법은 사용 하 여 명령을 실행 하는 방법과 초기 세션 상태를 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) 개체입니다.

 [Runspace11 샘플](./runspace11-sample.md) 사용 하는 방법을 보여 줍니다 합니다 [System.Management.Automation.Proxycommand](/dotnet/api/System.Management.Automation.ProxyCommand) 기존 cmdlet을 호출 하지만 사용 가능한 매개 변수 집합을 제한 하는 프록시 명령을 만드는 클래스입니다. 프록시 명령은 제한된 runspace를 만드는 데 사용되는 초기 세션 상태에 추가됩니다. 따라서 사용자가 프록시 명령을 통해서만 cmdlet의 기능에 액세스할 수 있습니다.

## <a name="see-also"></a>참고 항목
