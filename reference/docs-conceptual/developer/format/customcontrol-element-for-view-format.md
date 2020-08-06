---
title: Элемент ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786056"
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

## <a name="remarks"></a>Примечания

В большинстве случаев для каждого представления элемента управления требуется только одно определение, но можно предоставить несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент CustomEntries для элемента CustomControl для элемента View (формат)](./customentries-element-for-customcontrol-for-view-format.md)

[Элемент View (формат)](./view-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
