---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651699"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)

Задает набор объектов .NET для определения. Определение используется при каждом отображении одного из этих объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионсетнаме для EntrySelectedBy в WideEntry (Format)

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
|[Элемент EntrySelectedBy для элемента WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Комментарии

Каждое определение должно содержать одно имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также:

[Создание широкого представления](./creating-a-wide-view.md)

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент EntrySelectedBy для элемента WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
