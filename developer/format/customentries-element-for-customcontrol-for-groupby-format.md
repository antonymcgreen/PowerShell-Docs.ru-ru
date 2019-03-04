---
title: Элемент CustomEntries для пользовательский элемент управления для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853680"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)

Предоставляет определения для элемента управления. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние и родительские элементы из `CustomEntries` элемент. Не ограничено максимальное число дочерних элементов, которые могут быть указаны.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Пользовательский элемент управления-элемент для GroupBy (формат)](./customcontrol-element-for-groupby-format.md)|Определяет пользовательский элемент управления, отображающий новой группы.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, которое указано в одном `CustomEntry` элемент. Тем не менее можно указать несколько определений, если вы хотите использовать тот же элемент управления для отображения различных групп. В таких случаях можно определить `CustomEntry` элемента для группы.

## <a name="see-also"></a>См. также

[Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Пользовательский элемент управления-элемент для GroupBy (формат)](./customcontrol-element-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
