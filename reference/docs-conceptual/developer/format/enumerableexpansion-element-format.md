---
title: Элемент Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368753"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EnumerableExpansion`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Енумерабликспансион (Format)](./entryselectedby-element-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Определяет, какие объекты коллекции .NET разворачиваются этим определением.|
|[Элемент Expand (Format)](./expand-element-format.md)|Указывает, как разворачивается объект коллекции для этого определения.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Енумерабликспансионс (Format)](./enumerableexpansions-element-format.md)|Определяет различные способы развертывания объектов коллекции .NET при их отображении в представлении.|

## <a name="remarks"></a>Замечания

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .

Поведение по умолчанию — отображение только свойств объектов в коллекции.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
