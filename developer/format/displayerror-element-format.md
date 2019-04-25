---
title: Элемент DisplayError (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066266"
---
# <a name="displayerror-element-format"></a>Элемент DisplayError (формат)

Указывает, что строка #ERR отображаются при возникновении ошибки, отображение фрагмента данных.

DisplayError элемент DefaultSettings (формат) элемент (формат) для конфигурации элемента (формат)

## <a name="syntax"></a>Синтаксис

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `DisplayError` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.|

## <a name="remarks"></a>Замечания

По умолчанию при возникновении ошибки при попытке отображения фрагмента данных, расположение данных будет пустым. Когда этот элемент имеет значение true, то строка #ERR будет отображаться.

## <a name="see-also"></a>См. также

[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
