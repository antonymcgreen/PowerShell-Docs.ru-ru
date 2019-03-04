---
title: Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855170"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)

Определяет условие, которое должен существовать для определения элемента управления для использования. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionCondition GroupBy (формат) для EntrySelectedBy для GroupBy (формат)

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
|[Элемент PropertyName для SelectionCondition для GroupBy (формат)](./propertyname-element-for-selectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для GroupBy (формат)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для GroupBy (формат)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[TypeName-элемент для SelectionCondition для GroupBy (формат)](./typename-element-for-selectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.|

## <a name="remarks"></a>Замечания

При определении условию выбора, применяются следующие требования:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент SelectionSetName для SelectionCondition для пользовательского элемента управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[TypeName-элемент для SelectionCondition для GroupBy (формат)](./typename-element-for-selectioncondition-for-groupby-format.md)

[Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
