---
title: ColumnNumber-элемент для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe9eb5f9-a193-41a4-ad47-a96ba3f8d7e3
caps.latest.revision: 8
ms.openlocfilehash: 49f501538b8f72777984a5e575b999866abcdebf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856230"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>Элемент ColumnNumber для WideControl (формат)

Указывает количество столбцов, отображаемых в широком представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) ColumnNumber элемент конфигурации для WideControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ColumnNumber` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Большое (значение одно значение) определяет формат списка для представления.|

## <a name="text-value"></a>Текстовое значение

Укажите положительное целое число.

## <a name="remarks"></a>Замечания

При определении широкое представление, можно добавить `AutoSize` элемент или `ColumnNumber` элемент, но нельзя добавить одновременно.

Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

Пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[AutoSize-элемент для WideControl (формат)](./autosize-element-for-widecontrol-format.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Широкое представление (Basic)](./wide-view-basic.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
