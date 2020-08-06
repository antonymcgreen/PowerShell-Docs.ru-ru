---
title: Элемент Итемселектионкондитион для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783625"
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

## <a name="remarks"></a>Примечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также

[Элемент ListItem для элемента ListItems для элемента ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
