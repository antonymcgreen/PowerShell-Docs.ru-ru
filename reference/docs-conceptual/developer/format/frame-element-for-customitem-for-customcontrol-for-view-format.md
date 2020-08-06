---
title: Элемент Frame для Кустомитем для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4864ea1a865f77c9de6e495d7e8296e81c19b366
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781449"
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

|Элемент|Description|
|-------------|-----------------|
|`CustomItem Element`|Обязательный элемент|
|[Фирстлинехангинг, элемент](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Фирстлинеиндент, элемент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Лефтиндент, элемент](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Ригхтиндент, элемент](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Description|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Remarks

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) в одном и том же `Frame` элементе.

## <a name="see-also"></a>См. также:

[Фирстлинехангинг, элемент](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Фирстлинеиндент, элемент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Лефтиндент, элемент](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[Ригхтиндент, элемент](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
