---
title: Элемент ScriptBlock для ItemSelectionCondition для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 946cd2b5-ac37-4a13-bb49-29fbc70ec8d7
caps.latest.revision: 6
ms.openlocfilehash: 0c07ab0e5d04c4056a7e7215bfa55773bfccb41d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064481"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)

Указывает сценарий, который активирует условие. При вычислении этого сценария для `true`условие выполняется, и используется элемент управления. Этот элемент используется при определении представления пользовательского элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для элемента ItemSelectionCondition представления (формат) для привязки выражения для пользовательский элемент управления для элемента представления (формат) ScriptBlock для ItemSelectionCondition для Пользовательский элемент управления для представления (формат)

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
|[Элемент ItemSelectionCondition для привязки выражения для пользовательский элемент управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Определяет условие, которое должен существовать для данного элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Элемент PropertyName для ItemSelectionCondition для пользовательский элемент управления для представления (формат)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[Элемент ItemSelectionCondition для привязки выражения для пользовательский элемент управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
