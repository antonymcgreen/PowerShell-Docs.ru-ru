---
title: Элемент GroupBy для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2f9071a3ebbc7cc2ccb7721dd518e82723e9cc4e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781432"
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

## <a name="remarks"></a>Примечания

При определении того, как отображается новая группа объектов, необходимо указать свойство или скрипт, который будет запускать новую группу. Однако нельзя указать и то, и другое.

## <a name="see-also"></a>См. также

[Элемент CustomControlName для элемента GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)

[Элемент Label для элемента GroupBy (формат)](./label-element-for-groupby-format.md)

[Элемент PropertyName для элемента GroupBy (формат)](./propertyname-element-for-groupby-format.md)

[Элемент ScriptBlock для элемента GroupBy (формат)](./scriptblock-element-for-groupby-format.md)

[Элемент View (формат)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
