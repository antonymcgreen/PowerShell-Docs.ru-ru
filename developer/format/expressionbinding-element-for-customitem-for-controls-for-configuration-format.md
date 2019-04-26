---
title: Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065954"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для элемента конфигурации ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)

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
|[Элемент CustomControlName для ExpressionBinding для элементов управления для конфигурации (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемент управления.|
|[Элемент EnumerateCollection для ExpressionBinding для элементов управления для конфигурации (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указано, что элементом управления отображаются элементы коллекции.|
|[Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для этого общего элемента управления для использования.|
|[Элемент PropertyName для ExpressionBinding для элементов управления для конфигурации (формат)](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, значение которого отображается с общего элемента управления.|
|[Элемент ScriptBlock для ExpressionBinding для элементов управления для конфигурации (формат)](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, значение которого отображается с общего элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также

[Элемент CustomItem для CustomEntry для элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
