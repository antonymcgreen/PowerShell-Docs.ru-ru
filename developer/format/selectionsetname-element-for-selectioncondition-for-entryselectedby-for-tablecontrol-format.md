---
title: Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863280"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения представления таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy для элемента SelectionSetName TableRowEntry (формат) SelectionCondition для EntrySelectedBy для TableRowEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должен существовать для этого определения представления таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования. Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[TypeName-элемент для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
