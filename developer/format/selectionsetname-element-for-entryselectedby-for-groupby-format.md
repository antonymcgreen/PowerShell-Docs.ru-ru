---
title: Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569c623-2277-49e3-933e-c26262b91cd5
caps.latest.revision: 6
ms.openlocfilehash: 69cd113c444b4e3c5dceabcdfddb439cd1376f6b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858860"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)

Задает набор объектов .NET для записи в списке. Количество наборов выбора, которые можно задать для записи не ограничено. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionSetName GroupBy (формат) для EntrySelectedBy для GroupBy (формат)

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
|[Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)|Определяет типы .NET, использующих этот пользовательскую запись или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Каждое определение пользовательского элемента управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Например можно создать представление таблицы и представления списка для одного набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[Создание пользовательских элементов управления](./creating-custom-controls.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
