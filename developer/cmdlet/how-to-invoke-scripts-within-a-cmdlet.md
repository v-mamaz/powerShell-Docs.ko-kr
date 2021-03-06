---
title: Cmdlet 내에서 스크립트를 호출 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 7dcb8bc20ab56225764854f9dc6fdfd858ed7451
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055787"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>Cmdlet 내에서 스크립트를 호출하는 방법

이 예제에서는 cmdlet에 제공 된 스크립트를 호출 하는 방법을 보여 줍니다. Cmdlet 스크립트를 실행 하 고 그 결과의 컬렉션으로 cmdlet에 반환 됩니다 [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) 개체입니다.

## <a name="to-invoke-a-script-block"></a>스크립트 블록을 호출 하려면

1. 명령은 스크립트 블록을 cmdlet에 제공 된 있는지 확인 합니다. 스크립트 블록을 제공한 경우이 명령은 해당 필수 매개 변수를 사용 하 여 스크립트 블록을 호출 합니다.

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. 스크립트의 반환 된 컬렉션을 반복 하는 차례로 [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) 개체 및 필요한 작업을 수행 합니다.

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a>참고 항목

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)
