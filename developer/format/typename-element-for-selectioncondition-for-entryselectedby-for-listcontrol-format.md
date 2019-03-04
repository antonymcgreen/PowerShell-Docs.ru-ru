---
title: TypeName-элемент для SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862780"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Указывает тип .NET, который активирует условие. При наличии этого типа используется элемент списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для EntrySelectedBy элемента ListControl (формат) ListEntry для элемента ListControl (формат) SelectionCondition EntrySelectedBy для элемента ListControl (формат) TypeName SelectionCondition для EntrySelectedBy для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должен существовать для записи в этом списке для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентов представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
