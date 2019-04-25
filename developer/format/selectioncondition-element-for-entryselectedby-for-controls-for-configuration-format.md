---
title: Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075772"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)

Определяет условие, которое должен существовать для общего определения элемента управления для использования. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для элементов управления для Элемент конфигурации (формат) CustomEntry для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента конфигурации (формат) SelectionCondition для EntrySelectedBy для CustomEntry для Конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для SelectionCondition для элементов управления для конфигурации (формат)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для элементов управления для конфигурации (формат)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для элементов управления для конфигурации (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[TypeName-элемент для SelectionCondition для элементов управления для конфигурации (формат)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Определяет типы .NET, использующих эта запись общее определение элемента управления.|

## <a name="remarks"></a>Замечания

При определении условию выбора, должен следовать приведенным ниже рекомендациям:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент PropertyName для SelectionCondition для элементов управления для конфигурации (формат)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент ScriptBlock для SelectionCondition для элементов управления для конфигурации (формат)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент SelectionSetName для SelectionCondition для элементов управления для конфигурации (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[TypeName-элемент для SelectionCondition для элементов управления для конфигурации (формат)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
