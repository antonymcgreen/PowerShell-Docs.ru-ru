---
title: Элемент ScriptBlock для ListItem для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064583"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a>Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)

Указывает сценарий, значение которого отображается в строке.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для элемента ListControl (формат) ListItems ListEntry для элемента ListControl (формат) ListItem ListItems элемента ListControl (формат) ScriptBlock для ListItem для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)|Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, значение которого отображается в строке.

## <a name="remarks"></a>Замечания

Если этот элемент указан, нельзя указать [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) элемент.

Дополнительные сведения об указании скриптов в виде списка, см. в разделе [представление списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как задано свойство, значение которого отображается.

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a>См. также

[PropertyName элемент ListItem для ListControl (формат)](./propertyname-element-for-listitem-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Элемент ListItem для ListItems для ListControl (формат)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
