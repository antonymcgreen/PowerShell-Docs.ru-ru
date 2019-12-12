---
title: Элемент Label для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365203"
---
# <a name="label-element-for-groupby-format"></a>Элемент Label для элемента GroupBy (формат)

Указывает метку, которая отображается при обнаружении новой группы.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента метки представления (Format) для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Label`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)|Определяет, как отображается новая группа объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите текст, который будет отображаться каждый раз, когда Windows PowerShell встречает новое значение свойства или скрипта.

## <a name="remarks"></a>Замечания

В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает новое значение, которое запускает группу, и добавляет пустую строку до и после группы.

## <a name="example"></a>Пример

В следующем примере показана метка для новой группы. Отображаемая метка будет выглядеть примерно так: `Service Type: NewValueofProperty`

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>См. также:

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
