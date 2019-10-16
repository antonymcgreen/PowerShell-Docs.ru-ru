---
title: Элемент PropertyName для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01ae8cbe-acdc-4043-bd6e-1118a5691a55
caps.latest.revision: 12
ms.openlocfilehash: 405184f7bdbf1955f1df7766bf2723c244dcc27f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362383"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a>Элемент PropertyName для элемента ListItem для элемента ListControl (формат)

Указывает свойство .NET, значение которого отображается в списке.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) элемент списка ListItem (Format) элемент ListItem (Format) PropertyName элемент для ListItem (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Замечания

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

[Элемент ScriptBlock для ListItem для ListControl (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
