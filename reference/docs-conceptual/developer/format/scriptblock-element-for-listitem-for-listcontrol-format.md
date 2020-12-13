---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)
description: Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664969"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)

Указывает скрипт, значение которого отображается в строке.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес в ListControl (Format) элемент ListItem для листентри для элемента списка элементов ListControl в ListControl (Format).

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="text-value"></a>Текстовое значение

Укажите скрипт, значение которого отображается в строке.

## <a name="remarks"></a>Комментарии

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

[Элемент PropertyName для элемента ListItem для элемента ListControl (формат)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem для элемента ListItems для элемента ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
