---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ListItems для элемента ListEntry для элемента ListControl (формат)
description: Элемент ListItems для элемента ListEntry для элемента ListControl (формат)
ms.openlocfilehash: 1553c81bc559020223a3c1fea10336baf017c9a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666541"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>Элемент ListItems для элемента ListEntry для элемента ListControl (формат)

Определяет свойства и скрипты, значения которых отображаются в строках представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент для элемента управления списка (Format) Листентри для элемента в ListControl (Format) для ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListItems` элемента. Количество дочерних элементов, которые можно указать, не ограничено. Порядок дочерних элементов определяет порядок отображения значений в представлении списка.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипт, значение которого отображается в представлении списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListEntry для элемента ListControl (формат)](./listentry-element-for-listcontrol-format.md)|Предоставляет определение представления списка.|

## <a name="remarks"></a>Комментарии

Дополнительные сведения об этом типе представления см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны XML-элементы, определяющие три строки представления списка.

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a>См. также:

[Элемент ListEntry для элемента ListControl (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
