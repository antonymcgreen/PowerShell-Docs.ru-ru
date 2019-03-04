---
title: Элемент SelectionCondition для EntrySelectedBy для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854120"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)

Определяет условие, которое должен существовать для данного определения для использования. Нет ограничений на число условий выборки, которые могут быть указаны для определения расширенных запись.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy для WideEntry (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент. Необходимо указать один `PropertyName` или `ScriptBlock` элемент. `SelectionSetName` И `TypeName` элементы являются необязательными. Можно указать один из любой из элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает блок скрипта, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Определяет типы .NET, использующих эту запись широкий или условие, которое должен существовать для данной записи для использования.|

## <a name="remarks"></a>Замечания

Каждый расширенный запись должна иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

При определении условию выбора, применяются следующие требования:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)

[Элемент PropertyName для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
