---
title: Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065926"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении представления пользовательского элемента управления.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)

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
|[Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемент управления.|
|[Элемент EnumerateCollection для ExpressionBinding для пользовательский элемент управления для представления (формат)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указано, что отображаются элементы коллекции.|
|[Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного элемента управления для использования.|
|[Элемент PropertyName для ExpressionBinding для пользовательский элемент управления для представления (формат)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для ExpressionBinding для CustomCustomControl для представления (формат)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также

[Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент EnumerateCollection для ExpressionBinding для пользовательский элемент управления для представления (формат)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Элемент PropertyName для ExpressionBinding для пользовательский элемент управления для представления (формат)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для ExpressionBinding для пользовательский элемент управления для представления (формат)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент CustomItem для CustomEntry для пользовательский элемент управления для представления (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
