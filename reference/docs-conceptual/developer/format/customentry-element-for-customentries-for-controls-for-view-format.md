---
title: Элемент Кустоментри для Кустоментриес элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785903"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)

Предоставляет определение элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol, для элемента Control элементов ActiveX (формат).

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomEntry` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет, как элемент управления отображает данные.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntries для элемента CustomControl для элемента View (формат)](./customentries-element-for-customcontrol-for-view-format.md)|Предоставляет определения для элемента управления.|

## <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Элемент CustomEntries для элемента CustomControl для элемента View (формат)](./customentries-element-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
