---
title: Элемент Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 81a8959c19502a2e56f4cfa48a1e480509d84b6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774054"
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

## <a name="remarks"></a>Примечания

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .

Поведение по умолчанию — отображение только свойств объектов в коллекции.

## <a name="see-also"></a>См. также

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
