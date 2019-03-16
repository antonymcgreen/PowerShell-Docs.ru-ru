---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057779"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Указывает сценарий, который активирует условие. При вычислении этого сценария для `true`условие выполняется, и используется элемент списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy ListEntry (формат) элемента ScriptBlock для SelectionCondition для EntrySelectedBy для ListEntry (формат)

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
|[Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Определяет условие, которое должен существовать для записи в этом списке для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

Условию выбора необходимо указать как минимум одно имя сценария или свойство для оценки, но нельзя указать одновременно. (Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).)

Дополнительные сведения о других компонентов представления списка, см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также

[Элемент ListEntry (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент PropertyName для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Представление списка](./creating-a-list-view.md)

[Определение условия, при использовании операции отчета или элемента](./defining-conditions-for-displaying-data.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
