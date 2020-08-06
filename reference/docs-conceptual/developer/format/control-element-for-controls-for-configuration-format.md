---
title: Элемент Control для элементов управления Configuration (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9447efac84cff3cc33468aeebc97a8bdd6137518
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783829"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Элемент Control для элемента Controls для элемента Configuration (формат)

Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) для элементов управления конфигурации (Format).

## <a name="syntax"></a>Синтаксис

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент для `Control` элемента. Необходимо указать только один дочерний элемент.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomControl для элемента Control для элемента Controls для элемента Configuration (формат)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет элемент управления.|
|[Элемент Name для элемента управления конфигурации (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Задает имя, используемое для ссылки на элемент управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент управления в конфигурации (формат)](./controls-element-for-configuration-format.md)|Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования или другими элементами управления.|

## <a name="remarks"></a>Примечания

На имя, присвоенное этому элементу управления, можно ссылаться в следующих элементах:

- [Элемент ExpressionBinding для Кустомитем (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>См. также

[Элемент управления в конфигурации (формат)](./controls-element-for-configuration-format.md)

[Элемент ошибка customcontrol для элемента управления конфигурации (Format)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для Кустомитем (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент GroupBy для представления (формат)](./groupby-element-for-view-format.md)

[Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)](./name-element-for-control-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
