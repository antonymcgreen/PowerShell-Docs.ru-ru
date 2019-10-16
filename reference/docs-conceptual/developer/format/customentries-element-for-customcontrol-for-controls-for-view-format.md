---
title: Элемент Кустоментриес для ошибка customcontrol элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3485958a-ba87-4932-907c-a8f140c4abdb
caps.latest.revision: 8
ms.openlocfilehash: 4856aee930285781a101868bd6cb67824585bce1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368813"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента View (формат)

Предоставляет определения для элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элементов управления для представления (формат)

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
|[Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Определяет элемент управления, используемый представлением.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном элементе `CustomEntry`. Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
