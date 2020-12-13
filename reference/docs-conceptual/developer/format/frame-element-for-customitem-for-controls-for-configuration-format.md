---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)
description: Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652247"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control for Configuration (Format) Кустоментриес элемента для ошибка customcontrol для элементов конфигурации (Format) Кустоментри для ошибка customcontrol for Controls для элемента конфигурации (Format) Кустомитем для кустоментри для элементов управления конфигурации (формат).

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomItem Element`|Обязательный элемент|
|[Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Комментарии

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) в одном и том же `Frame` элементе.

## <a name="see-also"></a>См. также:

[Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
