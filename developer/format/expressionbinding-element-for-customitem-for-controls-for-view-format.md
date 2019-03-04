---
title: Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858300"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат)

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
|[Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемент управления.|
|[Элемент EnumerateCollection для ExpressionBinding для элементов управления для представления (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, что отображаются элементы коллекции.|
|[Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного элемента управления для использования.|
|[Элемент PropertyName для ExpressionBinding для элементов управления для представления (формат)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding для элементов управления для представления (формат)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Определяет, какие данные отображаются с помощью элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также

[Элемент CustomItem для CustomEntry для элементов управления для представления (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент EnumerateCollection для ExpressionBinding для элементов управления для представления (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент PropertyName для ExpressionBinding для элементов управления для представления (формат)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент ScriptBlock для ExpressionBinding для элементов управления для представления (формат)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
