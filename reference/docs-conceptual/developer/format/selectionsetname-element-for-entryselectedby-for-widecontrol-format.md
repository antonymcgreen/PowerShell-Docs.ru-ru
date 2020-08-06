---
title: Элемент Селектионсетнаме для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 546225b0619ebec83d04a7e27bbc298ffef0a14d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785257"
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

## <a name="remarks"></a>Примечания

Каждое определение должно содержать одно имя типа, набор выбора или условие выбора.

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкого представления](./creating-a-wide-view.md)

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент EntrySelectedBy для элемента WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
