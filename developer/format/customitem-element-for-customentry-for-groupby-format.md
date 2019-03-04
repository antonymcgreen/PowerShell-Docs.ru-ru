---
title: Элемент CustomItem для CustomEntry для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856930"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)

Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomItem GroupBy (формат) CustomEntry для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для CustomItem для GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.|
|[Элемент новой строки для CustomItem для GroupBy (формат)](./newline-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Добавляет пустой строки для отображения элемента управления.|
|[Текстовый элемент для CustomItem для GroupBy (формат)](./text-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает дополнительный текст для данных, отображаемых элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)|Предоставляет определение пользовательского элемента управления представления.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также

[Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)

[Элемент ExpressionBinding для CustomItem для GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Элемент Frame для CustomItem для GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)

[Элемент новой строки для CustomItem для GroupBy (формат)](./newline-element-for-customitem-for-groupby-format.md)

[Текстовый элемент для CustomItem для GroupBy (формат)](./text-element-for-customitem-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
