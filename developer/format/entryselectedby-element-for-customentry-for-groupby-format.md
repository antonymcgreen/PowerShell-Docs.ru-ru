---
title: Элемент EntrySelectedBy для CustomEntry для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066232"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)

Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) CustomEntry для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения. Не ограничено максимальное число дочерних элементов, которые можно использовать.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного определения для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение элемента управления.|
|[TypeName-элемент для EntrySelectedBy для GroupBy (формат)](./typename-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

Выбор условия используются для определения условия, которое должен существовать для определения используемого, например если объект имеет определенное свойство или когда значения конкретного свойства или скрипта, результатом которого является `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[TypeName-элемент для EntrySelectedBy для GroupBy (формат)](./typename-element-for-entryselectedby-for-groupby-format.md)

[Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
