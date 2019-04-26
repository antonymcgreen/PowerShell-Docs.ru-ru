---
title: Имя элемента для элемента управления для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065110"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>Элемент Name для элемента Control для элемента Controls для элемента View (формат)

Задает имя элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент конфигурации (формат) указывает элемент управления элемента (формат) для элементов управления для элемента имя представления (формат) для элемента управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `Name` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент управления для элементов управления для представления (формат)](./control-element-for-controls-for-view-format.md)|Определяет элемент управления, который может использоваться представление и имя, которое используется для ссылки на элемент управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя, которое используется для ссылки на элемент управления.

## <a name="remarks"></a>Замечания

Имя, указанное здесь можно использовать в следующих элементах для ссылки на этот элемент управления.

- При создании таблицы, список, расширенный пользовательский элемент управления или представления, элемент управления можно задать с помощью следующих элемента: [GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

- При создание другого элемента управления, можно использовать представление, этот элемент управления можно указать в следующем элементе: [Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также

[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

[Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент управления для элементов управления для представления (формат)](./control-element-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
