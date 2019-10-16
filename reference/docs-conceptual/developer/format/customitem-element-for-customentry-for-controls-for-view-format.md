---
title: Элемент Кустомитем для Кустоментри элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363943"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)

Определяет, какие данные отображаются элементом управления и как они отображаются. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) для Кустоментриес для элементов управления для представления (Format) Кустомитем для Кустоментри для элементов управления представления (формат)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomItem`. Дополнительные сведения см. в разделе Примечания.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для Кустомитем элементов управления для представления (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных, например сдвиг данных влево или вправо.|
|[Элемент новой строки для элементов управления Кустомитем для представления (формат)](./newline-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет пустую строку к отображению элемента управления.|
|[Текстовый элемент для Кустомитем элементов управления для представления (формат)](./text-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

При указании дочерних элементов элемента `CustomItem` учитывайте следующее:

- Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text` и `Frame`.

- Максимальное число последовательностей, которое можно указать, не ограничено.

- В каждой последовательности нет максимального ограничения числа элементов `ExpressionBinding`, которые можно использовать.

## <a name="see-also"></a>См. также:

[Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент Frame для Кустомитем элементов управления для представления (Format)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Элемент новой строки для элементов управления Кустомитем для представления (формат)](./newline-element-for-customitem-for-controls-for-view-format.md)

[Текстовый элемент для Кустомитем элементов управления для представления (формат)](./text-element-for-customitem-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
