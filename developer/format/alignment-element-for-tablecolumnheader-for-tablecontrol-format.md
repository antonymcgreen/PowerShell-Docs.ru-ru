---
title: Выравнивание элемента для TableColumnHeader для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067014"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Alignment для TableColumnHeader для TableControl (формат)

Определяет способ отображения данных в заголовке столбца.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableHeaders (формат) элемент TableColumnHeader (формат) выравнивание элемент конфигурации для TableColumnHeader (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Alignment` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивания данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите одно из следующих значений. Эти значения не учитывают регистр.

Выравнивание данных отображаются в столбце слева это значение по умолчанию, если этот элемент не указан.

По правому данные отображаются в столбце справа.

Center центров обработки данных, отображаемых в столбце.

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показано `TableColumnHeader` элемента, данные которого по левому краю.

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

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
