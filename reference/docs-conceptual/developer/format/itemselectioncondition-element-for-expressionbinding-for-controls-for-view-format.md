---
title: Элемент Итемселектионкондитион для ExpressionBinding элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781211"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления в элементе "View" (Format) ошибка customcontrol для элемента управления элементов формат). элемент Кустоментри для Кустоментриес для элементов управления для элемента Кустомитем представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) ExpressionBinding для Кустомитем для элементов управления для представления (Format) ItemSelectionCondition элемента ExpressionBinding для элементов управления представления (формат)

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
|[Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Примечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также

[Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
