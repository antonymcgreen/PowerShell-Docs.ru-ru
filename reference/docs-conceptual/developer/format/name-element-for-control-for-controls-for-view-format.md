---
title: Элемент Name для элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 109f3a40606dbe82322decf0c69d2367c75175f6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781092"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>Элемент Name для элемента Control для элемента Controls для элемента View (формат)

Задает имя элемента управления.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления для представления (формат) элемента управления для представления (формат).

## <a name="syntax"></a>Синтаксис

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элементов управления для представления (формат)](./control-element-for-controls-for-view-format.md)|Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя, используемое для ссылки на элемент управления.

## <a name="remarks"></a>Примечания

Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.

- При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .

- При создании другого элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .

## <a name="see-also"></a>См. также

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент Control для элементов управления для представления (формат)](./control-element-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
