---
title: Элемент CustomEntries для пользовательский элемент управления для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066606"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)

Предоставляет определения стандартного элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntries` элемент. Необходимо указать один или несколько дочерних элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|Предоставляет определение стандартного элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Определяет общего элемента управления.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, который определен в одном `CustomEntry` элемент. Тем не менее существует возможность иметь несколько определений, если вы хотите использовать тот же элемент управления для отображения различных объектов .NET. В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
