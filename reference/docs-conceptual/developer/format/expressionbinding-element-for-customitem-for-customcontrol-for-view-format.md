---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)
description: Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648198"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol для элемента Кустоментриес представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) кустомитем для кустоментри for ошибка customcontrol для представления (Format) ExpressionBinding для кустомитем для ошибка customcontrol для представления (формат).

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
|[Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент EnumerateCollection для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, что отображаются элементы коллекций.|
|[Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента управления.|
|[Элемент PropertyName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding для Кустомкустомконтрол для представления (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|

## <a name="remarks"></a>Комментарии

## <a name="see-also"></a>См. также:

[Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент EnumerateCollection для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Элемент PropertyName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
