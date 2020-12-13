---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Label для элемента ListItem для элемента ListControl (формат)
description: Элемент Label для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666660"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Элемент Label для элемента ListItem для элемента ListControl (формат)

Задает метку, которая отображается слева от значения свойства или скрипта в строке.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для элементов ListItem в ListControl (формат) для листентри (Format) элемент ListItem для элементов ListItem для ListControl (Format) элемент Label для элемента SPListItem для ListControl (Format).

## <a name="syntax"></a>Синтаксис

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для элемента ListItems для элемента ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите метку, которая будет отображаться слева от значения свойства или скрипта.

## <a name="remarks"></a>Комментарии

Если метка не указана, отображается имя свойства или скрипт. Дополнительные сведения об использовании меток в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как добавить метку к строке.

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
