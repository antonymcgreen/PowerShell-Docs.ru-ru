---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)
description: Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667816"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)

Определяет условие, которое должно существовать для использования этого элемента списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес для ListControl (Format) элемент ListItem для листентри для элементов ListItem в ListControl (формат) ListControl для элемента SPListItem (формат) элемент для элементов ListItem для итемселектионкондитион (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для элемента ListItems для элемента ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="remarks"></a>Комментарии

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Элемент ListItem для элемента ListItems для элемента ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
