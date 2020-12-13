---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент DisplayError (формат)
description: Элемент DisplayError (формат)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649921"
---
# <a name="displayerror-element-format"></a>Элемент DisplayError (формат)

Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.

Элемент Configuration (Format) Дефаултсеттингс элемент (Format) DisplayError (формат)

## <a name="syntax"></a>Синтаксис

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `DisplayError` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|

## <a name="remarks"></a>Комментарии

По умолчанию при возникновении ошибки при попытке отобразить фрагмент данных расположение данных остается пустым. Если этот элемент имеет значение true, будет отображена строка #ERR.

## <a name="see-also"></a>См. также:

[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
