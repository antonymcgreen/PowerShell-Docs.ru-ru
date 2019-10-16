---
title: Элемент ScriptBlock для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364813"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)

Указывает скрипт, значение которого отображается в строке.

Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) элемент ListItems для Листентри для ListControl (Format) элемент ListItem для элементов ListItem для ListControl (Format) элемент ScriptBlock для элемента ListItem для ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите скрипт, значение которого отображается в строке.

## <a name="remarks"></a>Замечания

Если этот элемент указан, нельзя указать элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .

Дополнительные сведения об указании скриптов в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как указать свойство, значение которого отображается.

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>См. также:

[Элемент PropertyName для ListItem для ListControl (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem для элементов ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
