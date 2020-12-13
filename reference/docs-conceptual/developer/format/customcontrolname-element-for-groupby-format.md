---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomControlName для элемента GroupBy (формат)
description: Элемент CustomControlName для элемента GroupBy (формат)
ms.openlocfilehash: 03664fe4d5559312e2720a3892493c90c15f7501
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655426"
---
# <a name="customcontrolname-element-for-groupby-format"></a>Элемент CustomControlName для элемента GroupBy (формат)

Задает имя пользовательского элемента управления, используемого для вывода новой группы. Этот элемент используется при определении представления таблицы, списка, расширенного или пользовательского элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента представления (Format) Кустомконтролнаме в GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomControlName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Определяет, как Windows PowerShell отображает новую группу объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите имя пользовательского элемента управления, используемого для вывода новой группы.

## <a name="remarks"></a>Комментарии

Можно создавать стандартные элементы управления, которые могут использоваться всеми представлениями файла форматирования, а также создавать элементы управления представления, которые могут использоваться в определенном представлении. Следующие элементы определяют имена этих настраиваемых элементов управления:

- [Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Элемент Name для элемента Control для элемента Controls для элемента View (формат)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также:

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

[Элемент Name для элемента Control для элемента Controls для элемента View (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
