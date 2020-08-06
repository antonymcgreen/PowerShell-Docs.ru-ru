---
title: Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773816"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес View (формат). для элемента Ошибка customcontrol для представления (Format) Кустоментри для Кустоментриес элементов управления для элемента Controls представления (Format) Кустомитем для Кустоментри для элементов управления представления (Format) ExpressionBinding для Кустомитем элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|`CustomControl Element`|Необязательный элемент.<br /><br /> Определяет элемент управления, используемый этим элементом управления.|
|[Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает, что элементы коллекций отображаются.|
|[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого элемента управления.|
|[Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается элементом управления.|
|[Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)|Определяет, какие данные отображаются элементом управления и как они отображаются.|

## <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)](./customitem-element-for-customentry-for-controls-for-view-format.md)

[Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
