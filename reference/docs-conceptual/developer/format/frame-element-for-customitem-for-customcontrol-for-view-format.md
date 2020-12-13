---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)
description: Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652180"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления для кустоментриес для представления (Format) кустомитем для кустоментри для кустомконтролвиев (Format) элемент Frame для CustomItem for ошибка customcontrol для представления (формат)

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
|[Фирстлинехангинг, элемент](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Фирстлинеиндент, элемент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Лефтиндент, элемент](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Ригхтиндент, элемент](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Комментарии

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) в одном и том же `Frame` элементе.

## <a name="see-also"></a>См. также:

[Фирстлинехангинг, элемент](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Фирстлинеиндент, элемент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Лефтиндент, элемент](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[Ригхтиндент, элемент](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
