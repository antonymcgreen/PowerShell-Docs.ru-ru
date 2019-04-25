---
title: Элемент ScriptBlock для SelectionCondition для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb032dfc-9ef6-403c-b557-5858617e3483
caps.latest.revision: 6
ms.openlocfilehash: 102987970152420896a0c986f0973280ae209623
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064430"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)

Указывает сценарий, который активирует условие. При вычислении этого сценария для `true`условие выполняется, и используется определение. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента конфигурации (формат) SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат) Элемент ScriptBlock для SelectionCondition для элементов управления для конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|Определяет условие, которое должен существовать для распространенных определение элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

Условию выбора необходимо указать как минимум одно имя сценария или свойство для оценки, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
