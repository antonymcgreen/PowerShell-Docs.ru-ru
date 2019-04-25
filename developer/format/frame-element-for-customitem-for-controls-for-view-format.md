---
title: Рамку элемента CustomItem для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065722"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)

Определяет способ отображения данных, таких как данные сдвига влево или вправо. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) кадра для CustomItem для элементов управления для представления (формат)

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
|[Элемент FirstLineHanging кадра элементов управления представления (формат)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка сдвигается влево.|
|[Элемент FirstLineIndent кадра элементов управления представления (формат)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка сдвигается вправо.|
|[Элемент LeftIndent кадра элементов управления представления (формат)](./leftindent-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от левого поля.|
|[Элемент RightIndent кадра элементов управления представления (формат)](./rightindent-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от правого поля.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Определяет, какие данные отображаются с помощью элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) элементы в одном `Frame` элемент.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging кадра элементов управления представления (формат)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[Элемент FirstLineIndent кадра элементов управления представления (формат)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[Элемент LeftIndent кадра элементов управления представления (формат)](./leftindent-element-for-frame-for-controls-for-view-format.md)

[Элемент RightIndent кадра элементов управления представления (формат)](./rightindent-element-for-frame-for-controls-for-view-format.md)

[Элемент CustomItem для CustomEntry для элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
