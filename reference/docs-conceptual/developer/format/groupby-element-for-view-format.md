---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент GroupBy для элемента View (формат)
description: Элемент GroupBy для элемента View (формат)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652103"
---
# <a name="groupby-element-for-view-format"></a>Элемент GroupBy для элемента View (формат)

Определяет, как отображается новая группа объектов. Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (формат)

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

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomControl для элемента GroupBy (формат)](./customcontrol-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет пользовательский элемент управления, отображающий новые группы.|
|[Элемент CustomControlName для элемента GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает имя элемента управления, используемого для вывода новой группы.|
|[Элемент Label для элемента GroupBy (формат)](./label-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает метку, которая отображается при обнаружении новой группы.|
|[Элемент PropertyName для элемента GroupBy (формат)](./propertyname-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает новую группу при изменении ее значения.|
|[Элемент ScriptBlock для элемента GroupBy (формат)](./scriptblock-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, запускающий новую группу при изменении ее значения.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, в котором отображается один или несколько объектов .NET.|

## <a name="remarks"></a>Комментарии

При определении того, как отображается новая группа объектов, необходимо указать свойство или скрипт, который будет запускать новую группу. Однако нельзя указать и то, и другое.

## <a name="see-also"></a>См. также:

[Элемент CustomControlName для элемента GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)

[Элемент Label для элемента GroupBy (формат)](./label-element-for-groupby-format.md)

[Элемент PropertyName для элемента GroupBy (формат)](./propertyname-element-for-groupby-format.md)

[Элемент ScriptBlock для элемента GroupBy (формат)](./scriptblock-element-for-groupby-format.md)

[Элемент View (формат)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
