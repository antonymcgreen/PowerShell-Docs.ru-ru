---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)
description: Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)
ms.openlocfilehash: 67bff97c27cfedf046b17eea438efcd66ae2ee4a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666762"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)

Определяет, какие данные отображаются элементом управления и как они отображаются. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес элемент для элементов управления для представления (Format) Кустоментри для Кустоментриес для элементов управления представления (формат) кустомитем для кустоментри для элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomItem` элемента. Дополнительные сведения см. в подразделе "Примечания".

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)](./frame-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных, например сдвиг данных влево или вправо.|
|[Элемент NewLine для элемента CustomItem для элемента Controls для элемента View (формат)](./newline-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет пустую строку к отображению элемента управления.|
|[Элемент Text для элемента CustomItem для элемента Controls для элемента View (формат)](./text-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Комментарии

При указании дочерних элементов `CustomItem` элемента учитывайте следующее:

- Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding` , `NewLine` , `Text` и `Frame` .

- Максимальное число последовательностей, которое можно указать, не ограничено.

- В каждой последовательности не существует максимального ограничения на количество `ExpressionBinding` элементов, которые можно использовать.

## <a name="see-also"></a>См. также:

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Элемент NewLine для элемента CustomItem для элемента Controls для элемента View (формат)](./newline-element-for-customitem-for-controls-for-view-format.md)

[Элемент Text для элемента CustomItem для элемента Controls для элемента View (формат)](./text-element-for-customitem-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
