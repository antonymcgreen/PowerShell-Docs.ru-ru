---
title: Элемент DisplayError (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363993"
---
# <a name="displayerror-element-format"></a>Элемент DisplayError (формат)

Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.

Элемент Configuration (Format) Дефаултсеттингс элемент (Format) DisplayError (формат)

## <a name="syntax"></a>Синтаксис

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `DisplayError`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Дефаултсеттингс (Format)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|

## <a name="remarks"></a>Замечания

По умолчанию при возникновении ошибки при попытке отобразить фрагмент данных расположение данных остается пустым. Если этот элемент имеет значение true, будет отображена строка #ERR.

## <a name="see-also"></a>См. также:

[Элемент Дефаултсеттингс (Format)](./defaultsettings-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
