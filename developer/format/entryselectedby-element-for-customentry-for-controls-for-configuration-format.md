---
title: Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066300"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)

Определяет типы .NET, использующих определение общего элемента управления или условие, которое должен существовать для данного элемента управления для использования. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для распространенных определение элемента управления для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение стандартного элемента управления.|
|[TypeName-элемент для EntrySelectedBy для элементов управления для конфигурации (формат)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение стандартного элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение стандартного элемента управления.|

## <a name="remarks"></a>Замечания

Как минимум каждое определение должен иметь по крайней мере один тип .NET, выбора или выделение условие, заданное. Не ограничено максимальное число типов, выбор наборов или условий выборки, которые можно задать.

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[TypeName-элемент для EntrySelectedBy для элементов управления для конфигурации (формат)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
