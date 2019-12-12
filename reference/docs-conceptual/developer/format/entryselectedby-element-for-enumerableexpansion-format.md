---
title: Элемент Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368803"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)

Определяет типы .NET, которые используют это определение, или условие, которое должно существовать, чтобы использовать это определение.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби для Енумерабликспансион (Format)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.|
|[Элемент Селектионсетнаме для Ентриселектедби для Енумерабликспансион (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение того, как разворачиваются объекты коллекции.|
|[Элемент TypeName для Ентриселектедби для Енумерабликспансион (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение того, как разворачиваются объекты коллекции.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Енумерабликспансион (Format)](./enumerableexpansion-element-format.md)|Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи определения. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта оценивается как `true`. Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Енумерабликспансион (Format)](./enumerableexpansion-element-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Енумерабликспансион (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент TypeName для Ентриселектедби для Енумерабликспансион (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
