---
title: Метка элемента для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862400"
---
# <a name="label-element-for-groupby-format"></a>Элемент Label для элемента GroupBy (формат)

Указывает метку, которая отображается при обнаружении новой группы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) метки для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Label` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)|Определяет порядок отображения группу объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите текст, который отображается каждый раз, когда Windows PowerShell обнаруживает новое свойство или значение скрипта.

## <a name="remarks"></a>Замечания

В дополнение к текст, заданный этим элементом Windows PowerShell отображает новое значение, которое запускает группе и добавляет пустой строки до и после группы.

## <a name="example"></a>Пример

В следующем примере показано метки для новой группы. Отображаемой метки будет выглядеть примерно следующим образом: `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Например, полный файл форматирования, который содержит этот элемент, см. в разделе [широкое представление (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>См. также

[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
