---
title: Элемент Кустоментриес для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c89eb25f6922a92e2c18298d0128c4c2ca93df3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785971"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>Элемент CustomEntries для элемента CustomControl для элемента View (формат)

Предоставляет определения представления пользовательского элемента управления. В представлении пользовательского элемента управления должно быть указано одно или несколько определений.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomControlEntries` элемента. Необходимо указать один или несколько дочерних элементов.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение представления пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomControl для элемента View (формат)](./customcontrol-element-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет формат пользовательского элемента управления для представления.|

## <a name="remarks"></a>Примечания

В большинстве случаев элемент управления имеет только одно определение, которое определено в одном `CustomEntry` элементе. Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент CustomControl для элемента View (формат)](./customcontrol-element-for-view-format.md)

[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
