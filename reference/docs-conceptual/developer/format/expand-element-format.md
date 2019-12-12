---
title: Элемент Expand (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368743"
---
# <a name="expand-element-format"></a>Элемент Expand (формат)

Указывает, как разворачивается объект коллекции для этого определения.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) развернуть элемент (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Expand`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Енумерабликспансион (Format)](./enumerableexpansion-element-format.md)|Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.|

## <a name="text-value"></a>Текстовое значение

Укажите одно из следующих значений.

- Енумонли: отображает только свойства объектов в коллекции.

- Кореонли: отображает только свойства объекта коллекции.

- Оба: отображает свойства объектов в коллекции и свойства объекта коллекции.

## <a name="remarks"></a>Замечания

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .

Поведение по умолчанию — отображение только свойств объектов в коллекции.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
