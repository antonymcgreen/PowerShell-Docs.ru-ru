---
title: Элемент SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861240"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Определяет условие, которое должен существовать для этого определения представления таблицы. Нет ограничений на число условий выборки, которые могут быть указаны для определения таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Атрибуты, дочерние элементы и родительский элемент элемента SelectionCondition в следующих разделах.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые активируют условие.|
|[TypeName-элемент для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для TableRowEntry (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, использующих этой записи таблицы или условие, которое должен существовать для данной записи для использования.|

## <a name="remarks"></a>Замечания

Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

При определении условию выбора, применяются следующие требования:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент EntrySelectedBy (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[TypeName-элемент для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
