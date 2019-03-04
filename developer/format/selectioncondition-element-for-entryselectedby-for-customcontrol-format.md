---
title: Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 231e9c6d-09ec-4e68-80ee-0c8f7fe1b9f5
caps.latest.revision: 7
ms.openlocfilehash: 49e2c0cf09dfa55b535effcd431e980daf12fac3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858830"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)

Определяет условие, которое должен существовать для определения элемента управления для использования. Этот элемент используется при определении представления пользовательского элемента управления.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) EntrySelectedBy для CustomEntry для пользовательский элемент управления для элемента представления (формат) SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)

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
|[Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|
|[Элемент SelectionSetName для SelectionCondition для пользовательского элемента управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[TypeName-элемент для SelectionCondition для пользовательский элемент управления для представления (формат)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для пользовательский элемент управления для представления (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.|

## <a name="remarks"></a>Замечания

При определении условию выбора, применяются следующие требования:

- Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент SelectionSetName для SelectionCondition для пользовательского элемента управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[TypeName-элемент для SelectionCondition для пользовательский элемент управления для представления (формат)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент EntrySelectedBy для CustomEntry для пользовательский элемент управления для представления (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
