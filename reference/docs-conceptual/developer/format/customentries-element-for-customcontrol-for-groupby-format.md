---
title: Элемент Кустоментриес для ошибка customcontrol для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2221d1bb94159697ff10466e4606d6d54e117e30
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785954"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)

Предоставляет определения для элемента управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент GroupBy для элемента представления (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomEntries` элемента. Максимальное количество дочерних элементов, которое можно указать, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomControl для элемента GroupBy (формат)](./customcontrol-element-for-groupby-format.md)|Определяет пользовательский элемент управления, отображающий новую группу.|

## <a name="remarks"></a>Примечания

В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном `CustomEntry` элементе. Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных групп. В таких случаях можно определить `CustomEntry` элемент для группы.

## <a name="see-also"></a>См. также

[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Элемент CustomControl для элемента GroupBy (формат)](./customcontrol-element-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
