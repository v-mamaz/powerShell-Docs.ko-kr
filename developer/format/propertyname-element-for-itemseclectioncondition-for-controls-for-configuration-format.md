---
title: 구성 (형식)에 대 한 컨트롤에 대 한 ItemSeclectionCondition PropertyName 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8ab181-c559-492e-a0cf-299e381fdcc3
caps.latest.revision: 6
ms.openlocfilehash: ce25789bdfc2679372ca9e42f99dcc6a30ae2def
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860929"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Configuration에 대한 Controls의 ItemSelectionCondition에 대한 PropertyName 요소(형식)

조건이 트리거하는.NET 속성을 지정 합니다. 이 속성이 있는 경우 또는로 평가 되 면 `true`조건이 충족 되 고 컨트롤이 사용 합니다. 이 요소는 서식 파일의 모든 보기에서 사용할 수 있는 공용 컨트롤을 정의할 때 사용 됩니다.

CustomControl Configuration (구성 (형식) CustomEntries 요소에 대 한 컨트롤에 대 한 구성 (형식) CustomControl 요소에 대 한 컨트롤에 대 한 Control 요소 구성 (형식)의 구성 요소 (형식) 컨트롤 요소 CustomEntry CustomItem 구성 (형식)에 대 한 컨트롤에 대 한 구성 ExpressionBinding 요소에 대 한 컨트롤에 대 한 구성 (형식) CustomItem 요소에 대 한 컨트롤에 대 한 CustomControl CustomEntry 요소 형식) ExpressionBinding ItemSeclectionCondition 구성 (형식)에 대 한 컨트롤에 대 한 구성 (형식) PropertyName 요소에 대 한 컨트롤에 대 한 ItemSelectionCondition 요소

## <a name="syntax"></a>구문

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에는 `PropertyName` 요소입니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[구성 (형식)에 대 한 컨트롤에 대 한 ExpressionBinding에 대 한 ItemSelectionCondition 요소](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|이 컨트롤을 사용할 수 있어야 하는 조건을 정의 합니다.|

## <a name="text-value"></a>텍스트 값

조건이 트리거하는.NET 속성의 이름을 지정 합니다.

## <a name="remarks"></a>설명

이 요소를 사용 하는 경우를 지정할 수 없습니다는 [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) 요소 선택 조건을 정의할 수 있습니다.

## <a name="see-also"></a>참고 항목

[구성 (형식)에 대 한 컨트롤에 대 한 ItemSeclectionCondition ScriptBlock 요소](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[구성 (형식)에 대 한 컨트롤에 대 한 ExpressionBinding에 대 한 ItemSelectionCondition 요소](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[서식 파일을 PowerShell 작성](./writing-a-powershell-formatting-file.md)
