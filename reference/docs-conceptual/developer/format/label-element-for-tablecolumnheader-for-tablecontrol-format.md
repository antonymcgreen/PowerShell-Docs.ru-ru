---
title: Элемент Label для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365173"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)

Определяет метку, отображаемую в верхней части столбца. Этот элемент используется при определении табличного представления.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер элемента для Таблехеадерс в TableControl (Format) элемент Label для Таблеколумнхеадер для Таблеконтрол (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Label`. Для каждого столбца допускается только одна метка.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивание данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите текст, отображаемый в верхней части столбца таблицы. Для метки столбца нет ограниченных символов.

## <a name="remarks"></a>Замечания

Если метка не указана, то используется имя свойства, значение которого отображается в строках.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан элемент `TableColumnHeader`, метка которого равна "Column 1".

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
