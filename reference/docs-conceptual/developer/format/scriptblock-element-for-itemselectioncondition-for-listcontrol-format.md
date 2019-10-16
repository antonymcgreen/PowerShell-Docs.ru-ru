---
title: Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362103"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта в `true` условие выполняется, и используется элемент списка. Этот элемент используется при определении представления списка.

Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) элемент ListItems для Листентри для элемента ListControl (Format) ListItem для элементов управления List (Format) Итемселектионкондитион для элемента ListItem в элементе ScriptBlock для ListControl (Format) для Итемселектионкондитион для ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `ScriptBlock`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Итемселектионкондитион для ListItem для ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Определяет условие, которое должно существовать для использования этого элемента списка.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать элемент `PropertyName` при определении условия выбора.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
