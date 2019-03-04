---
title: Рамку элемента CustomItem для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862980"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)

Определяет способ отображения данных, таких как данные сдвига влево или вправо. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для фрейма элемента конфигурации для CustomItem для элементов управления для конфигурации (формат)

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
|[Элемент FirstLineHanging для кадра для элементов управления для конфигурации (формат)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка данных сдвигается влево.|
|[Элемент FirstLineIndent для кадра для элементов управления для конфигурации (формат)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка данных сдвигается вправо.|
|[Элемент LeftIndent для кадра для элементов управления для конфигурации (формат)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от левого поля.|
|[Элемент RightIndent для кадра для элементов управления для конфигурации (формат)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от правого поля.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Определяет, какие данные отображаются с помощью элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) элементы в одном `Frame` элемент.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging для кадра для элементов управления для конфигурации (формат)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Элемент FirstLineIndent для кадра для элементов управления для конфигурации (формат)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент LeftIndent для кадра для элементов управления для конфигурации (формат)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент RightIndent для кадра для элементов управления для конфигурации (формат)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент CustomItem для CustomEntry для элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
