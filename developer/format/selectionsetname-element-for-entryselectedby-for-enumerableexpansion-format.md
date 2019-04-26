---
title: Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076265"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Указывает набор типов .NET, которые расширяются в соответствии с этим определением.

Элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansion (формат) EntrySelectedBy элемента конфигурации для элемента SelectionSetName EnumerableExpansion (формат) EntrySelectedBy для EnumerableExpansion (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)|Определяет коллекцию объектов .NET, которые будут развернуты в соответствии с этим определением.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Каждое определение необходимо указать один или несколько имен типов, выбора или условию выбора.

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Например можно создать представление таблицы и представления списка для одного набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).

## <a name="see-also"></a>См. также

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент EntrySelectedBy для EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
