---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Control для элемента Controls для элемента View (формат)
description: Элемент Control для элемента Controls для элемента View (формат)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668088"
---
# <a name="control-element-for-controls-for-view--format"></a>Элемент Control для элемента Controls для элемента View (формат)

Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Control` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Name элемента управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Задает имя элемента управления.|
|[Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет элемент управления, используемый этим представлением.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Controls (Format)](./controls-element-for-view-format.md)|Определяет элементы управления представления, которые могут использоваться в определенном представлении.|

## <a name="remarks"></a>Комментарии

Этот элемент управления может быть задан следующими элементами:

- [Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [Элемент CustomControlName для элемента GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>См. также:

[Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент Controls (Format)](./controls-element-for-view-format.md)

[Элемент Name для элемента Control для элемента Controls для элемента View (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
