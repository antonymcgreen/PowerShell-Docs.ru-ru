---
title: Элемент Дефаултсеттингс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787739"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DisplayError (формат)](./displayerror-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что строка #ERR отображается при возникновении ошибки при отображении фрагмента данных.|
|[Элемент EnumerableExpansions (формат)](./enumerableexpansions-element-format.md)|Необязательный элемент.<br /><br /> Определяет различные способы развертывания объектов .NET при их отображении в представлении.|
|[Пропертикаунтфортабле (формат)](./propertycountfortable-element-format.md)|Необязательный элемент.<br /><br /> Указывает минимальное число свойств, которое должен иметь объект для отображения объекта в табличном представлении.|
|[Элемент ShowError (формат)](./showerror-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что полная запись об ошибке отображается при возникновении ошибки при отображении фрагмента данных.|
|[Элемент WrapTables (формат)](./wraptables-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что данные в таблице перемещаются на следующую строку, если она не умещается в ширину столбца.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Элемент Configuration](./configuration-element-format.md)

[Элемент DisplayError (формат)](./displayerror-element-format.md)

[Элемент EnumerableExpansions (формат)](./enumerableexpansions-element-format.md)

[Пропертикаунтфортабле (формат)](./propertycountfortable-element-format.md)

[Элемент ShowError (формат)](./showerror-element-format.md)

[Элемент WrapTables (формат)](./wraptables-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
