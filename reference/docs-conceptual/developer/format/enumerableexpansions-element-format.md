---
title: Элемент Енумерабликспансионс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363303"
---
# <a name="enumerableexpansions-element-format"></a>Элемент EnumerableExpansions (формат)

Определяет, как развертываются объекты коллекции .NET, когда они отображаются в представлении.

Элемент Configuration (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EnumerableExpansions`. Количество дочерних элементов, которые можно использовать, не ограничено.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Енумерабликспансион (Format)](./enumerableexpansion-element-format.md)|Необязательный элемент.<br /><br /> Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Дефаултсеттингс (Format)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|

## <a name="remarks"></a>Замечания

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
