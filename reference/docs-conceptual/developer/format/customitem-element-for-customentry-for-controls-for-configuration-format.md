---
title: Элемент Кустомитем для Кустоментри для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: bb8124242496f192717127f201674bc1428e5de0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785869"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)

Определяет, какие данные отображаются элементом управления и как они отображаются. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элемента Configuration (формат) Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format) Кустомитем для кустоментри для элементов управления конфигурации.

## <a name="syntax"></a>Синтаксис

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomItem` элемента. Дополнительные сведения см. в подразделе "Примечания".

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных, например сдвиг данных влево или вправо.|
|[Элемент NewLine для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Добавляет пустую строку к отображению элемента управления.|
|[Элемент Text для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./text-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Примечания

При указании дочерних элементов `CustomItem` элемента учитывайте следующее:

- Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding` , `NewLine` , `Text` и `Frame` .

- Максимальное число последовательностей, которое можно указать, не ограничено.

- В каждой последовательности не существует максимального ограничения на количество `ExpressionBinding` элементов, которые можно использовать.

## <a name="see-also"></a>См. также

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент NewLine для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент Text для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
