---
title: Cmdlet 출력 유형의 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], output
ms.assetid: 547e6695-e936-4cac-a90b-417d0dab393d
caps.latest.revision: 12
ms.openlocfilehash: 3efa98c7aa22fdaee8042bae99282aea0618ef5f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853929"
---
# <a name="types-of-cmdlet-output"></a>Cmdlet 출력의 형식

PowerShell은 cmdlet 출력을 생성 하 여 호출할 수 있는 여러 메서드를 제공 합니다. 이러한 메서드는 성공 데이터 스트림 또는 오류 데이터 스트림 등의 특정 데이터 스트림에 해당 출력을 작성 하는 특정 작업을 사용 합니다. 이 문서에서는 출력을 생성 하는 메서드의 형식을 설명 합니다.

## <a name="types-of-output"></a>출력 형식

### <a name="success-output"></a>성공 시 출력

Cmdlet은 파이프라인의 다음 명령에서 처리할 수 있는 개체를 반환 하 여 성공 여부를 보고할 수 있습니다. Cmdlet은 해당 작업을 성공적으로 수행 된 후 cmdlet을 호출 합니다 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 메서드. 대신이 메서드를 호출 하는 것을 권장 합니다 [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine) 또는 [System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) 메서드.

제공할 수 있습니다는 **PassThru** 일반적으로 개체를 반환 하지 않는 cmdlet에 대 한 매개 변수를 전환 합니다.
경우는 **PassThru** 스위치 매개 변수를 지정 하 여 명령줄에서 cmdlet 개체를 반환 하도록 요청 합니다. 있는 cmdlet의 예는 **PassThru** 매개 변수를 참조 하십시오 [Add-history](/powershell/module/Microsoft.PowerShell.Core/Add-History)합니다.

### <a name="error-output"></a>오류 출력

Cmdlet는 오류를 보고할 수 있습니다. Cmdlet은 종료 오류가 발생 하면 예외가 발생 합니다. 비종료 오류가 발생 하는 cmdlet을 호출 합니다 [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) 메서드는 오류 데이터 스트림에 오류 레코드를 보내려고 합니다. 오류 보고에 대 한 자세한 내용은 참조 하세요. [오류 보고 개념](./error-reporting-concepts.md)합니다.

### <a name="verbose-output"></a>자세한 정보 출력

Cmdlet을 호출 하 여 레코드를 올바르게 처리 되는 동안 Cmdlet에 유용한 정보 제공할 수는 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) 메서드. 메서드는 작업을 처리 하는 방법을 나타내는 자세한 정보 표시 메시지를 생성 합니다.

기본적으로 자세한 정보 표시 메시지는 표시 되지 않습니다. 지정할 수 있습니다 합니다 **Verbose** 이러한 메시지를 표시 하도록 cmdlet이 실행 될 때 매개 변수입니다. **Verbose** 모든 cmdlet에 사용할 수 있는 일반적인 매개 변수입니다.

### <a name="progress-output"></a>진행률 출력

Cmdlet은 디렉터리를 재귀적으로 복사 하는 등을 완료 하려면 시간이 오래 걸리는 작업을 수행 하는 경우 Cmdlet에 진행률 정보를 제공할 수 있습니다. Cmdlet은 진행률 정보를 표시 하기 위해 호출 된 [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) 메서드.

### <a name="debug-output"></a>디버그 출력

Cmdlet은 cmdlet 코드 문제를 해결할 때 도움이 되는 디버그 메시지를 제공할 수 있습니다. Cmdlet은 디버그 정보를 표시 하기 위해 호출 된 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) 메서드.

기본적으로 디버그 메시지는 표시 되지 않습니다. 지정할 수 있습니다 합니다 **디버그** 이러한 메시지를 표시 하도록 cmdlet이 실행 될 때 매개 변수입니다. **디버그** 모든 cmdlet에 사용할 수 있는 일반적인 매개 변수입니다.

### <a name="warning-output"></a>경고 출력

Cmdlet를 호출 하 여 경고 메시지를 표시할 수는 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) 메서드.

기본적으로 경고 메시지가 표시 됩니다. 그러나 사용 하 여 경고 메시지를 구성할 수 있습니다 합니다 `$WarningPreference` 변수나를 사용 하 여는 **Verbose** 및 **디버그** cmdlet를 호출할 때 매개 변수입니다.

## <a name="displaying-output"></a>출력 표시

모든 쓰기 메서드 호출에 대 한 콘텐츠 표시는 특정 런타임 변수에 따라 결정 됩니다. 예외는 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 메서드. 이러한 변수를 사용 하 여 적절 한 코드에서 올바른 위치에 대 한 호출을 작성 하 고 걱정할 필요 없이 출력을 표시 해야 하면 때나을 만들 수 있습니다.

## <a name="accessing-the-output-functionality-of-a-host-application"></a>호스트 응용 프로그램의 출력 기능에 액세스

또한 직접 PowerShell 런타임을 통해 호스트 응용 프로그램의 출력 기능에 액세스 하는 cmdlet를 디자인할 수 있습니다. 호스트 대신 PowerShell이 제공한 Api를 사용 하 여 [System.Console](/dotnet/api/System.Console) 하거나 [System.Windows.Forms](/dotnet/api/System.Windows.Forms) cmdlet 다양 한 호스트를 사용 하 여 작동을 보장 합니다. 예를 들어: 합니다 **powershell.exe** 콘솔 호스트 합니다 **powershell_ise.exe** 그래픽 호스트, PowerShell remoting 호스트 및 타사 호스트 합니다.

## <a name="see-also"></a>참고 항목

[오류 보고 개념](./error-reporting-concepts.md)

[Cmdlet 개요](./cmdlet-overview.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)