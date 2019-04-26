---
title: Элемент пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066674"
---
# <a name="customcontrol-element-for-view-format"></a>Элемент CustomControl для элемента View (формат)

Определяет формат для представления пользовательского элемента управления.

Элемент элемента (формат) пользовательский элемент управления для элемента (формат) элемент ViewDefinitions (формат) конфигурации представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomControl` элемент. Необходимо указать один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntries для пользовательский элемент управления для представления (формат)](./customentries-element-for-customcontrol-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения представления пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент представления (формат)](./view-element-format.md)|Определяет представление, которое используется для отображения один или несколько объектов .NET.|

## <a name="remarks"></a>Замечания

В большинстве случаев только одно определение является обязательным для каждого элемента управления представления, но можно указать несколько определений, если вы хотите использовать одинаковое представление для отображения различных объектов .NET. В таком случае можно задать отдельный определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент CustomEntries для пользовательский элемент управления для представления (формат)](./customentries-element-for-customcontrol-for-view-format.md)

[Элемент представления (формат)](./view-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
