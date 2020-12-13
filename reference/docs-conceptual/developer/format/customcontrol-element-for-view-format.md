---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomControl для элемента View (формат)
description: Элемент CustomControl для элемента View (формат)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655462"
---
# <a name="customcontrol-element-for-view-format"></a>Элемент CustomControl для элемента View (формат)

Определяет формат пользовательского элемента управления для представления.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ошибка customcontrol (Format)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomControl` элемента. Необходимо указать один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntries для элемента CustomControl для элемента View (формат)](./customentries-element-for-customcontrol-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения представления пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент View (формат)](./view-element-format.md)|Определяет представление, используемое для отображения одного или нескольких объектов .NET.|

## <a name="remarks"></a>Комментарии

В большинстве случаев для каждого представления элемента управления требуется только одно определение, но можно предоставить несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент CustomEntries для элемента CustomControl для элемента View (формат)](./customentries-element-for-customcontrol-for-view-format.md)

[Элемент View (формат)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
