---
title: 구성 (형식)에 대 한 컨트롤에 대 한 CustomEntry EntrySelectedBy 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059221"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Configuration에 대한 Controls의 CustomEntry에 대한 EntrySelectedBy 요소(형식)

공용 컨트롤 또는이 컨트롤을 사용할 수 있어야 하는 조건을 정의 사용 하는.NET 형식을 정의 합니다. 이 요소는 서식 파일의 모든 보기에서 사용할 수 있는 공용 컨트롤을 정의할 때 사용 됩니다.

CustomControl Configuration (구성 (형식) CustomEntries 요소에 대 한 컨트롤에 대 한 구성 (형식) CustomControl 요소에 대 한 컨트롤에 대 한 Control 요소 구성 (형식)의 구성 요소 (형식) 컨트롤 요소 CustomEntry 구성 (형식)에 대 한 컨트롤에 대 한 구성 (형식) EntrySelectedBy 요소에 대 한 컨트롤에 대 한 CustomControl CustomEntry 요소 형식)

## <a name="syntax"></a>구문

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에는 `EntrySelectedBy` 요소입니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[구성 (형식)에 대 한 컨트롤에 대 한 EntrySelectedBy SelectionCondition 요소](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|선택적 요소입니다.<br /><br /> 공용 컨트롤 정의 사용할 수 있어야 하는 조건을 정의 합니다.|
|[구성 (형식)에 대 한 컨트롤에 대 한 EntrySelectedBy SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|선택적 요소입니다.<br /><br /> 공용 컨트롤의이 정의 사용 하는.NET 형식의 집합을 지정 합니다.|
|[구성 (형식)에 대 한 컨트롤에 대 한 EntrySelectedBy TypeName 요소](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|선택적 요소입니다.<br /><br /> 공용 컨트롤의이 정의 사용 하는.NET 형식을 지정 합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[구성 (형식)에 대 한 컨트롤에 대 한 CustomControl CustomEntry 요소](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|공용 컨트롤의 정의 제공 합니다.|

## <a name="remarks"></a>설명

최소한 각 정의 하나 이상의.NET 유형, 선택 항목 집합 또는 지정 된 선택 조건이 있어야 합니다. 형식, 선택 항목 집합 또는 지정할 수 있는 선택 조건 수가 최대 제한은 없습니다.

## <a name="see-also"></a>참고 항목

[구성 (형식)에 대 한 컨트롤에 대 한 EntrySelectedBy SelectionCondition 요소](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[구성 (형식)에 대 한 컨트롤에 대 한 EntrySelectedBy SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[구성 (형식)에 대 한 컨트롤에 대 한 CustomControl CustomEntry 요소](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[구성 (형식)에 대 한 컨트롤에 대 한 EntrySelectedBy TypeName 요소](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[서식 파일을 PowerShell 작성](./writing-a-powershell-formatting-file.md)
