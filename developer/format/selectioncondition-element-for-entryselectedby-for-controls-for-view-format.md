---
title: Элемент SelectionCondition для EntrySelectedBy для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858020"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)

Определяет условие, которое должен существовать для определение элемента управления для использования. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элементов управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента представления (формат) SelectionCondition для EntrySelectedBy для элементов управления (представление Формат)

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
|[Элемент PropertyName для SelectionCondition для элементов управления для представления (формат)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для элементов управления для представления (формат)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для элементов управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[TypeName-элемент для SelectionCondition для элементов управления для представления (формат)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.|

## <a name="remarks"></a>Замечания

При определении условию выбора, применяются следующие требования:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент PropertyName для SelectionCondition для элементов управления для представления (формат)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент ScriptBlock для SelectionCondition для элементов управления для представления (формат)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент SelectionSetName для SelectionCondition для элементов управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[TypeName-элемент для SelectionCondition для элементов управления для представления (формат)](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
