---
title: Элемент PropertyName для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362523"
---
# <a name="propertyname-element-for-groupby-format"></a>Элемент PropertyName для элемента GroupBy (формат)

Указывает свойство .NET, которое запускает новую группу при изменении ее значения.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (Format) PropertyName для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)|Определяет, как отображается группа объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Замечания

Windows PowerShell запускает новую группу при каждом изменении значения этого свойства.

Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) для запуска новой группы.

## <a name="example"></a>Пример

В следующем примере показано, как запустить новую группу при изменении значения свойства.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>См. также:

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Элемент ScriptBlock для GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
