---
title: Элемент SelectionSetName для EntrySelectedBy для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9c6e18f-6cca-465c-bd20-3969e7897a96
caps.latest.revision: 10
ms.openlocfilehash: 6b6a4a4647412d11d947f1dc4ea12d1e05ff536e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856800"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)

Задает набор объектов .NET, для определения. Определение используется в том случае, когда отображается одно из этих объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionSetName WideEntry (формат) для EntrySelectedBy для WideEntry (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Определяет типы .NET, использующих эту запись широкий или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Каждое определение необходимо указать одно имя типа, выбора или условию выбора.

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Например можно создать представление таблицы и представления списка для одного набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
