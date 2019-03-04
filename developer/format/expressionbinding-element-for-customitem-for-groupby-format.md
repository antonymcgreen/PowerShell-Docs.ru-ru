---
title: Элемент ExpressionBinding для CustomItem для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854930"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента ExpressionBinding GroupBy (формат) для CustomItem для GroupBy (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomControl Element`|Необязательный элемент.<br /><br /> Определяет элемент управления, который используется в этом элементе управления.|
|[Элемент CustomControlName для ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемент управления.|
|[Элемент EnumerateCollection для ExpressionBinding для GroupBy (формат)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection-элемент для ExpressionBinding для GroupBy (формат)|Необязательный элемент.<br /><br /> Указано, что отображаются элементы коллекции.|
|[Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного элемента управления для использования.|
|[Элемент PropertyName для ExpressionBinding для GroupBy (формат)](./propertyname-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding для GroupBy (формат)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.|

## <a name="see-also"></a>См. также

[Элемент CustomControlName для ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент EnumerateCollection для ExpressionBinding для GroupBy (формат)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Элемент PropertyName для ExpressionBinding для GroupBy (формат)](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[Элемент ScriptBlock для ExpressionBinding для GroupBy (формат)](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[Элемент CustomItem для CustomEntry для GroupBy (формат)](./customitem-element-for-customentry-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
