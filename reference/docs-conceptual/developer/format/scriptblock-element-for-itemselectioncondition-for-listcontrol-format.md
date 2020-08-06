---
title: Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 38dc952bfadd6aed24bae8cbef05adcd22e61dd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787637"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта выполняется `true` условие, и используется элемент списка. Этот элемент используется при определении представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес для ListControl (Format) элемент ListItem для листентри для элемента списка элементов управления "список" (формат) ListControl для элемента SPListItem в итемселектионкондитион (Format) элемент ScriptBlock для ListControl в ItemSelectionCondition (Format).

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|Определяет условие, которое должно существовать для использования этого элемента списка.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

Если используется этот элемент, нельзя указать `PropertyName` элемент при определении условия выбора.

## <a name="see-also"></a>См. также

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
