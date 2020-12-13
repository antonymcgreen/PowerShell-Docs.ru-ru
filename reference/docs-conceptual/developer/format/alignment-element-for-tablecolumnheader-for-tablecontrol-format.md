---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Alignment для TableColumnHeader для TableControl (формат)
description: Элемент Alignment для TableColumnHeader для TableControl (формат)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666830"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Alignment для TableColumnHeader для TableControl (формат)

Определяет, как отображаются данные в заголовке столбца.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблехеадерс элемент (Format) Таблеколумнхеадер элемент (Format) элемента выравнивания для Таблеколумнхеадер (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Alignment` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивание данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите одно из следующих значений. В этих значениях регистр не учитывается.

По левому краю отображает данные, отображаемые в столбце слева. это значение по умолчанию, если этот элемент не указан.

По правому краю показывает данные, отображаемые в столбце справа.

Центрирование центров данных, отображаемых в столбце.

## <a name="remarks"></a>Комментарии

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан `TableColumnHeader` элемент, данные которого выводятся слева.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
