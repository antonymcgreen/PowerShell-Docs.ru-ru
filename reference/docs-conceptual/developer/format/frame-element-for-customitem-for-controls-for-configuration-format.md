---
title: Элемент Frame для Кустомитем элементов управления в конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363663"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Формат) элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри для элементов управления для элемента конфигурации Кустомитем для элементов управления конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Frame`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomItem Element`|Обязательный элемент|
|[Элемент Фирстлинехангинг для Frame для элементов управления конфигурации (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Элемент Фирстлинеиндент для Frame для элементов управления конфигурации (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Элемент Лефтиндент для Frame для элементов управления конфигурации (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Элемент Ригхтиндент для Frame для элементов управления конфигурации (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Замечания

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) в одном элементе `Frame`.

## <a name="see-also"></a>См. также:

[Элемент Фирстлинехангинг для Frame для элементов управления конфигурации (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Элемент Фирстлинеиндент для Frame для элементов управления конфигурации (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент Лефтиндент для Frame для элементов управления конфигурации (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент Ригхтиндент для Frame для элементов управления конфигурации (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
