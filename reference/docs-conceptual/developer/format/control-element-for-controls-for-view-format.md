---
title: Элемент Control для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363473"
---
# <a name="control-element-for-controls-for-view--format"></a>Элемент Control для элемента Controls для элемента View (формат)

Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Control`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Name элемента управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Задает имя элемента управления.|
|[Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет элемент управления, используемый этим представлением.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Controls (Format)](./controls-element-for-view-format.md)|Определяет элементы управления представления, которые могут использоваться в определенном представлении.|

## <a name="remarks"></a>Замечания

Этот элемент управления может быть задан следующими элементами:

- [Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [Элемент Кустомконтролнаме для ExpressionBinding для ошибка customcontrol для представления (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [Элемент Кустомконтролнаме для GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>См. также:

[Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент Кустомконтролнаме для ExpressionBinding для ошибка customcontrol для представления (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент Controls (Format)](./controls-element-for-view-format.md)

[Элемент Name для элемента управления для элементов управления в представлении (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
