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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066776"
---
# <a name="control-element-for-controls-for-view--format"></a>Элемент Control для элемента Controls для элемента View (формат)

Определяет элемент управления, который может использоваться представление и имя, которое используется для ссылки на элемент управления.

Элемент представления ViewDefinitions элемент (формат) конфигурации элемент (формат) (формат) управляет элемент управления элемента (формат) для элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Control` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Name описания для элемента управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Задает имя элемента управления.|
|[Пользовательский элемент управления элемент для элемента управления для элементов управления для представления (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)|Обязательный элемент.<br /><br /> Определяет элемент управления, используемый в данном представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Controls-элемент (формат)](./controls-element-for-view-format.md)|Определяет элементы управления представления, которые могут использоваться по определенному представлению.|

## <a name="remarks"></a>Замечания

Этот элемент управления можно указать, следующие элементы:

- [Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [Элемент CustomControlName для ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [Элемент CustomControlName для GroupBy (формат)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>См. также

[Пользовательский элемент управления элемент для элемента управления для элементов управления для представления (формат)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[Элемент CustomControlName для ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Элемент CustomControlName для ExpressionBinding для GroupBy (формат)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[Controls-элемент (формат)](./controls-element-for-view-format.md)

[Элемент Name описания для элемента управления для элементов управления для представления (формат)](./name-element-for-control-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
