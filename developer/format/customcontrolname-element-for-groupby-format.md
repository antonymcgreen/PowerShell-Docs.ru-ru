---
title: Элемент CustomControlName для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860310"
---
# <a name="customcontrolname-element-for-groupby-format"></a>Элемент CustomControlName для элемента GroupBy (формат)

Задает имя пользовательского элемента управления, используемый для отображения новой группы. Этот элемент используется при определении таблицы, список, расширенный пользовательский элемент управления или представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) CustomControlName GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительские элементы из `CustomControlName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)|Определяет, как Windows PowerShell отображает группу объектов.|

## <a name="text-value"></a>Текстовое значение

Укажите имя пользовательского элемента управления, который используется для отображения новой группы.

## <a name="remarks"></a>Замечания

Можно создавать стандартные элементы управления, которые могут использоваться все представления файл форматирования, и можно создать элементы управления представления, которые могут использоваться по определенному представлению. Следующие элементы укажите имена этих пользовательских элементов управления:

- [Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Элемент Name описания для элемента управления для элементов управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также

[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

[Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

[Элемент Name описания для элемента управления для элементов управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
