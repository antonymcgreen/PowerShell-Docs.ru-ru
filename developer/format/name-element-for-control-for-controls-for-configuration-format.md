---
title: Имя элемента для элемента управления для элементов управления для Configuration (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860090"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)

Задает имя элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) имя для элемента управления для элементов управления для конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `Name` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент управления для элементов управления для конфигурации (формат)](./control-element-for-controls-for-configuration-format.md)|Определяет общий элемент управления, который может использоваться все представления файла форматирования и имя, которое используется для ссылки на элемент управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя, которое используется для ссылки на этот элемент управления.

## <a name="remarks"></a>Замечания

Имя, указанное здесь можно использовать в следующих элементах для ссылки на этот элемент управления.

- При создании таблицы, список, расширенный пользовательский элемент управления или представления, элемент управления можно задать с помощью следующих элемента: [GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

- При создании другого общего элемента управления, этот элемент управления можно задать с помощью следующих элемента: [Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- При Создание элемента управления, который можно использовать представления, этот элемент управления можно указать в следующем элементе: [Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>См. также

[Элемент управления для элементов управления для конфигурации (формат)](./control-element-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
