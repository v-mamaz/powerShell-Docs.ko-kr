---
title: Windows PowerShell 참조 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows PowerShell SDK
ms.assetid: cbba4879-bcac-484a-9906-4bbe2cd1eb33
caps.latest.revision: 11
ms.openlocfilehash: 86595ebaac32318a4e3b9a3c4b295c73fb2e1c75
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055498"
---
# <a name="windows-powershell-reference"></a>Windows PowerShell 참조

Windows PowerShell에는 관리 자동화를 위한 Microsoft.NET Framework에 연결 된 환경입니다. Windows PowerShell 명령을 빌드, 솔루션을 작성 및 그래픽 사용자 인터페이스 기반 관리 도구를 만들 수 있는 새로운 방법을 제공 합니다.

Windows PowerShell 명령 실행 하 여 시스템 리소스의 관리를 자동화 하려면 시스템 관리자를 통해 직접 또는 스크립트를 통해.

## <a name="developer-audience"></a>개발자 대상

Windows PowerShell 소프트웨어 개발 키트 (SDK)는 Windows PowerShell에서 제공 하는 Api에 대 한 참조 정보를 필요로 하는 명령 개발자를 위한 기록 됩니다. 명령 개발자 명령 및 Windows PowerShell에서 수행할 수 있는 작업을 확장 하는 공급자를 만들려면 Windows PowerShell을 사용 합니다.

## <a name="windows-powershell-resources"></a>Windows PowerShell 리소스

Windows PowerShell SDK 외에도 다음 리소스를 자세한 정보를 제공 합니다.

[Windows PowerShell 시작](/powershell/scripting/getting-started/getting-started-with-windows-powershell) Windows PowerShell에 대해 소개 합니다: 언어, cmdlet, 공급자 및 개체의 사용 합니다.

[Windows PowerShell 모듈 작성](./module/writing-a-windows-powershell-module.md) 관리자, 스크립트 개발자 및 패키지 및 Windows PowerShell 모듈을 사용 하 여 해당 Windows PowerShell 솔루션을 배포 해야 하는 cmdlet 개발자에 대 한 정보와 예제를 제공 합니다.

[Windows PowerShell Cmdlet 작성](./cmdlet/writing-a-windows-powershell-cmdlet.md) cmdlet 코드를 구현 하는 개발자 및 cmdlet을 디자인 하는 프로그램 관리자에 대 한 정보 및 코드 예제를 제공 합니다.

[Windows PowerShell 팀 블로그](https://blogs.msdn.microsoft.com/PowerShell/) 에서 학습 하 고 다른 Windows PowerShell 사용자와 공동 작업에 대 한 최상의 리소스입니다. Windows PowerShell 팀 블로그를 읽고 Windows PowerShell 사용자 포럼 (microsoft.public.windows.powershell)를 조인 합니다. Windows Live Search를 사용 하 여 다른 Windows PowerShell 블로그 및 리소스를 찾습니다. 그런 다음 전문 지식을 개발 하는 경우, 귀하의 아이디어 자유롭게 기여 합니다.

[PowerShell 모듈 브라우저](/powershell/module/) 명령줄 도움말 항목의 최신 버전을 제공 합니다.

## <a name="class-libraries"></a>클래스 라이브러리

[System.Management.Automation](/dotnet/api/System.Management.Automation) 이 네임 스페이스는 Windows PowerShell에 대 한 루트 네임 스페이스입니다. 클래스, 열거형 및 사용자 지정 cmdlet을 구현 하는 데 필요한 인터페이스를 포함 합니다. 특히 합니다 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) 클래스는 기본 클래스는 모든 cmdlet에서 클래스가 파생 되어야 합니다. Cmdlet에 대 한 자세한 내용은 다음을 참조 하세요.

[System.Management.Automation.Provider](/dotnet/api/System.Management.Automation.Provider) 클래스, 열거형 및 인터페이스는 Windows PowerShell 공급자를 구현 하는 데 필요한이 네임 스페이스에 포함 되어 있습니다. 특히 합니다 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 클래스는 기본 클래스는 모든 Windows PowerShell에서 공급자 클래스를 파생 되어야 합니다.

[Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) 이 네임 스페이스 Windows PowerShell에 의해 구현 되는 공급자와 cmdlet에 대 한 클래스를 포함 합니다. 마찬가지로, 것이 좋습니다 사용자가 만든를 *YourName*합니다. 구현 하는 이러한 cmdlet에 대 한 네임 스페이스는 명령입니다.

[System.Management.Automation.Host](/dotnet/api/System.Management.Automation.Host) 클래스, 열거형 및 인터페이스는 사용자 및 Windows PowerShell 간의 상호 작용을 정의 하는 cmdlet이 네임이 스페이스에 포함 되어 있습니다.

[System.Management.Automation.Internal](/dotnet/api/System.Management.Automation.Internal) 이 네임 스페이스에는 다른 네임 스페이스 클래스에서 사용 하는 기본 클래스를 포함 합니다. 예를 들어 합니다 [System.Management.Automation.Internal.Cmdletmetadataattribute](/dotnet/api/System.Management.Automation.Internal.CmdletMetadataAttribute) 클래스는 기본 클래스에 대 한 합니다 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) 클래스.

[System.Management.Automation.Runspaces](/dotnet/api/System.Management.Automation.Runspaces) 클래스, 열거형 및 인터페이스는 Windows PowerShell runspace를 만드는 데이 네임 스페이스에 포함 되어 있습니다. 이 컨텍스트에서 Windows PowerShell runspace는 하나 이상의 Windows PowerShell 파이프라인 cmdlet을 호출 하는 컨텍스트입니다. 즉, cmdlet은 Windows PowerShell runspace의 컨텍스트 내에서 작동합니다. 자세한 내용은 aboutWindows PowerShell runspace에 대 한 참조 [Windows PowerShell Runspace](http://msdn.microsoft.com/en-us/a1582cfe-f06d-4aff-adc6-71f49a860ce9)합니다.
