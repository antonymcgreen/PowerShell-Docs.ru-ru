---
title: Элемент DefaultSettings (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059071"
---
# <a name="defaultsettings-element-format"></a>Элемент DefaultSettings (формат)

Определяет общие параметры, которые применяются ко всем представлениям форматирования файла. Общие параметры включают отображение ошибок, переноса текста в таблицах, определение развернуты как коллекции и многое другое.

Элемент DefaultSettings конфигурации элемент (формат) (формат)

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

Ниже описаны атрибуты, дочерние элементы и родительский элемент `DefaultSettings` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент DisplayError (формат)](./displayerror-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что строка #ERR отображаются при возникновении ошибки при отображении фрагмента данных.|
|[Элемент EnumerableExpansions (формат)](./enumerableexpansions-element-format.md)|Необязательный элемент.<br /><br /> Определяет, что объекты .NET, разворачиваются, когда они отображаются в представлении различным образом.|
|[PropertyCountForTable (формат)](./propertycountfortable-element-format.md)|Необязательный элемент.<br /><br /> Указывает минимальное число свойств, которые объект должен иметь для отображения объекта в табличном представлении.|
|[Элемент ShowError (формат)](./showerror-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что запись об ошибке полный отображаются при возникновении ошибки при отображении фрагмента данных.|
|[Элемент WrapTables (формат)](./wraptables-element-format.md)|Необязательный элемент.<br /><br /> Указывает, что данные в таблице перемещается на следующую строку, если оно не поместится в ширину столбца.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент конфигурации](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Замечания

## <a name="see-also"></a>См. также

[Элемент конфигурации](./configuration-element-format.md)

[Элемент DisplayError (формат)](./displayerror-element-format.md)

[Элемент EnumerableExpansions (формат)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (формат)](./propertycountfortable-element-format.md)

[Элемент ShowError (формат)](./showerror-element-format.md)

[Элемент WrapTables (формат)](./wraptables-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
