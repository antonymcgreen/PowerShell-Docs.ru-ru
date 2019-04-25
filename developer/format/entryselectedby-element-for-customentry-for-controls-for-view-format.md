---
title: Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066249"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)

Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элементов управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) EntrySelectedBy для CustomEntry для элементов управления для представления (формат)

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
|[Элемент SelectionCondition для EntrySelectedBy для элементов управления для представления (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного определения для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для элементов управления для представления (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение элемента управления.|
|[TypeName-элемент для EntrySelectedBy для элементов управления для представления (формат)](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

Выбор условия используются для определения условия, которое должен существовать для определения используемого, например если объект имеет определенное свойство или когда значения конкретного свойства или скрипта, результатом которого является `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
