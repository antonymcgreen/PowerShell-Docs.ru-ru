---
title: Элемент ScriptBlock для ItemSelectionCondition для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855420"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)

Указывает сценарий, который активирует условие. При вычислении этого сценария для `true`условие выполняется, и используется элемент списка. Этот элемент используется при определении представления списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для элемента ListControl (формат) ListItems ListEntry для элемента ListControl (формат) ListItem ListItems для списка (формат) ItemSelectionCondition элемент Control для ListItem для элемента ListControl (формат) ScriptBlock для ItemSelectionCondition для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние и родительские элементы из `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition для ListItem для ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Определяет условие, которое должен существовать для данного элемента списка для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать `PropertyName` элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
