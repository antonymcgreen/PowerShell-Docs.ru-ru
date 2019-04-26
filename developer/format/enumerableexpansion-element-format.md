---
title: Элемент EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066147"
---
# <a name="enumerableexpansion-element-format"></a>Элемент EnumerableExpansion (формат)

Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.

Элемент конфигурации элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) EnumerableExpansion (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `EnumerableExpansion` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для EnumerableExpansion (формат)](./entryselectedby-element-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Определяет, какие объекты коллекции .NET расширяются согласно этому определению.|
|[Разверните элемент (формат)](./expand-element-format.md)|Указывает, каким образом объект коллекции расширяется для данного определения.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansions (формат)](./enumerableexpansions-element-format.md)|Определяет различные способы, коллекции .NET, в которой объекты развертываются в том случае, когда они отображаются в представлении.|

## <a name="remarks"></a>Замечания

Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.

По умолчанию задается для отображения только свойств объектов в коллекции.

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
