---
title: ScriptBlock 요소 CustomControl 보려면 (형식)에 대 한 SelectionCondition | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7031fa8b-3e2b-4ea8-89cb-95171f467b5a
caps.latest.revision: 6
ms.openlocfilehash: e55d1c5aa533005b258ecbbbf3ed9d55f852eab6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857419"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a>View에 대한 CustomControl의 SelectionCondition에 대한 ScriptBlock 요소(형식)

조건이 트리거하는 스크립트를 지정 합니다. 이 스크립트를 계산할 때 `true`조건이 충족 되 고 정의가 사용 됩니다. 이 요소는 사용자 지정 컨트롤 뷰를 정의할 때 사용 됩니다.

구성 요소 (형식) ViewDefinitions 요소 (형식) 보기 (형식) CustomControl 요소 CustomControl CustomEntries CustomControl 보기 (에 대 한 보기 (형식) CustomEntry 요소에 대 한 보기 (형식) CustomEntries 요소에 CustomControl EntrySelectedBy CustomControl SelectionCondition CustomControl 보려면 (형식)에 대 한 보기 (형식) ScriptBlock 요소에 대 한 보기 (형식) SelectionCondition 요소에 대 한 CustomEntry CustomItem 요소 형식)

## <a name="syntax"></a>구문

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에는 `ScriptBlock` 요소입니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[CustomControl 보려면 (형식)에 대 한 EntrySelectedBy SelectionCondition 요소](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|사용할 컨트롤 정의에 있어야 하는 조건을 정의 합니다.|

## <a name="text-value"></a>텍스트 값

계산 되는 스크립트를 지정 합니다.

## <a name="remarks"></a>설명

선택 조건 최소 하나의 스크립트 또는 속성 이름을 평가 수행 하려면을 지정 해야 하지만 둘 다 지정할 수 없습니다. 선택 조건을 사용할 수 있는 방법에 대 한 자세한 내용은 참조 하세요. [표시 데이터에 대 한 조건을 정의](./defining-conditions-for-displaying-data.md)합니다.

## <a name="see-also"></a>참고 항목

[CustomControl 보려면 (형식)에 대 한 EntrySelectedBy SelectionCondition 요소](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[서식 파일을 PowerShell 작성](./writing-a-powershell-formatting-file.md)
