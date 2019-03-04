---
title: Рамку элемента для CustomItem пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: a7ee550527ec1cb00b4ed83478992c7ab54dbdb6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861710"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a>Элемент Frame для элемента CustomItem для элемента CustomControl для элемента View (формат)

Определяет способ отображения данных, таких как данные сдвига влево или вправо. Этот элемент используется при определении представления пользовательского элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry CutomControlView (формат) элемента фрейма для CustomItem для пользовательский элемент управления для представления (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomItem Element`|Обязательный элемент|
|[Элемент FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка данных сдвигается влево.|
|[Элемент FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, первая строка данных сдвигается вправо.|
|[Элемент LeftIndent](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от левого поля.|
|[Элемент RightIndent](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает количество символов, данные сдвигается от правого поля.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для CustomEntry для представления (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|Определяет, какие данные отображаются с помощью элемента управления и как он отображается.|

## <a name="remarks"></a>Замечания

Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) элементы в одном `Frame` элемент.

## <a name="see-also"></a>См. также

[Элемент FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент LeftIndent](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент RightIndent](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[Элемент CustomItem для CustomEntry для представления (формат)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
