---
title: Элемент Итемселектионкондитион для ExpressionBinding элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c15014-2440-410d-b02d-b7f1a49240a0
caps.latest.revision: 7
ms.openlocfilehash: 80f375c53c205c793600655fa6031d114871618e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362943"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) для Кустоментриес для элементов управления для представления (Format) Кустомитем элемента для Кустоментри для элементов управления для представления (Format) ExpressionBinding для Кустомитем элементов управления для представления (формат) Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)

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
|[Элемент PropertyName для Итемселектионкондитион элементов управления для представления (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Итемселектионкондитион элементов управления для представления (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для Итемселектионкондитион элементов управления для представления (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ScriptBlock для Итемселектионкондитион элементов управления для представления (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
