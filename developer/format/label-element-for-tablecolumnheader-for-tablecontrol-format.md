---
title: Метка элемента для TableColumnHeader для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 59dfd40b95d5088a711eb89cf101eb31a4b159f5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856090"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)

Определяет метку, которая отображается в верхней части столбца. Этот элемент используется при определении представления таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) TableControl-элемент (формат) TableHeaders элемент конфигурации для элемента TableColumnHeader TableControl (формат) для TableHeaders для метки элемента TableControl (формат) TableColumnHeader для TablControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Label` элемент. Для каждого столбца можно использовать только одну метку.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnHeader для TableHeaders для TableControl (формат)](./tablecolumnheader-element-format.md)|Определяет метку, ширину и выравнивания данных для столбца таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите текст, отображаемый в верхней части столбца таблицы. Существуют не запрещенные знаки для метки столбца.

## <a name="remarks"></a>Замечания

Если метка не указана, используется имя свойства, значение которого отображается в строках.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показано `TableColumnHeader` элемент, метка которого является «Столбец 1».

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
