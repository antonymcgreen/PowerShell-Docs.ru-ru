---
title: Элемент PropertyName для SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: f857f5944b9e971215a06d6f5c39f7c22c6cf99f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853300"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Задает свойство .NET, которое активирует условие. Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется элемент списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy элемента PropertyName ListEntry (формат) для SelectionCondition для EmtrySelectedBy для ListEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должен существовать для записи в этом списке для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Замечания

Условию выбора необходимо указать по крайней мере для одного имени свойства или блок скрипта, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Определение условия для данных, когда отображается](./defining-conditions-for-displaying-data.md)

[Элемент ListEntry (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
