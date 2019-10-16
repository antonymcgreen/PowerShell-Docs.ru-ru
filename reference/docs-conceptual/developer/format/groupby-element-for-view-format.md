---
title: Элемент GroupBy для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363633"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет пользовательский элемент управления, отображающий новые группы.|
|[Элемент Кустомконтролнаме для GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает имя элемента управления, используемого для вывода новой группы.|
|[Элемент Label для GroupBy (Format)](./label-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает метку, которая отображается при обнаружении новой группы.|
|[Элемент PropertyName для GroupBy (Format)](./propertyname-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает новую группу при изменении ее значения.|
|[Элемент ScriptBlock для GroupBy (Format)](./scriptblock-element-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, запускающий новую группу при изменении ее значения.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, в котором отображается один или несколько объектов .NET.|

## <a name="remarks"></a>Замечания

При определении того, как отображается новая группа объектов, необходимо указать свойство или скрипт, который будет запускать новую группу. Однако нельзя указать и то, и другое.

## <a name="see-also"></a>См. также:

[Элемент Кустомконтролнаме для GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

[Элемент Label для GroupBy (Format)](./label-element-for-groupby-format.md)

[Элемент PropertyName для GroupBy (Format)](./propertyname-element-for-groupby-format.md)

[Элемент ScriptBlock для GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[View, элемент (Format)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
