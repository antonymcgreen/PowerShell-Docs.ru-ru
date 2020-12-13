---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ListItem для элемента ListControl (формат)
description: Элемент PropertyName для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665980"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>Элемент PropertyName для элемента ListItem для элемента ListControl (формат)

Указывает свойство .NET, значение которого отображается в списке.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) элемент списка ListItem (Format) элемент "PropertyName" (Format) ИмяСвойства Element для ListItem (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Комментарии

Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .

В дополнение к отображению значения свойства можно также указать метку для значения или строку формата, которую можно использовать для изменения отображения значения. Дополнительные сведения об указании данных в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать метку и свойство, значение которого отображается.

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a>См. также:

[Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
