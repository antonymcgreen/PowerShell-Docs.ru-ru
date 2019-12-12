---
title: Элемент Frame для элемента управления Кустомитем для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363653"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a>Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) Кустоментриес для элементов управления для элемента Controls представления (Format) Кустомитем для Кустоментри для элементов управления элемента Frame (формат) для кустомитем для элементов управления представления (формат)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Frame`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomItem Element`|Обязательный элемент|
|[Элемент Фирстлинехангинг рамки элементов управления представления (формат)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка смещается влево.|
|[Элемент Фирстлинеиндент рамки элементов управления представления (формат)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка смещается вправо.|
|[Элемент Лефтиндент рамки элементов управления представления (формат)](./leftindent-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Элемент Ригхтиндент рамки элементов управления представления (формат)](./rightindent-element-for-frame-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Замечания

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-view-format.md) в одном элементе `Frame`.

## <a name="see-also"></a>См. также:

[Элемент Фирстлинехангинг рамки элементов управления представления (формат)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[Элемент Фирстлинеиндент рамки элементов управления представления (формат)](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[Элемент Лефтиндент рамки элементов управления представления (формат)](./leftindent-element-for-frame-for-controls-for-view-format.md)

[Элемент Ригхтиндент рамки элементов управления представления (формат)](./rightindent-element-for-frame-for-controls-for-view-format.md)

[Элемент Кустомитем для Кустоментри элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
