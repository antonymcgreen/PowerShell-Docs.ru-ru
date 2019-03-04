---
title: Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13a429c-a31b-4e29-828c-c0c0917b5415
caps.latest.revision: 11
ms.openlocfilehash: baea89e4b259611dfa45b6bcf94fa0bf2df6b9de
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854130"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения широкое представление.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy элемента SelectionSetName WideEntry (формат) для SelectionCondition для EntrySelectedBy для WideEntry (формат)

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
|[Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Определяет условие, которое должен существовать для данного определения для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования. Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
