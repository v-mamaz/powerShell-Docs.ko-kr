---
title: GroupBy (형식)에 대 한 ItemSelectionCondition ScriptBlock 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58d25835-4636-4c58-9f6c-0332b9318051
caps.latest.revision: 6
ms.openlocfilehash: 4045196e306e766cd805b3e7ae31bfcb3de184ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860949"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a>GroupBy의 ItemSelectionCondition에 대한 ScriptBlock 요소(형식)

조건이 트리거하는 스크립트를 지정 합니다. 이 스크립트를 계산할 때 `true`조건이 충족 되 고 컨트롤이 사용 합니다. 이 요소는 새 개체 그룹에 표시 되는 방식을 정의 하는 경우에 사용 됩니다.

구성 요소 (형식) ViewDefinitions 요소 (형식) 보기 (형식) GroupBy 요소 CustomControl GroupBy (형식) CustomEntry 요소에 대 한 GroupBy (형식) CustomEntries 요소에 대 한 보기 (형식) CustomControl 요소에 대 한 CustomControl CustomEntry CustomItem ExpressionBinding GroupBy (형식) ScriptBlock 요소에 대 한 GroupBy (형식) ItemSelectionCondition 요소에 대 한 GroupBy (형식) ExpressionBinding 요소에 대 한 GroupBy (형식) CustomItem 요소에 GroupBy (형식)에 대 한 ItemSelectionCondition

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
|[GroupBy (형식)에 대 한 ExpressionBinding에 대 한 ItemSelectionCondition 요소](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|이 컨트롤을 사용할 수 있어야 하는 조건을 정의 합니다.|

## <a name="text-value"></a>텍스트 값

계산 되는 스크립트를 지정 합니다.

## <a name="remarks"></a>설명

이 요소를 사용 하는 경우를 지정할 수 없습니다는 [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) 요소 선택 조건을 정의할 수 있습니다.

## <a name="see-also"></a>참고 항목

[GroupBy (형식)에 대 한 ExpressionBinding에 대 한 ItemSelectionCondition 요소](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (형식)에 대 한 ItemSelectionCondition PropertyName 요소](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[서식 파일을 PowerShell 작성](./writing-a-powershell-formatting-file.md)
