---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EnumerableExpansions (формат)
description: Элемент EnumerableExpansions (формат)
ms.openlocfilehash: 789599e6ff368b4685c7937d5b6eb38618752f9e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660179"
---
# <a name="enumerableexpansions-element-format"></a>Элемент EnumerableExpansions (формат)

Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.

Элемент Configuration (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемента. Количество дочерних элементов, которые можно использовать, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)|Необязательный элемент.<br /><br /> Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|

## <a name="remarks"></a>Комментарии

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс  **System. Collections. ICollection** .

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
