---
title: Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 362f7844c09a52494387a62e329adfb309767427
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785291"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)

Задает набор объектов .NET для записи списка. Количество наборов выбора, которые можно указать для записи, не ограничено. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format) селектионсетнаме для EntrySelectedBy for GroupBy (формат)

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
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Для каждого определения пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
