---
title: Элемент Alignment для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364383"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Alignment для TableColumnHeader для TableControl (формат)

Определяет, как отображаются данные в заголовке столбца.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблехеадерс элемент (Format) Таблеколумнхеадер элемент (Format) элемента выравнивания для Таблеколумнхеадер (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Alignment`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнхеадер (Format)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивание данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите одно из следующих значений. В этих значениях регистр не учитывается.

По левому краю отображает данные, отображаемые в столбце слева. это значение по умолчанию, если этот элемент не указан.

По правому краю показывает данные, отображаемые в столбце справа.

Центрирование центров данных, отображаемых в столбце.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан элемент `TableColumnHeader`, данные по которому выводятся слева.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Таблеколумнхеадер (Format)](./tablecolumnheader-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
