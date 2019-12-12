---
title: Элемент ListItem для элементов ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365133"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>Элемент ListItem для элемента ListItems для элемента ListControl (формат)

Определяет свойство или скрипт, значение которого отображается в строке представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемента для ListControl (Format) элемент ListItems для ListControl (Format) Элемент ListItem для элемента ListControl (Format)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListItem`. Можно указать только одно свойство или скрипт.

### <a name="attributes"></a>Атрибуты

Нет

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент FormatString для ListItem для ListControl (Format)](./formatstring-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает строку формата, определяющую способ отображения значения свойства или скрипта.|
|[Элемент Итемселектионкондитион для ListItem для ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента списка.|
|[Элемент Label для ListItem для ListControl (Format)](./label-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент<br /><br /> Задает метку, которая отображается слева от значения свойства или скрипта в строке.|
|[Элемент PropertyName для ListItem для ListControl (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается в строке.|
|[Элемент ScriptBlock для ListItem для ListControl (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, значение которого отображается в строке.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItems для элемента управления "список" (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)|Определяет свойства и скрипты, значения которых отображаются в представлении списка.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны XML-элементы, определяющие три строки представления списка. В первых двух строках отображается значение свойства .NET, а в последней строке — значение, созданное сценарием.

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

## <a name="see-also"></a>См. также:

[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Элемент FormatString для ListItem (Format)](./formatstring-element-for-listitem-for-listcontrol-format.md)

[Элемент Label для ListItem (Format)](./label-element-for-listitem-for-listcontrol-format.md)

[Элемент PropertyName для ListItem (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Элемент ScriptBlock для ListItem (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
