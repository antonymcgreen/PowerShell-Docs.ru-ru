---
title: Элемент Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363503"
---
# <a name="configuration-element-format"></a>Элемент Configuration (формат)

Представляет элемент верхнего уровня файла форматирования.

Элемент Configuration

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Configuration`. Этот элемент должен быть корневым элементом для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Controls для конфигурации (Format)](./controls-element-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.|
|[Элемент Дефаултсеттингс (Format)](./defaultsettings-element-format.md)|Необязательный элемент.<br /><br /> Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|
|[Формат элемента Селектионсетс](./selectionsets-element-format.md)|Необязательный элемент.<br /><br /> Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.|
|[Элемент Виевдефинитионс (Format)](./viewdefinitions-element-format.md)|Необязательный элемент.<br /><br /> Определяет представления, используемые для отображения объектов.|

### <a name="parent-elements"></a>Родительские элементы

Нет.

## <a name="remarks"></a>Замечания

Файлы форматирования определяют, как отображаются объекты. В большинстве случаев этот корневой элемент содержит элемент [виевдефинитионс](./viewdefinitions-element-format.md) , определяющий таблицу, список и широкие представления файла форматирования. В дополнение к определениям представлений файл форматирования может определять стандартные наборы, параметры и элементы управления, которые могут использоваться этими представлениями.

## <a name="see-also"></a>См. также:

[Элемент Controls для конфигурации (Format)](./controls-element-for-configuration-format.md)

[Элемент Дефаултсеттингс (Format)](./defaultsettings-element-format.md)

[Элемент Селектионсетс (Format)](./selectionsets-element-format.md)

[Элемент Виевдефинитионс (Format)](./viewdefinitions-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
