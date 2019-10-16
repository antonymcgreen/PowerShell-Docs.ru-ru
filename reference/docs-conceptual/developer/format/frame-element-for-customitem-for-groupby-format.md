---
title: Элемент Frame для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362953"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a>Элемент Frame для элемента CustomItem для элемента GroupBy (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Кустомитем GroupBy для Кустоментри для GroupBy (Format) элемент Frame для Кустомитем для GroupBy (Format)

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
|[Элемент Фирстлинехангинг для Frame для GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Элемент Фирстлинеиндент для Frame для GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Элемент Лефтиндент для Frame для GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Элемент ригхтиндент для Frame для GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Ригхтиндент, элемент|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри для GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Замечания

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-groupby-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-groupby-format.md) в одном элементе `Frame`.

## <a name="see-also"></a>См. также:

[Элемент Фирстлинехангинг для Frame для GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md)

[Элемент Фирстлинеиндент для Frame для GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Элемент Лефтиндент для Frame для GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md)

[Элемент Ригхтиндент для Frame для GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)

[Элемент Кустомитем для Кустоментри для GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
