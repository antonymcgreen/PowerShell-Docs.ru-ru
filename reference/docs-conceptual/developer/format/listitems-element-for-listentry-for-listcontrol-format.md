---
title: Элемент ListItems для Листентри для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c1da6d-acc7-4fe8-9e7d-6dcddc2787cd
caps.latest.revision: 9
ms.openlocfilehash: c25f18489d9c7abd8889758499dbbacd6ee29304
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362743"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>Элемент ListItems для элемента ListEntry для элемента ListControl (формат)

Определяет свойства и скрипты, значения которых отображаются в строках представления списка.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент для элемента управления списка (Format) Листентри для элемента в ListControl (Format) для ListControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListItems`. Количество дочерних элементов, которые можно указать, не ограничено. Порядок дочерних элементов определяет порядок отображения значений в представлении списка.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипт, значение которого отображается в представлении списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Листентри для ListControl (Format)](./listentry-element-for-listcontrol-format.md)|Предоставляет определение представления списка.|

## <a name="remarks"></a>Замечания

Дополнительные сведения об этом типе представления см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В этом примере показаны XML-элементы, определяющие три строки представления списка.

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a>См. также:

[Элемент Листентри для ListControl (Format)](./listentry-element-for-listcontrol-format.md)

[Элемент ListItem для ListControl (Format)](./listitem-element-for-listitems-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
