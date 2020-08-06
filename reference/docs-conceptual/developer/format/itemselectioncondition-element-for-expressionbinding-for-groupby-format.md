---
title: Элемент Итемселектионкондитион для ExpressionBinding для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a9b74f1882efc578f7d9ab27b8cd2f8a52833ab8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773442"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Количество условий выбора, которое можно указать для элемента управления, не ограничено. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри for GroupBy, ExpressionBinding для кустомитем для элемента GroupBy (Format) итемселектионкондитион для ExpressionBinding for GroupBy (формат)

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
|[Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Примечания

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)
