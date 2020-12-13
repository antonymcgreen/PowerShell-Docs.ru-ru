---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: a158c5476fb3a168a146ce67565c0ed6f7859519
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651909"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)

Задает набор объектов .NET для записи списка. Количество наборов выбора, которые можно указать для записи, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления для кустоментриес для представления (Format) ентриселектедби для кустоментри для SelectionSetName for EntrySelectedBy (формат).

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
|[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Комментарии

Для каждой записи пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также:

[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Представление пользовательского элемента управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
