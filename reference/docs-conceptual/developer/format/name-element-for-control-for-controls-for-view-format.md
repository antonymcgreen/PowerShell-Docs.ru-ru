---
title: Элемент Name для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365103"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>Элемент Name для элемента Control для элемента Controls для элемента View (формат)

Задает имя элемента управления.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления для представления (формат) элемента управления для представления (формат).

## <a name="syntax"></a>Синтаксис

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элементов управления для представления (формат)](./control-element-for-controls-for-view-format.md)|Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя, используемое для ссылки на элемент управления.

## <a name="remarks"></a>Замечания

Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.

- При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .

- При создании другого элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .

## <a name="see-also"></a>См. также:

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент Control для элементов управления для представления (формат)](./control-element-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
