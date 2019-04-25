---
title: Элемент FirstLineHanging для кадра для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cdcf66e-96a5-47b5-9269-b4330bde29f2
caps.latest.revision: 6
ms.openlocfilehash: 08db1f2d89c3fe6c1e9a5a522de3071425042c3f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065841"
---
# <a name="firstlinehanging-element-for-frame-for-groupby-format"></a>Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)

Указывает количество символов, первая строка данных сдвигается влево. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для элемента FirstLineHanging GroupBy (формат) для кадра для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineHanging` элемент.

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

Если этот элемент указан, нельзя указать [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) элемент.

## <a name="see-also"></a>См. также

[Элемент FirstLineIndent для кадра для GroupBy (формат)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Элемент Frame для CustomItem для GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
