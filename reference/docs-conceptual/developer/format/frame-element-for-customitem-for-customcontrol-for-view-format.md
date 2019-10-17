---
title: Элемент Frame для Кустомитем для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: 925ef86e61801f5a66f89dd25e0756f00dd35155
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363643"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)

Определяет способ отображения данных, например сдвиг данных влево или вправо. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для элемента View (формат) Кустоментри для Кустоментриес для представления (Format) Кустомитем для Кустоментри для Кустомконтролвиев (Format) элемент Frame для Кустомитем для ошибка customcontrol для представления (Format)

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
|[Фирстлинехангинг, элемент](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается влево.|
|[Фирстлинеиндент, элемент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько знаков первая строка данных смещается вправо.|
|[Лефтиндент, элемент](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные из левого поля.|
|[Ригхтиндент, элемент](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, сколько символов перемещает данные с правого края.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Замечания

Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) в одном элементе `Frame`.

## <a name="see-also"></a>См. также:

[Фирстлинехангинг, элемент](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Фирстлинеиндент, элемент](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Лефтиндент, элемент](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[Ригхтиндент, элемент](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент Кустомитем для Кустоментри для представления (Format)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
