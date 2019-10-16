---
title: Элемент Label для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362893"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Элемент Label для элемента ListItem для элемента ListControl (формат)

Задает метку, которая отображается слева от значения свойства или скрипта в строке.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для элемента ListControl (Format) для листентри в элементе ListControl ( Format) элемент ListItem для элементов ListItem для элемента ListControl (Format) Метки для ListItem для ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Label`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для элементов ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите метку, которая будет отображаться слева от значения свойства или скрипта.

## <a name="remarks"></a>Замечания

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
