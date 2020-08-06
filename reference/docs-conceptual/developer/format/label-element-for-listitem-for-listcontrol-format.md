---
title: Элемент Label для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783642"
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

## <a name="remarks"></a>Примечания

Если метка не указана, отображается имя свойства или скрипт. Дополнительные сведения об использовании меток в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как добавить метку к строке.

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
