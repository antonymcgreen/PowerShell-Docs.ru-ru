---
title: Элемент SelectionSetName для EntrySelectedBy для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861000"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)

Задает набор типов .NET, которые используют это определение элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элементов управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента представления (формат) SelectionSetName для EntrySelectedBy для элементов управления (представление Формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.

### <a name="attributes"></a>Атрибуты

Нет

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Каждое определение элемента управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Дополнительные сведения об определении наборов выбора см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
