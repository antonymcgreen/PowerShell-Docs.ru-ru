---
title: Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363783"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) для Кустоментриес для элементов управления для представления (Format) Кустомитем элемента для Кустоментри для элементов управления для представления (Format) ExpressionBinding для Кустомитем элементов управления для представления (формат)

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
|[Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент Енумератеколлектион для ExpressionBinding элементов управления для представления (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, что элементы коллекций отображаются.|
|[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента управления.|
|[Элемент PropertyName для ExpressionBinding элементов управления для представления (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding элементов управления для представления (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также:

[Элемент Кустомитем для Кустоментри элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент Енумератеколлектион для ExpressionBinding элементов управления для представления (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент PropertyName для ExpressionBinding элементов управления для представления (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент ScriptBlock для ExpressionBinding элементов управления для представления (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
