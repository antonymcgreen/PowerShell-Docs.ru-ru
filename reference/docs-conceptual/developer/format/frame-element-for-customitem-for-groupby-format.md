---
title: Элемент Frame для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785767"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>Элемент Frame для элемента CustomItem для элемента GroupBy (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри для кустомитем для GroupBy (формат)

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
|[Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)](./firstlinehanging-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)](./firstlineindent-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Элемент LeftIndent для элемента Frame для элемента GroupBy (формат)](./leftindent-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Элемент ригхтиндент для Frame для GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Ригхтиндент, элемент|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Примечания

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-groupby-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-groupby-format.md) в одном и том же `Frame` элементе.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Элемент LeftIndent для элемента Frame для элемента GroupBy (формат)](./leftindent-element-for-frame-for-groupby-format.md)

[Элемент RightIndent для элемента Frame для элемента GroupBy (формат)](./rightindent-element-for-frame-for-groupby-format.md)

[Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
