---
ms.date: 06/12/2017
contributor: JKeithB
keywords: gallery,powershell,cmdlet,psgallery
title: 패키지 삭제
ms.openlocfilehash: ca5e68fcad52e4c7561d2c2b3858228652f22e0b
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003863"
---
# <a name="deleting-packages"></a><span data-ttu-id="14df7-103">패키지 삭제</span><span class="sxs-lookup"><span data-stu-id="14df7-103">Deleting Packages</span></span>

<span data-ttu-id="14df7-104">PowerShell 갤러리는 패키지를 계속 사용해야 하는 사용자에게 영향을 주기 때문에 패키지의 영구 삭제를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-104">The PowerShell Gallery does not support permanent deletion of packages, because that would break anyone who is depending on it remaining available.</span></span>

<span data-ttu-id="14df7-105">대신, PowerShell 갤러리는 패키지를 '목록에서 제거'하는 방법을 지원합니다. 이 작업은 웹 사이트의 패키지 관리 페이지에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-105">Instead, the PowerShell Gallery supports a way to 'unlist' a package, which can be done in the package management page on the web site.</span></span>
<span data-ttu-id="14df7-106">패키지가 목록에서 제거되면 PowerShell 갤러리와 PowerShellGet 명령 사용 시 둘 다에서 검색과 패키지 목록에 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-106">When a package is unlisted, it no longer shows up in search and in any package listing, both on the PowerShell Gallery and using PowerShellGet commands.</span></span>
<span data-ttu-id="14df7-107">그러나 정확한 버전을 지정하여 자동화된 스크립트가 계속 작동할 수 있게 하면 항목을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-107">However, it remains downloadable by specifying its exact version, which is what allows the automated scripts to continue working.</span></span>

<span data-ttu-id="14df7-108">패키지 중 하나를 삭제해야 하는 예외적인 상황이 발생할 경우 PowerShell 갤러리 팀이 수동으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-108">If you run into an exceptional situation where you think one of your packages must be deleted, this can be handled manually by the PowerShell Gallery team.</span></span>
<span data-ttu-id="14df7-109">예를 들어 저작권 침해 문제 또는 잠재적으로 유해한 콘텐츠가 있을 경우 항목을 삭제해야 하는 유효한 이유가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-109">For example, if there is a copyright infringement issue, or potentially harmful content, that could be a valid reason to delete it.</span></span>
<span data-ttu-id="14df7-110">이 경우 [PowerShell 갤러리](http://www.PowerShellGallery.com)를 통해 지원 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14df7-110">You should submit a support request through [PowerShell Gallery](http://www.PowerShellGallery.com) in that case.</span></span>