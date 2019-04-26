---
title: Элемент SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: 633204f3b181316761746ea2679910216fb74657
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064107"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Определяет условие, которое должна существовать, чтобы использовать это определение представления "list". Нет ограничений на число условий выборки, которые могут быть указаны для определения списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy для ListEntry (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые активируют условие.|
|[TypeName-элемент для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для TableRowEntry (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, использующих этой записи таблицы или условие, которое должен существовать для данной записи для использования.|

## <a name="remarks"></a>Замечания

lWhen при определении условию выбора, применяются следующие требования:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент ListEntry (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент SelectionSetName для EntrySelectedBy для ListEntry (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[TypeName-элемент для EntrySelectedBy для ListEntry (формат)](http://msdn.microsoft.com/en-us/fcd4daa6-f3fd-43f7-a468-03c582d34533)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
