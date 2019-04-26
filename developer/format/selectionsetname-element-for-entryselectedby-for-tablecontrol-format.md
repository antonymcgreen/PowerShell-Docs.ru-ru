---
title: Элемент SelectionSetName для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063927"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает, что набор .NET вводит использование этой записи таблицы представления. Количество наборов выбора, которые можно задать для записи не ограничено.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент EntrySelectedBy (формат) SelectionSetName элемент конфигурации для EntrySelectedBy для TableRowEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Атрибуты, дочерние и родительские элементы в следующих разделах.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, использующих эту запись или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Например можно создать представление таблицы и представления списка для одного набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).

При указании выбора для записи, невозможно указать имя типа. Дополнительные сведения о том, как задать тип .NET, см. в разделе [элемент TypeName для EntrySelectedBy для TableRowEntry (формат)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Определение наборов объектов для представления](./defining-selection-sets.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
