---
title: Элемент Кустомитем для Кустоментри для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783727"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)

Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) Кустомитем для ошибка customcontrol для Кустоментри для GroupBy (формат)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomItem` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Description|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет данные, отображаемые элементом управления.|
|[Элемент Frame для элемента CustomItem для элемента GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|
|[Элемент NewLine для элемента CustomItem для элемента GroupBy (формат)](./newline-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Добавляет пустую строку к отображению элемента управления.|
|[Элемент Text для элемента CustomItem для элемента GroupBy (формат)](./text-element-for-customitem-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает дополнительный текст для данных, отображаемых элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Description|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)|Предоставляет определение представления пользовательского элемента управления.|

## <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также:

[Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Элемент Frame для элемента CustomItem для элемента GroupBy (формат)](./frame-element-for-customitem-for-groupby-format.md)

[Элемент NewLine для элемента CustomItem для элемента GroupBy (формат)](./newline-element-for-customitem-for-groupby-format.md)

[Элемент Text для элемента CustomItem для элемента GroupBy (формат)](./text-element-for-customitem-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
