---
title: Элемент ScriptBlock для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787688"
---
# <a name="scriptblock-element-for-groupby-format"></a>Элемент ScriptBlock для элемента GroupBy (формат)

Задает скрипт, запускающий новую группу при изменении ее значения.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента ScriptBlock представления (Format) для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Определяет, как отображается группа объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Примечания

PowerShell запускает новую группу при каждом изменении значения этого сценария.

Если этот элемент указан, нельзя указать элемент [PropertyName](propertyname-element-for-groupby-format.md) для запуска новой группы.

## <a name="see-also"></a>См. также

[Элемент PropertyName для элемента GroupBy (формат)](propertyname-element-for-groupby-format.md)

[Элемент GroupBy для элемента View (формат)](groupby-element-for-view-format.md)

[Написание файла форматирования PowerShell](writing-a-powershell-formatting-file.md)
