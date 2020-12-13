---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)
description: Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648276"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)

Предоставляет определение общего элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элемента Configuration (формат) Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемента. Необходимо указать элементы, отображаемые в определении.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления.|
|[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет, какие данные отображаются элементом управления и как они отображаются.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определения общего элемента управления.|

## <a name="remarks"></a>Комментарии

В большинстве случаев для каждого общего пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
