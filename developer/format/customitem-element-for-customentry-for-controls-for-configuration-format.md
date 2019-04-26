---
title: Элемент CustomItem для CustomEntry для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066436"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)

Определяет, какие данные отображаются с помощью элемента управления и как он отображается. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для конфигурации

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент. Дополнительные сведения см. в разделе "Примечания".

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для CustomItem для элементов управления для конфигурации (формат)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных, таких как данные сдвига влево или вправо.|
|[Элемент новой строки для CustomItem для элементов управления для конфигурации (формат)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Добавляет пустой строки для отображения элемента управления.|
|[Текстовый элемент для CustomItem для элементов управления для конфигурации (формат)](./text-element-for-customitem-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Добавляет текст, таких как круглые скобки или квадратные скобки, отображение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Замечания

При указании дочерние элементы `CustomItem` элемент, имейте в виду следующее:

- Дочерние элементы должны добавляться в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text`, и `Frame`.

- Не ограничено максимальное число последовательности, которые можно указать.

- В каждой последовательности не ограничено максимальное число `ExpressionBinding` элементы, которые можно использовать.

## <a name="see-also"></a>См. также

[Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент Frame для CustomItem для элементов управления для конфигурации (формат)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент новой строки для CustomItem для элементов управления для конфигурации (формат)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[Текстовый элемент для CustomItem для элементов управления для конфигурации (формат)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
