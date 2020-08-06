---
title: Элемент Енумерабликспансионс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774020"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansions` элемента. Количество дочерних элементов, которые можно использовать, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)|Необязательный элемент.<br /><br /> Определяет конкретные объекты коллекции .NET, развернутые при их отображении в представлении.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DefaultSettings (формат)](./defaultsettings-element-format.md)|Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.|

## <a name="remarks"></a>Примечания

Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции. В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .

## <a name="see-also"></a>См. также

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
