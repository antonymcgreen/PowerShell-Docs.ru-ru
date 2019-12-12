---
title: Элемент Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364023"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomEntry`. Необходимо указать элементы, отображаемые в определении.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, которые используют определение представления пользовательского элемента управления или условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет элемент управления для определения пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментриес для ошибка customcontrol для представления (Format)](./customentries-element-for-customcontrol-for-view-format.md)|Предоставляет определения представления пользовательского элемента управления. В представлении пользовательского элемента управления должно быть указано одно или несколько определений.|

## <a name="remarks"></a>Замечания

В большинстве случаев для каждого представления пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент ошибка customcontrol для представления (формат)](./customcontrol-element-for-view-format.md)

[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Элемент Ентриселектедби для Кустоментри для представления (Format)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
