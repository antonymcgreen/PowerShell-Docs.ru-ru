---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntry для элемента CustomEntries для элемента CustomControl для элемента View (формат)
description: Элемент CustomEntry для элемента CustomEntries для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: ff481f13e6f16267bdda4c3053faebc96d9a6d3a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646056"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a>Элемент CustomEntry для элемента CustomEntries для элемента CustomControl для элемента View (формат)

Предоставляет определение представления пользовательского элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для Кустоментри представления (формат) Кустоментриес для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемента. Необходимо указать элементы, отображаемые в определении.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, которые используют определение представления пользовательского элемента управления или условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет элемент управления для определения пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntries для элемента CustomControl для элемента View (формат)](./customentries-element-for-customcontrol-for-view-format.md)|Предоставляет определения представления пользовательского элемента управления. В представлении пользовательского элемента управления должно быть указано одно или несколько определений.|

## <a name="remarks"></a>Комментарии

В большинстве случаев для каждого представления пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент CustomControl для элемента View (формат)](./customcontrol-element-for-view-format.md)

[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
