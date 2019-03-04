---
title: TypeName-элемент для EntrySelectedBy для WideEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81a91c74-6229-4b64-aa2b-9123e8b7e9e5
caps.latest.revision: 11
ms.openlocfilehash: be35f6e9e2ad0b2d9a21a91c053aa0f70cafaf9c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862650"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a>Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)

Указывает тип .NET для определения. Определение используется в том случае, когда отображается этот объект.

Элемент (формат) ViewDefinitions элемент (формат) представление элемент (формат) элемент WideControl (формат) элемент WideEntries (формат) WideEntry элемент (формат) EntrySelectedBy элемент конфигурации для элемент TypeName WideEntry (формат) (WideEntry Формат)

## <a name="syntax"></a>Синтаксис

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Определяет типы .NET, использующих эту запись широкий или условие, которое должен существовать для данной записи для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.

## <a name="remarks"></a>Замечания

Каждая запись широкий необходимо указать один или несколько типов .NET, выбора или условию выбора, которые нужны для определения для использования.

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Элемент EntrySelectedBy для WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
