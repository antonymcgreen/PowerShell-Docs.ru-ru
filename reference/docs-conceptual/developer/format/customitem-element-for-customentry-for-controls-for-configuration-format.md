---
title: Элемент Кустомитем для Кустоментри для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364033"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)

Определяет, какие данные отображаются элементом управления и как они отображаются. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри для элементов управления в конфигурации

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomItem`. Дополнительные сведения см. в разделе Примечания.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для элемента управления Кустомитем для Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных, например сдвиг данных влево или вправо.|
|[Элемент новой строки для элементов управления Кустомитем для Configuration (Format)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Добавляет пустую строку к отображению элемента управления.|
|[Текстовый элемент для Кустомитем элементов управления для конфигурации (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

При указании дочерних элементов элемента `CustomItem` учитывайте следующее:

- Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text` и `Frame`.

- Максимальное число последовательностей, которое можно указать, не ограничено.

- В каждой последовательности нет максимального ограничения числа элементов `ExpressionBinding`, которые можно использовать.

## <a name="see-also"></a>См. также:

[Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент Frame для элемента управления Кустомитем для Configuration (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент новой строки для элементов управления Кустомитем для Configuration (Format)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Текстовый элемент для Кустомитем элементов управления для конфигурации (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
