---
title: Элемент Name для элемента управления для элементов управления Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362713"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)

Задает имя элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления (Format) Name для элемента Control (формат), для которого наследуется конфигурация (Format).

## <a name="syntax"></a>Синтаксис

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элементов управления конфигурации (Format)](./control-element-for-controls-for-configuration-format.md)|Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя, используемое для ссылки на этот элемент управления.

## <a name="remarks"></a>Замечания

Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.

- При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .

- При создании другого общего элемента управления этот элемент управления может быть задан следующим элементом: [ExpressionBinding элемент для кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md) .

- При создании элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .

## <a name="see-also"></a>См. также:

[Элемент Control для элементов управления конфигурации (Format)](./control-element-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
