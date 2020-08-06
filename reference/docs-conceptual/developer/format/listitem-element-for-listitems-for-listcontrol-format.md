---
title: Элемент ListItem для элементов ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e72a887e8bd1f93bacb663e3079eeaec34bdfa51
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785682"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a>Элемент ListItem для элемента ListItems для элемента ListControl (формат)

Определяет свойство или скрипт, значение которого отображается в строке представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для ListControl (Format) элемент списка элементов для ListControl (Format) для элемента (формат)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListItem` элемента. Можно указать только одно свойство или скрипт.

### <a name="attributes"></a>Атрибуты

Нет

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент FormatString для ListItem для ListControl (Format)](./formatstring-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает строку формата, определяющую способ отображения значения свойства или скрипта.|
|[Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента списка.|
|[Элемент Label для элемента ListItem для элемента ListControl (формат)](./label-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент<br /><br /> Задает метку, которая отображается слева от значения свойства или скрипта в строке.|
|[Элемент PropertyName для элемента ListItem для элемента ListControl (формат)](./propertyname-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается в строке.|
|[Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)](./scriptblock-element-for-listitem-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, значение которого отображается в строке.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItems для элемента управления "список" (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)|Определяет свойства и скрипты, значения которых отображаются в представлении списка.|

## <a name="remarks"></a>Примечания

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

## <a name="see-also"></a>См. также

[Элемент ListItems (формат)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Элемент FormatString для ListItem (Format)](./formatstring-element-for-listitem-for-listcontrol-format.md)

[Элемент Label для ListItem (Format)](./label-element-for-listitem-for-listcontrol-format.md)

[Элемент PropertyName для ListItem (Format)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Элемент ScriptBlock для ListItem (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
