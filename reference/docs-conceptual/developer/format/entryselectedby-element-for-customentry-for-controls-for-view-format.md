---
title: Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5c82e02d23b1694d05f7a32578ccc5d33686f13f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774258"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)

Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol для элемента Control для элементов управления для элемента "View" (формат) Кустоментриес для ошибка customcontrol для элементов управления для представления (Format) кустоментри для кустоментриес для элементов управления представления (формат).

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение элемента управления.|
|[Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Примечания

Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства не равны `true` . Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
