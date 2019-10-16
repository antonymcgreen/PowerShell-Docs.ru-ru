---
title: Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364073"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)

Предоставляет определение общего элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol элементов управления в конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomEntry`. Необходимо указать элементы, отображаемые в определении.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления.|
|[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет, какие данные отображаются элементом управления и как они отображаются.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определения общего элемента управления.|

## <a name="remarks"></a>Замечания

В большинстве случаев для каждого общего пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET. В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также:

[Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
