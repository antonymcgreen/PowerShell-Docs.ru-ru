---
title: Элемент Селектионсетнаме для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 8745ef9e6f326c3e8a5dbf185a595bbe93e92414
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785325"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Указывает набор типов .NET, развернутых этим определением.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionSetName для EntrySelectedBy в EnumerableExpansion (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)|Определяет объекты коллекции .NET, развернутые этим определением.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Каждое определение должно указывать одно или несколько имен типов, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).

## <a name="see-also"></a>См. также

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
