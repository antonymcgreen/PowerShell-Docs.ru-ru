---
title: Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42143d1e-7cda-4c4a-b568-fa1951bb9417
caps.latest.revision: 6
ms.openlocfilehash: 9060ee54d6f88c7f910b16cf5c9b87f37844b736
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860910"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)

Задает набор типов .NET, которые используют это определение элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента конфигурации (формат) SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)

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
|[Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Каждое определение элемента управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Дополнительные сведения об определении наборов выбора см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
