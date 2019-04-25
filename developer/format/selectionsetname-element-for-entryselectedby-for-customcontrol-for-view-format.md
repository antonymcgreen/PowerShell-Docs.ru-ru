---
title: Элемент SelectionSetName для EntrySelectedBy для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063983"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)

Задает набор объектов .NET для записи в списке. Количество наборов выбора, которые можно задать для записи не ограничено.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для EntrySelectedBy представление (формат) Элемент для CustomEntry для элемента представления (формат) SelectionSetName для EntrySelectedBy для CustomEntry (формат)

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
|[Элемент EntrySelectedBy для CustomEntry для представления (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет типы .NET, использующих этот пользовательскую запись или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Замечания

Каждая запись пользовательский элемент управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.

Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях. Например можно создать представление таблицы и представления списка для одного набора объектов. Дополнительные сведения об определении наборов выбора см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также

[Элемент EntrySelectedBy для CustomEntry для представления (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Представление пользовательского элемента управления](./creating-custom-controls.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
