---
title: Элемент CustomEntries для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066521"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>Элемент CustomEntries для элемента CustomControl для элемента View (формат)

Предоставляет определения представления пользовательского элемента управления. Представление пользовательского элемента управления необходимо указать одно или несколько определений.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomControlEntries` элемент. Необходимо указать один или несколько дочерних элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для CustomEntries для представления (формат)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Обязательный элемент.<br /><br /> Предоставляет определение пользовательского элемента управления представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент пользовательский элемент управления для представления (формат)](./customcontrol-element-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет формат для представления пользовательского элемента управления.|

## <a name="remarks"></a>Замечания

В большинстве случаев элемент управления имеет только одно определение, который определен в одном `CustomEntry` элемент. Тем не менее существует возможность иметь несколько определений, если вы хотите использовать тот же элемент управления для отображения различных объектов .NET. В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.

## <a name="see-also"></a>См. также

[Элемент пользовательский элемент управления для представления (формат)](./customcontrol-element-for-view-format.md)

[Элемент CustomEntry для CustomEntries для представления (формат)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
