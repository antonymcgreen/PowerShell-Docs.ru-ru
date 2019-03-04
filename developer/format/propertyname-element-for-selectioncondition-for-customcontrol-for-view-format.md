---
title: Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48a417-2083-46d4-ac38-16c12e65b6b9
caps.latest.revision: 7
ms.openlocfilehash: e08037d5d051d3be51e90193c7e87cc2e738f78a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860970"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)

Задает свойство .NET, которое активирует условие. Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется определение. Этот элемент используется при определении представления пользовательского элемента управления.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) EntrySelectedBy для CustomEntry для пользовательский элемент управления для элемента представления (формат) SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат) PropertyName Элемент для SelectionCondition для пользовательский элемент управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Определяет условие, которое должен существовать для определение элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Замечания

Условию выбора необходимо указать имя как минимум одно свойство или сценария, но нельзя указать одновременно. Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
