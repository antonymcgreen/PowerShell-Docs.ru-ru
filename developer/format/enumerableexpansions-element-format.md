---
title: Элемент EnumerableExpansions (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066096"
---
# <a name="enumerableexpansions-element-format"></a>Элемент EnumerableExpansions (формат)

Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.

EnumerableExpansions элемент DefaultSettings (формат) элемент (формат) для конфигурации элемента (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемент. Нет ограничений на количество дочерних элементов, которые можно использовать.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)|Необязательный элемент.<br /><br /> Определяет определенных объектов коллекции .NET, которые будут развернуты, когда они отображаются в представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.|

## <a name="remarks"></a>Замечания

Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
