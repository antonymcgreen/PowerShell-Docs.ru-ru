---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)
description: Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665997"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется представление. Этот элемент используется при определении представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент для ListControl (Format) элементов ListItem для листентри для ListControl (Format) элемент ListItem для элемента ListItem для ListControl (формат) Итемселектионкондитион для элемента ListItem для листконтролс в ItemSelectionCondition (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Комментарии

Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент ScriptBlock для Итемселектионкондитион для Листиконтрол (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
