---
title: Элемент ListItems для Листентри для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 03b89a3df2ab0498533d0c00f303f643e0039b25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781143"
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

## <a name="remarks"></a>Примечания

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

## <a name="see-also"></a>См. также

[Элемент ListEntry для элемента ListControl (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
