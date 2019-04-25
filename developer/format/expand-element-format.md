---
title: Разверните элемент (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066011"
---
# <a name="expand-element-format"></a>Элемент Expand (формат)

Указывает, каким образом объект коллекции расширяется для данного определения.

Элемент конфигурации элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) EnumerableExpansion (формат) разверните элемент (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `Expand` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)|Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите одно из следующих значений:

- EnumOnly: Отображаются только свойства объектов в коллекции.

- CoreOnly — Отображаются только свойства объекта коллекции.

- Оба: Отображает свойства объектов в коллекции и свойства объекта коллекции.

## <a name="remarks"></a>Замечания

Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.

По умолчанию задается для отображения только свойств объектов в коллекции.

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
