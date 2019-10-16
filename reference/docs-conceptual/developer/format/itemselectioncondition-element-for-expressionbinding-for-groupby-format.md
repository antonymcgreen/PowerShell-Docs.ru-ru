---
title: Элемент Итемселектионкондитион для ExpressionBinding для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365293"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Количество условий выбора, которое можно указать для элемента управления, не ограничено. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Кустомитем GroupBy для Кустоментри для GroupBy (Format) ExpressionBinding элемента для Кустомитем для элемента итемселектионкондитион в ExpressionBinding для GroupBy (Format)

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
|[Элемент PropertyName для Итемселектионкондитион для GroupBy (Format)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Итемселектионкондитион для GroupBy (Format)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для Кустомитем для GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)

[Элемент ExpressionBinding для Кустомитем для GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)
