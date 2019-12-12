---
title: Элемент ScriptBlock для Итемсеклектионкондитион для элементов управления Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f7aec9-7b01-4370-84f4-1e58508a851f
caps.latest.revision: 6
ms.openlocfilehash: e92b2dfff07358132c480c47c34279e5365fe400
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362123"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Элемент ScriptBlock для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта для `true`выполняется условие, и используется элемент управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента конфигурации ExpressionBinding для элементов управления конфигурации (Format) Элемент Итемселектионкондитион для ExpressionBinding элементов управления для элемента конфигурации (Format) элемент ScriptBlock для Итемселектионкондитион для элементов управления конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Замечания

Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для Итемсеклектионкондитион элементов управления в конфигурации (Format)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
