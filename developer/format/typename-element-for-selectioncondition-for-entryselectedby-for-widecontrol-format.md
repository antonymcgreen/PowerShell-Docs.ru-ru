---
title: TypeName-элемент для SelectionCondition для EntrySelectedBy для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d6d43fa-c900-4e2f-952d-deccd584236f
caps.latest.revision: 11
ms.openlocfilehash: 0d7bbfd8be3bf2bd1af75a45ca4db016dfb6bff6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857960"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a>Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)

Указывает тип .NET, который активирует условие. При наличии этого типа используется определение.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy WideEntry (формат) имя типа элемента для SelectionCondition для EntrySelectedBy для WideEntry (формат)

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
|[Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Определяет условие, которое должен существовать для данной записи, расширенный для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

Условию выбора можно указать тип .NET или выбор задать, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Creatng широкое представление](./creating-a-wide-view.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
