---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
ms.openlocfilehash: 57152e9f62c34600df63a2db8e9683928e825d93
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680783"
---
# <a name="detailed-information-about-lcm-state"></a>LCM 상태에 대한 자세한 정보

LCM 상태에 대한 세부 정보를 노출하는 기능이 향상되었습니다. 이제 Get-DscLocalConfigurationManager에서 반환되는 LCMState에 다음과 같은 값이 포함될 수 있습니다.

* **유휴 상태**
* **사용 중**
* **PendingReboot**
* **PendingConfiguration**

또한 상태에 대한 자세한 정보를 포함하는 LCMStateDetail 속성이 추가되었습니다.
