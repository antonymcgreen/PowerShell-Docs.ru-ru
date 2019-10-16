---
title: Элемент Кустоментриес для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364083"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>Элемент CustomEntries для элемента CustomControl для элемента View (формат)

Предоставляет определения представления пользовательского элемента управления. В представлении пользовательского элемента управления должно быть указано одно или несколько определений.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomControlEntries`. Необходимо указать один или несколько дочерних элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение представления пользовательского элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ошибка customcontrol для представления (формат)](./customcontrol-element-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет формат пользовательского элемента управления для представления.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, которое определено в одном элементе `CustomEntry`. Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент ошибка customcontrol для представления (формат)](./customcontrol-element-for-view-format.md)

[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
