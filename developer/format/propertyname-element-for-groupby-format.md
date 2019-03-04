---
title: Элемент PropertyName для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863270"
---
# <a name="propertyname-element-for-groupby-format"></a>Элемент PropertyName для элемента GroupBy (формат)

Задает свойство .NET, которая запускает новую группу, при каждом изменении его значения.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) PropertyName для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)|Определяет порядок отображения группы объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Замечания

Windows PowerShell запускает новую группу, при каждом изменении значения этого свойства.

Если этот элемент указан, нельзя указать [ScriptBlock](./scriptblock-element-for-groupby-format.md) элемент, чтобы начать новую группу.

## <a name="example"></a>Пример

Приведенный ниже показано, как начать новую группу, при изменении значения свойства.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Например, полный файл форматирования, который содержит этот элемент, см. в разделе [широкое представление (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>См. также

[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

[Элемент ScriptBlock для GroupBy (формат)](./scriptblock-element-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
