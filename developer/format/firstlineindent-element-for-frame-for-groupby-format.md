---
title: Элемент FirstLineIndent для кадра для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065858"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a>Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)

Указывает количество символов, первая строка данных сдвигается вправо. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для элемента FirstLineIndent GroupBy (формат) для кадра для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineIndent` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Frame для CustomItem для GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)|Определяет способ отображения данных, таких как данные сдвига влево или вправо.|

## <a name="text-value"></a>Текстовое значение

Укажите количество символов, которые нужно сместить первая строка данных.

## <a name="remarks"></a>Замечания

Если этот элемент указан, нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) элемент.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging для кадра для GroupBy (формат)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Элемент Frame для CustomItem для GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
