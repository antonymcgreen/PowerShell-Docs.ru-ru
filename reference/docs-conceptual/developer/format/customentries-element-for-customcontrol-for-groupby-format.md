---
title: Элемент Кустоментриес для ошибка customcontrol для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364093"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `CustomEntries`. Максимальное количество дочерних элементов, которое можно указать, не ограничено.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для ошибка customcontrol для GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|Определяет пользовательский элемент управления, отображающий новую группу.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном элементе `CustomEntry`. Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных групп. В таких случаях можно определить элемент `CustomEntry` для группы.

## <a name="see-also"></a>См. также:

[Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Элемент ошибка customcontrol для GroupBy (Format)](./customcontrol-element-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
