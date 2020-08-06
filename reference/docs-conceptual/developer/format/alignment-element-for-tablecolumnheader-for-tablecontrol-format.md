---
title: Элемент Alignment для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1bf395b84af90d725c14b2f0ef569f72b5fcc613
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783931"
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

## <a name="remarks"></a>Примечания

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

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
