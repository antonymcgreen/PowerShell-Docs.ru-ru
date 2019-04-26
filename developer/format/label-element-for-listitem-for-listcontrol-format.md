---
title: Этикетка элемент ListItem для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065433"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>Элемент Label для элемента ListItem для элемента ListControl (формат)

Указывает метку, которая отображается слева от значения свойства или сценарий, в строке.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListItems ListControl (формат) для ListEntry элемента ListControl ( Элемент ListItem Format) для ListItems для метки элемента ListControl (формат) ListItem для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Label` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для ListItems для ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.|

## <a name="text-value"></a>Текстовое значение

Укажите метку, который будет отображаться слева от значения свойства или скрипт.

## <a name="remarks"></a>Замечания

Если метка не указана, отображается имя свойства или скрипт. Дополнительные сведения об использовании меток в представлении списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

Приведенный ниже показано, как добавить метку для строки.

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>См. также

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
