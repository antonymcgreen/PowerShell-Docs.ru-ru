---
title: Элемент ExpressionBinding для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368633"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Кустомитем GroupBy для Кустоментри для GroupBy (Format) ExpressionBinding элемента для Кустомитем для GroupBy (Format)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ExpressionBinding`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomControl Element`|Необязательный элемент.<br /><br /> Определяет элемент управления, используемый этим элементом управления.|
|[Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент енумератеколлектион для ExpressionBinding для GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)|Необязательный элемент.<br /><br /> Указывает, что отображаются элементы коллекций.|
|[Элемент Итемселектионкондитион для ExpressionBinding для GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента управления.|
|[Элемент PropertyName для ExpressionBinding для GroupBy (Format)](./propertyname-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding для GroupBy (Format)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри для GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|

## <a name="see-also"></a>См. также:

[Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[Элемент Итемселектионкондитион для ExpressionBinding для GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Элемент PropertyName для ExpressionBinding для GroupBy (Format)](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[Элемент ScriptBlock для ExpressionBinding для GroupBy (Format)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[Элемент Кустомитем для Кустоментри для GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
