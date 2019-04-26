---
title: Элемент ListItem для ListItems для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065773"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>Элемент ListItem для элемента ListItems для элемента ListControl (формат)

Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListEntry ListControl (формат) для элемента ListControl (формат) ListItems ListControl (формат) ListItem для элемента ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListItem` элемент. Можно указать только одно свойство или скрипт.

### <a name="attributes"></a>Атрибуты

Нет

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент FormatString для ListItem для ListControl (формат)](./formatstring-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает строку формата, который определяет способ отображения значения свойства или скрипт.|
|[Элемент ItemSelectionCondition для ListItem для ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного элемента списка для использования.|
|[Элемент Label для ListItem для ListControl (формат)](./label-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент<br /><br /> Указывает метку, которая отображается слева от значения свойства или сценарий, в строке.|
|[PropertyName элемент ListItem для ListControl (формат)](./propertyname-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, значение которого отображается в строке.|
|[Элемент ScriptBlock для ListItem для ListControl (формат)](./scriptblock-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, значение которого отображается в строке.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[ListItems элемент управления "список" (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)|Определяет свойства и скрипты, значения которых отображаются в представлении списка.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны элементы XML, которые определяют три строки в представлении списка. Первые две строки отображения значения свойства .NET, а последняя строка выводит значение, созданные с помощью сценария.

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a>См. также

[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Элемент FormatString для ListItem (формат)](./formatstring-element-for-listitem-for-listcontrol-format.md)

[Элемент Label для ListItem (формат)](./label-element-for-listitem-for-listcontrol-format.md)

[PropertyName элемент ListItem (формат)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Элемент ScriptBlock для ListItem (формат)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
