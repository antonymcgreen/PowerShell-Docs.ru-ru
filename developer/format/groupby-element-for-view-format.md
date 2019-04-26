---
title: GroupBy-элемент для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065549"
---
# <a name="groupby-element-for-view-format"></a>Элемент GroupBy для элемента View (формат)

Определяет порядок отображения группу объектов. Этот элемент используется при определении таблицы, список, представление ширину или пользовательского элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Атрибуты, дочерние и родительские элементы в следующих разделах.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Пользовательский элемент управления-элемент для GroupBy (формат)](./customcontrol-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет пользовательский элемент управления, отображающие новые группы.|
|[Элемент CustomControlName для GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает имя элемента управления, который используется для отображения новой группы.|
|[Элемент Label для GroupBy (формат)](./label-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает метку, которая отображается при обнаружении новой группы.|
|[Элемент PropertyName для GroupBy (формат)](./propertyname-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, то начинается группу при каждом изменении его значения.|
|[Элемент ScriptBlock для GroupBy (формат)](./scriptblock-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который запускает новую группу, при каждом изменении его значения.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое отображает один или несколько объектов .NET.|

## <a name="remarks"></a>Замечания

При определении, как отображается группу объектов, необходимо указать свойство или скрипт, который запустит группы. Тем не менее нельзя одновременно задать.

## <a name="see-also"></a>См. также

[Элемент CustomControlName для GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)

[Элемент Label для GroupBy (формат)](./label-element-for-groupby-format.md)

[Элемент PropertyName для GroupBy (формат)](./propertyname-element-for-groupby-format.md)

[Элемент ScriptBlock для GroupBy (формат)](./scriptblock-element-for-groupby-format.md)

[Элемент представления (формат)](./view-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
