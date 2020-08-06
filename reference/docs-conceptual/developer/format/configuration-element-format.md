---
title: Элемент Configuration (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 90be02f8e27c0bd391e01da1a08ecd8eeb29b84c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783846"
---
# <a name="configuration-element-format"></a>Элемент Configuration (формат)

Представляет элемент верхнего уровня файла форматирования.

Элемент настройки

## <a name="syntax"></a>Синтаксис

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Configuration` элемента. Этот элемент должен быть корневым элементом для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Description|
|-------------|-----------------|
|[Элемент Controls для элемента Configuration (формат)](./controls-element-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Необязательный элемент.<br /><br /> Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|
|[Формат элемента Селектионсетс](./selectionsets-element-format.md)|Необязательный элемент.<br /><br /> Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.|
|[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)|Необязательный элемент.<br /><br /> Определяет представления, используемые для отображения объектов.|

### <a name="parent-elements"></a>Родительские элементы

Нет.

## <a name="remarks"></a>Remarks

Файлы форматирования определяют, как отображаются объекты. В большинстве случаев этот корневой элемент содержит элемент [виевдефинитионс](./viewdefinitions-element-format.md) , определяющий таблицу, список и широкие представления файла форматирования. В дополнение к определениям представлений файл форматирования может определять стандартные наборы, параметры и элементы управления, которые могут использоваться этими представлениями.

## <a name="see-also"></a>См. также:

[Элемент Controls для элемента Configuration (формат)](./controls-element-for-configuration-format.md)

[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)

[Элемент SelectionSets (формат)](./selectionsets-element-format.md)

[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
