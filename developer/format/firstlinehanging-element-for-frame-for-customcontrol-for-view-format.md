---
title: 뷰 (형식)에 대 한 CustomControl 프레임에 대 한 FirstLineHanging 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6ac3d86-0529-4b93-9bc7-ee94fcef9618
caps.latest.revision: 8
ms.openlocfilehash: ea43e025f5f653ff000e1d7591b535e73da5c9e5
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054223"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a>View에 대한 CustomControl의 Frame에 대한 FirstLineHanging 요소(형식)

데이터의 첫 번째 줄은 왼쪽으로 이동 하는 문자 수를 지정 합니다. 이 요소는 사용자 지정 컨트롤 뷰를 정의할 때 사용 됩니다.

구성 요소 (형식) ViewDefinitions 요소 (형식) 보기 (형식) CustomControl 요소 (형식) CustomEntries 요소 CustomControl CustomEntries CustomItem 요소 (형식) 보기에 대 한 보기 (형식) CustomEntry 요소에 대 한 CustomControlView (형식) 프레임에 대 한 요소의 CustomControl CustomControl 보려면 (형식)에 대 한 프레임에 대 한 보기 (형식) FirstLineHanging 요소에 대 한 CustomItem CustomEntry

## <a name="syntax"></a>구문

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에는 `FirstLineHanging` 요소입니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[CustomItem CustomControl 보려면 (형식)에 대 한 프레임 요소](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|왼쪽 또는 오른쪽에 데이터를 이동 하는 등 데이터를 표시 하는 방법을 정의 합니다.|

## <a name="text-value"></a>텍스트 값

데이터의 첫 번째 줄을 이동 하려는 문자 수를 지정 합니다.

## <a name="remarks"></a>설명

이 요소를 지정 하는 경우를 지정할 수 없습니다는 [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) 요소입니다.

## <a name="see-also"></a>참고 항목

[뷰 (형식)에 대 한 CustomControl 프레임에 대 한 FirstLineIndent 요소](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[CustomItem CustomControl 보려면 (형식)에 대 한 프레임 요소](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[서식 파일을 PowerShell 작성](./writing-a-powershell-formatting-file.md)
