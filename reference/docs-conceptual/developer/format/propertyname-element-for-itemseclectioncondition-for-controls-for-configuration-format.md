---
title: Элемент PropertyName для Итемсеклектионкондитион элементов управления в конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8ab181-c559-492e-a0cf-299e381fdcc3
caps.latest.revision: 6
ms.openlocfilehash: ce25789bdfc2679372ca9e42f99dcc6a30ae2def
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362533"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Элемент PropertyName для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)

Указывает свойство .NET, которое запускает условие. Если это свойство имеется или если оно имеет значение `true`, условие выполняется, и используется элемент управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента конфигурации ExpressionBinding для элементов управления конфигурации (Format) Элемент Итемселектионкондитион для ExpressionBinding элементов управления для элемента конфигурации (Format) PropertyName для Итемсеклектионкондитион для элементов управления в конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое запускает условие.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент ScriptBlock для Итемсеклектионкондитион элементов управления в конфигурации (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
