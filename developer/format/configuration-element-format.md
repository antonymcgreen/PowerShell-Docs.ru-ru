---
title: Элемент конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856330"
---
# <a name="configuration-element-format"></a>Элемент Configuration (формат)

Представляет элемент верхнего уровня файла форматирования.

Элемент конфигурации

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

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Configuration` элемент. Этот элемент должен быть корневой элемент для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элементы управления элемент конфигурации (формат)](./controls-element-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет общие элементы управления, которые могут использоваться все представления файла форматирования.|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Необязательный элемент.<br /><br /> Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.|
|[Формат SelectionSets элемент](./selectionsets-element-format.md)|Необязательный элемент.<br /><br /> Определяет общие наборы объектов .NET, которые могут использоваться все представления файла форматирования.|
|[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)|Необязательный элемент.<br /><br /> Определяет представления для отображения объектов.|

### <a name="parent-elements"></a>Родительские элементы

Нет.

## <a name="remarks"></a>Замечания

Файлы форматирования определяют способ отображения объектов. В большинстве случаев это корневой элемент содержит [ViewDefinitions](./viewdefinitions-element-format.md) элемент, который определяет таблицы, список и широкие представления файла форматирования. Помимо определения представлений файл форматирования можно определить общие наборы выделения, параметры и элементы управления, которые могут использовать эти представления.

## <a name="see-also"></a>См. также

[Элементы управления элемент конфигурации (формат)](./controls-element-for-configuration-format.md)

[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)

[Элемент SelectionSets (формат)](./selectionsets-element-format.md)

[Элемент ViewDefinitions (формат)](./viewdefinitions-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
