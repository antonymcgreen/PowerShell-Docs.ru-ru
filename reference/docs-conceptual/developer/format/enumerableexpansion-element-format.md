---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EnumerableExpansion (формат)
description: Элемент EnumerableExpansion (формат)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668020"
---
# <a name="enumerableexpansion-element-format"></a>Элемент EnumerableExpansion (формат)

Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansion` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Определяет, какие объекты коллекции .NET разворачиваются этим определением.|
|[Элемент Expand (формат)](./expand-element-format.md)|Указывает, как разворачивается объект коллекции для этого определения.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansions (формат)](./enumerableexpansions-element-format.md)|Определяет различные способы развертывания объектов коллекции .NET при их отображении в представлении.|

## <a name="remarks"></a>Комментарии

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс  **System. Collections. ICollection** .

Поведение по умолчанию — отображение только свойств объектов в коллекции.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
