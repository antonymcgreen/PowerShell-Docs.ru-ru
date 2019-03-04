---
title: Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859810"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)

Предоставляет определение стандартного элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемент. Необходимо указать элементы, отображаемые с помощью определения.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет типы .NET, использующих определение общего элемента управления или условие, которое должен существовать для данного элемента управления для использования.|
|[Элемент CustomItem для CustomEntry для элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет, какие данные отображаются с помощью элемента управления и как он отображается.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntries для пользовательский элемент управления для конфигурации (формат)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определения стандартного элемента управления.|

## <a name="remarks"></a>Замечания

В большинстве случаев для каждого распространенных пользовательского элемента управления необходим только одно определение, но можно иметь несколько определений, если вы хотите использовать тот же элемент управления для отображения различных объектов .NET. В таком случае можно задать отдельный определение для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент CustomEntries для пользовательский элемент управления для конфигурации (формат)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[Элемент CustomItem для CustomEntry для элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
