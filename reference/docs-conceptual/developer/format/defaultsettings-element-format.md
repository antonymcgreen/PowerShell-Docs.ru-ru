---
title: Элемент Дефаултсеттингс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363873"
---
# <a name="defaultsettings-element-format"></a>Элемент DefaultSettings (формат)

Определяет общие параметры, которые применяются ко всем представлениям файла форматирования. К общим параметрам относятся отображение ошибок, перенос текста в таблицы, определение порядка развертывания коллекций и многое другое.

Элемент Configuration (Format) Дефаултсеттингс (формат)

## <a name="syntax"></a>Синтаксис

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `DefaultSettings`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DisplayError (Format)](./displayerror-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.|
|[Элемент Енумерабликспансионс (Format)](./enumerableexpansions-element-format.md)|Необязательный элемент.<br /><br /> Определяет различные способы развертывания объектов .NET при их отображении в представлении.|
|[Пропертикаунтфортабле (формат)](./propertycountfortable-element-format.md)|Необязательный элемент.<br /><br /> Указывает минимальное число свойств, которое должен иметь объект для отображения объекта в табличном представлении.|
|[Элемент ShowError (Format)](./showerror-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что полная запись об ошибке отображается при возникновении ошибки при отображении фрагмента данных.|
|[Элемент Враптаблес (Format)](./wraptables-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что данные в таблице перемещаются на следующую строку, если она не умещается в ширину столбца.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также:

[Элемент Configuration](./configuration-element-format.md)

[Элемент DisplayError (Format)](./displayerror-element-format.md)

[Элемент Енумерабликспансионс (Format)](./enumerableexpansions-element-format.md)

[Пропертикаунтфортабле (формат)](./propertycountfortable-element-format.md)

[Элемент ShowError (Format)](./showerror-element-format.md)

[Элемент Враптаблес (Format)](./wraptables-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
