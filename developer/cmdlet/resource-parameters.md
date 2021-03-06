---
title: 리소스 매개 변수 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 460c43aa-f5c5-4a1a-a6f2-5e07db143de1
caps.latest.revision: 5
ms.openlocfilehash: 9752570e5c997ef4da56a08df14f39b77ba37a4a
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251203"
---
# <a name="resource-parameters"></a>리소스 매개 변수

다음 표에서 권장 되는 이름 및 리소스 매개 변수에 대 한 기능을 나열합니다. 이러한 매개 변수에 대 한 리소스는 cmdlet 클래스 또는 cmdlet을 실행 하는 호스트 응용 프로그램을 포함 하는 어셈블리 수 있습니다.

|매개 변수|기능|
|---|---|
|**응용 프로그램**<br>데이터 형식: 문자열|사용자는 응용 프로그램을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**Assembly**<br>데이터 형식: 문자열|사용자 어셈블리를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**특성**<br>데이터 형식: 문자열|사용자 특성을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**클래스**<br>데이터 형식: 문자열|사용자는 Microsoft.NET Framework 클래스를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**클러스터**<br>데이터 형식: 문자열|사용자는 클러스터를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**문화권**<br>데이터 형식: 문자열|사용자는 cmdlet을 실행 하는 문화권을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**도메인**<br>데이터 형식: 문자열|사용자 도메인 이름을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**드라이브**<br>데이터 형식: 문자열|사용자 드라이브 이름을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**이벤트**<br>데이터 형식: 문자열|사용자 이벤트 이름을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**인터페이스**<br>데이터 형식: 문자열|사용자는 네트워크 인터페이스 이름을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**IpAddress**<br>데이터 형식: 문자열|사용자 IP 주소를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**Job**<br>데이터 형식: 문자열|사용자 작업을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**LiteralPath**<br>데이터 형식: 문자열|와일드 카드 문자는 지원 되지 않는 경우 사용자 리소스에 대 한 경로 지정할 수 있도록이 매개 변수를 구현 합니다. (사용 된 **경로** 와일드 카드 문자는 지원 되는 경우 매개 변수.)|
|**Mac**<br>데이터 형식: 문자열|사용자에 미디어 액세스 컨트롤러 (MAC) 주소를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**ParentId**<br>데이터 형식: 문자열|사용자의 부모 식별자를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**경로**<br>데이터 형식: String, String[]|와일드 카드 문자는 지원 되는 경우 사용자 리소스에 대 한 경로 지정할 수 있도록이 매개 변수를 구현 합니다. (사용 된 **LiteralPath** 매개 변수에 와일드 카드 문자가 지원 되지 않습니다.) 전체 지원 되도록이 매개 변수를 개발 하는 것이 좋습니다 `provider:path` 공급자가 사용 되는 구문입니다. 또한 가능한 만큼 공급자와 작동 되도록 개발 하는 것이 좋습니다.|
|**포트**<br>데이터 형식: 정수, 문자열|네트워킹에 대 한 정수 값 또는 "biztalk" 다른 형식에 대 한 포트 같은 문자열 값을 사용자 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**프린터**<br>데이터 형식: 정수, 문자열|사용자를 사용 하 여 cmdlet에 대 한 프린터를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**크기**<br>데이터 형식: Int32|사용자는 크기를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**TID**<br>데이터 형식: 문자열|사용자는 cmdlet에 대 한 트랜잭션 id (TID) 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**형식**<br>데이터 형식: 문자열|사용자는 작동 하는 리소스의 유형을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**URL**<br>데이터 형식: 문자열|사용자는 로케이터 URL (Uniform Resource)을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**User**<br>데이터 형식: 문자열|해당 이름이 나 다른 사용자의 이름을 사용자 지정할 수 있도록이 매개 변수를 구현 합니다.|

## <a name="see-also"></a>참고 항목

[Cmdlet 매개 변수](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)

[Windows PowerShell SDK](../windows-powershell-reference.md)
