---
title: Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362923"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента конфигурации ExpressionBinding для элементов управления конфигурации (Format) Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)

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
|[Элемент PropertyName для Итемселектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Итемселектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для Итемселектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ScriptBlock для Итемселектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
