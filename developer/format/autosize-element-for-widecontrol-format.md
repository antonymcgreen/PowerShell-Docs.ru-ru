---
title: AutoSize-элемент для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066929"
---
# <a name="autosize-element-for-widecontrol-format"></a>Элемент AutoSize для WideControl (формат)

Указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) Autosize элемент конфигурации для WideControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `AutoSize` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Большое (значение одно значение) определяет формат списка для представления.|

## <a name="remarks"></a>Замечания

При определении широкое представление, можно добавить `AutoSize` элемент или [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) элемент, но нельзя добавить одновременно.

Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

Пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>См. также

[ColumnNumber-элемент для WideControl (формат)](./columnnumber-element-for-widecontrol-format.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Элемент WideControl (формат)](./widecontrol-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
