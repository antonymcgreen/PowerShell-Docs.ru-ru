---
title: Элемент ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363363"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomControl`. Необходимо указать один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментриес для ошибка customcontrol для представления (Format)](./customentries-element-for-customcontrol-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определения представления пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[View, элемент (Format)](./view-element-format.md)|Определяет представление, используемое для отображения одного или нескольких объектов .NET.|

## <a name="remarks"></a>Замечания

В большинстве случаев для каждого представления элемента управления требуется только одно определение, но можно предоставить несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент Кустоментриес для ошибка customcontrol для представления (Format)](./customentries-element-for-customcontrol-for-view-format.md)

[View, элемент (Format)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
