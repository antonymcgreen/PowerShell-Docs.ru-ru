---
title: TypeName-элемент для SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e97d56fb-4e35-447a-9282-26f10d0a4609
caps.latest.revision: 11
ms.openlocfilehash: fe65ac95cead7df0069ffdae666fb34b7309fbb6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856500"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает тип .NET, который активирует условие. При наличии этого типа условие выполняется, и используется строке таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy элемента TypeName TableRowEntry (формат) для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должен существовать для строки таблицы для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
