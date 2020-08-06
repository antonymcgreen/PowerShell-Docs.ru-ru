---
title: Элемент Frame для Кустомитем элементов управления в конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781483"
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

## <a name="remarks"></a>Примечания

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) в одном и том же `Frame` элементе.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
