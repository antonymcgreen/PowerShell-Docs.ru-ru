---
title: Элемент CustomItem для CustomEntry для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855610"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a>Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)

Определяет, какие данные отображаются с помощью элемента управления и как он отображается. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для представления (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент. Дополнительные сведения см. в разделе "Примечания".

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для CustomItem для элементов управления для представления (формат)](./frame-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных, таких как данные сдвига влево или вправо.|
|[Элемент новой строки для CustomItem для элементов управления для представления (формат)](./newline-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет пустой строки для отображения элемента управления.|
|[Текстовый элемент для CustomItem для элементов управления для представления (формат)](./text-element-for-customitem-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Добавляет текст, таких как круглые скобки или квадратные скобки, отображение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

При указании дочерние элементы `CustomItem` элемент, имейте в виду следующее:

- Дочерние элементы должны добавляться в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text`, и `Frame`.

- Не ограничено максимальное число последовательности, которые можно указать.

- В каждой последовательности не ограничено максимальное число `ExpressionBinding` элементы, которые можно использовать.

## <a name="see-also"></a>См. также

[Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент Frame для CustomItem для элементов управления для представления (формат)](./frame-element-for-customitem-for-controls-for-view-format.md)

[Элемент новой строки для CustomItem для элементов управления для представления (формат)](./newline-element-for-customitem-for-controls-for-view-format.md)

[Текстовый элемент для CustomItem для элементов управления для представления (формат)](./text-element-for-customitem-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
