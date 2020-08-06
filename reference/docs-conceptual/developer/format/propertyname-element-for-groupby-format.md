---
title: Элемент PropertyName для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e83ebd49e4f3087c817b3cc8772889dbe85113aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785614"
---
# <a name="propertyname-element-for-groupby-format"></a>Элемент PropertyName для элемента GroupBy (формат)

Указывает свойство .NET, которое запускает новую группу при изменении ее значения.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для представления (Format) PropertyName для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Определяет, как отображается группа объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Примечания

Windows PowerShell запускает новую группу при каждом изменении значения этого свойства.

Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) для запуска новой группы.

## <a name="example"></a>Пример

В следующем примере показано, как запустить новую группу при изменении значения свойства.

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).

## <a name="see-also"></a>См. также

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Элемент ScriptBlock для элемента GroupBy (формат)](./scriptblock-element-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
