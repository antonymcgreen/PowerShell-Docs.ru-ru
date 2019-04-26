---
title: Элемент ListItems для ListEntry для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c1da6d-acc7-4fe8-9e7d-6dcddc2787cd
caps.latest.revision: 9
ms.openlocfilehash: c25f18489d9c7abd8889758499dbbacd6ee29304
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065246"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>Элемент ListItems для элемента ListEntry для элемента ListControl (формат)

Определяет свойства и скрипты, значения которых отображаются в строках представления "list".

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемент конфигурации для списка (формат) ListEntry элемент для элемента ListControl (формат) ListItems ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListItems` элемент. Нет ограничений на количество дочерних элементов, которые могут быть указаны. Порядок дочерних элементов определяет порядок отображения значений в представлении списка.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипта, значение которого отображается в представлении списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListEntry для ListControl (формат)](./listentry-element-for-listcontrol-format.md)|Предоставляет определение представления "list".|

## <a name="remarks"></a>Замечания

Дополнительные сведения об этом типе представления, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны элементы XML, которые определяют три строки в представлении списка.

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

[Элемент ListEntry для ListControl (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент ListItem для ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
