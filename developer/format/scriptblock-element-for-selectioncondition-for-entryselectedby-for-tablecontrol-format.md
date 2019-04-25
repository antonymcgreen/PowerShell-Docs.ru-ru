---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076350"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает блок скрипта, который активирует условие. При вычислении этого сценария для `true`условие выполняется, и записи в таблице используется.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy TableRowEntry (формат) элемента ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должен существовать для этой записи таблицы для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

Условию выбора необходимо указать по крайней мере один скрипт блока или имя свойства, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
