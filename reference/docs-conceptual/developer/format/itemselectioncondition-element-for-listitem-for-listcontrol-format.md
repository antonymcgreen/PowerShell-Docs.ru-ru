---
title: Элемент Итемселектионкондитион для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365193"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)

Определяет условие, которое должно существовать для использования этого элемента списка.

Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) элемент ListItems для Листентри Элемент ListControl (Format) ListItem для элементов ListItem для ListControl (Format) Итемселектионкондитион для элемента ListItem для ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ItemSelectionCondition`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Итемселектионкондитион для ListControl (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для элементов ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в строке представления списка.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Элемент ListItem для элементов ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Элемент PropertyName для Итемселектионкондитион для ListControl (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
