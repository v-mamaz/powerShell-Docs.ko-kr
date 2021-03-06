---
title: 인수 길이 확인 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, example
ms.assetid: d5ddaa6e-4904-46da-beb0-0295a8f38332
caps.latest.revision: 12
ms.openlocfilehash: 8a21675acd087df93f93c25952c78931255d60b3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857129"
---
# <a name="how-to-validate-the-argument-length"></a>인수 길이 유효성을 검사하는 방법

이 예제에서는 Windows PowerShell 런타임이 cmdlet을 실행 하기 전에 매개 변수 인수의 문자 (길이)의 수를 확인 하는 데 사용할 수 있는 유효성 검사 규칙을 지정 하는 방법을 보여 줍니다. ValidateLength 특성을 선언 하 여이 유효성 검사 규칙을 설정 합니다.

> [!NOTE]
> 이 특성을 정의 하는 클래스에 대 한 자세한 내용은 참조 하세요. [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)합니다.

## <a name="to-validate-the-argument-length"></a>인수 길이 유효성을 검사 하려면

- 다음 코드에 표시 된 것과 같이 유효성 검사 특성을 추가 합니다. 이 예제에서는 인수의 길이가 0 ~ 10 자 길이가 있어야 함을 지정 합니다.

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

이 특성을 선언 하는 방법에 대 한 자세한 내용은 참조 하세요. [ValidateLength 특성 선언을](./validatelength-attribute-declaration.md)합니다.

## <a name="see-also"></a>참고 항목

[ValidateLength 특성 선언](./validatelength-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)
