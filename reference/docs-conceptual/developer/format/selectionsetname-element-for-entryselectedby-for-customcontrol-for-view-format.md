---
title: Элемент Селектионсетнаме для Ентриселектедби для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364753"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)

Задает набор объектов .NET для записи списка. Количество наборов выбора, которые можно указать для записи, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для представления (Format) Ентриселектедби Элемент для Кустоментри для элемента Селектионсетнаме представления (Format) для Ентриселектедби для Кустоментри (Format)

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
|[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Для каждой записи пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также:

[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Представление пользовательского элемента управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
