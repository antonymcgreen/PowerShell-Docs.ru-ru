---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)
description: Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655298"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри for GroupBy (Format) ExpressionBinding для кустомитем for GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomControl Element`|Необязательный элемент.<br /><br /> Определяет элемент управления, используемый этим элементом управления.|
|[Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент енумератеколлектион для ExpressionBinding для GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)|Необязательный элемент.<br /><br /> Указывает, что отображаются элементы коллекций.|
|[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента управления.|
|[Элемент PropertyName для элемента ExpressionBinding для элемента GroupBy (формат)](./propertyname-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для элемента ExpressionBinding для элемента GroupBy (формат)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|

## <a name="see-also"></a>См. также:

[Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент EnumerateCollection для элемента ExpressionBinding для элемента GroupBy (формат)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Элемент PropertyName для элемента ExpressionBinding для элемента GroupBy (формат)](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[Элемент ScriptBlock для элемента ExpressionBinding для элемента GroupBy (формат)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
