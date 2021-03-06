---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента View (формат)
description: Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента View (формат)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652372"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента View (формат)

Предоставляет определения для элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления элементов

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomEntries` элемента. Максимальное количество дочерних элементов, которое можно указать, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Определяет элемент управления, используемый представлением.|

## <a name="remarks"></a>Комментарии

В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном `CustomEntry` элементе. Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
