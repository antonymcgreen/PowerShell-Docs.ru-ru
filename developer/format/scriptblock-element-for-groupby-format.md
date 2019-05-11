---
title: Элемент ScriptBlock для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229315"
---
# <a name="scriptblock-element-for-groupby-format"></a>Элемент ScriptBlock для элемента GroupBy (формат)

Указывает сценарий, который запускает новую группу, при каждом изменении его значения.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) ScriptBlock для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[GroupBy-элемент для представления (формат)](./groupby-element-for-view-format.md)|Определяет порядок отображения группы объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

PowerShell запускает новую группу, при каждом изменении значения этого сценария.

Если этот элемент указан, нельзя указать [PropertyName](propertyname-element-for-groupby-format.md) элемент, чтобы начать новую группу.

## <a name="see-also"></a>См. также

[Элемент PropertyName для GroupBy (формат)](propertyname-element-for-groupby-format.md)

[GroupBy-элемент для представления (формат)](groupby-element-for-view-format.md)

[Запись файла форматирования PowerShell](writing-a-powershell-formatting-file.md)
