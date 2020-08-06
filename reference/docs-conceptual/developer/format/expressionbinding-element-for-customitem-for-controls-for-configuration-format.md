---
title: Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1ad83fa9d915822eaefb490658f8a219defdddf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773918"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a>Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)

Определяет данные, отображаемые элементом управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control for Configuration (Format) Кустоментриес элемента для ошибка customcontrol для элементов конфигурации (Format) Кустоментри для ошибка customcontrol for Controls для элемента конфигурации (Format) Кустомитем для кустоментри для элементов управления в элементе Configuration ExpressionBinding для кустомитем для элементов управления конфигурации (Format).

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
|[Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает имя общего элемента управления или элемента управления представления.|
|[Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает, что элементы коллекций отображаются элементом управления.|
|[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для использования этого общего элемента управления.|
|[Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, значение которого отображается общим элементом управления.|
|[Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, значение которого отображается общим элементом управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.|

## <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Элемент Кустомитем для Кустоментри элементов управления для конфигурации](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
