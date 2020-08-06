---
title: Элемент DisplayError (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774292"
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

## <a name="remarks"></a>Примечания

По умолчанию при возникновении ошибки при попытке отобразить фрагмент данных расположение данных остается пустым. Если этот элемент имеет значение true, будет отображена строка #ERR.

## <a name="see-also"></a>См. также

[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
