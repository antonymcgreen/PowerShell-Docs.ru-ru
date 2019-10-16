---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7af0b2-68e6-43c3-adcc-7c58007fced8
caps.latest.revision: 13
ms.openlocfilehash: 6f7c8d9af3c1c2fbda0208148b0088161701fdbe
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361993"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие будет выполнено.

Элемент конфигурации Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансионс элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy Енумерабликспансион (Format) Селектионсетнаме элемент для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

## <a name="see-also"></a>См. также:

[Определение наборов выбора](./defining-selection-sets.md)

[Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
