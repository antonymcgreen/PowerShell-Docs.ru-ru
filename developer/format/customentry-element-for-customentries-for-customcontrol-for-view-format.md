---
title: Элемент CustomEntry для CustomEntries для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861820"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a>Элемент CustomEntry для элемента CustomEntries для элемента CustomControl для элемента View (формат)

Предоставляет определение пользовательского элемента управления представления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемент. Необходимо указать элементы, отображаемые с помощью определения.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для представления (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, использующих определение представления пользовательского элемента управления или условие, которое должен существовать для данного определения для использования.|
|[Элемент CustomItem для CustomEntry для представления (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет элемент управления для определения пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntries для пользовательский элемент управления для представления (формат)](./customentries-element-for-customcontrol-for-view-format.md)|Предоставляет определения представления пользовательского элемента управления. Представление пользовательского элемента управления необходимо указать одно или несколько определений.|

## <a name="remarks"></a>Замечания

В большинстве случаев для каждого представления пользовательского элемента управления требуется только одно определение, но можно иметь несколько определений, если вы хотите использовать одинаковое представление для отображения различных объектов .NET. В таком случае можно задать отдельный определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент пользовательский элемент управления для представления (формат)](./customcontrol-element-for-view-format.md)

[Элемент CustomItem для CustomEntry для представления (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Элемент EntrySelectedBy для CustomEntry для представления (формат)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
