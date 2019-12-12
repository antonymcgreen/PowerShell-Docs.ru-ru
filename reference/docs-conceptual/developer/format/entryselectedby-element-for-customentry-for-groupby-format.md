---
title: Элемент Ентриселектедби для Кустоментри для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363863"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)

Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy (Format) для Кустоментри для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение элемента управления.|
|[Элемент TypeName для Ентриселектедби для GroupBy (Format)](./typename-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для ошибка customcontrol для GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства имеют `true`. Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[Элемент TypeName для Ентриселектедби для GroupBy (Format)](./typename-element-for-entryselectedby-for-groupby-format.md)

[Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
