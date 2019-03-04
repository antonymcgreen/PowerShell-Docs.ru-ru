---
title: Элемент ItemSelectionCondition для ListItem для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861870"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a>Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)

Определяет условие, которое должен существовать для данного элемента списка для использования.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для элемента ListControl (формат) ListItems ListEntry для элемента ListControl (формат) ListItem ListItems для элемента ListControl (формат) ItemSelectionCondition ListItem для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для ItemSelectionCondition для ListControl (формат)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для ItemSelectionCondition для ListControl (формат)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для ListItems для ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Элемент ListItem для ListItems для ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Элемент PropertyName для ItemSelectionCondition для ListControl (формат)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[Элемент ScriptBlock для ItemSelectionCondition для ListControl (формат)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
