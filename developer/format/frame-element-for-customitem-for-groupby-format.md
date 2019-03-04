---
title: Рамку элемента для CustomItem GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854850"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>Элемент Frame для элемента CustomItem для элемента GroupBy (формат)

Определяет способ отображения данных, таких как данные сдвига влево или вправо. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomItem Element`|Обязательный элемент|
|[Элемент FirstLineHanging для кадра для GroupBy (формат)](./firstlinehanging-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка данных сдвигается влево.|
|[Элемент FirstLineIndent для кадра для GroupBy (формат)](./firstlineindent-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка данных сдвигается вправо.|
|[Элемент LeftIndent для кадра для GroupBy (формат)](./leftindent-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от левого поля.|
|[Элемент RightIndent для кадра для GroupBy (формат)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent элемент|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от правого поля.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)|Определяет, какие данные отображаются с помощью элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) элементы в одном `Frame` элемент.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging для кадра для GroupBy (формат)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Элемент FirstLineIndent для кадра для GroupBy (формат)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Элемент LeftIndent для кадра для GroupBy (формат)](./leftindent-element-for-frame-for-groupby-format.md)

[Элемент RightIndent для кадра для GroupBy (формат)](./rightindent-element-for-frame-for-groupby-format.md)

[Элемент CustomItem для CustomEntry для GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
