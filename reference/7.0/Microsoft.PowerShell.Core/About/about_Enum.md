---
description: '`enum`Оператор используется для объявления перечисления. Перечисление — это отдельный тип, состоящий из набора именованных меток, которые называются списком перечислителей.'
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 9cd4f60db2903bc4ede6b0c3ad738b3137b87191
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232606"
---
# <a name="about-enum"></a>О перечислении

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
`enum`Оператор используется для объявления перечисления. Перечисление — это отдельный тип, состоящий из набора именованных меток, которые называются списком перечислителей.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

`enum`Оператор позволяет создать строго типизированный набор меток. Это перечисление может использоваться в коде без необходимости анализировать или проверять орфографические ошибки.

Перечисления внутренне представляются как целые числа с начальным значением 0. Первой метке в списке присваивается нулевое значение. Остальные метки присваиваются последовательным числам.

В определении меткам можно присвоить любое целочисленное значение. Метки без присвоения значения принимают следующее целочисленное значение.

## <a name="syntax-basic"></a>Синтаксис (базовый)

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a>Пример использования

В следующем примере показано перечисление объектов, которые можно увидеть как файлы мультимедиа. Определение присваивает явные значения базовым значениям `music` , `picture` , `video` . Метки сразу после явного присваивания получают следующее целочисленное значение. Синонимы можно создать, назначив одно и то же значение другой метке. см. сформированные значения для: `ogg` , `oga` , `mogg` или `jpg` , `jpeg` или, `mpg` `mpeg` .

```powershell
enum MediaTypes {
    unknown
    music = 10
    mp3
    aac
    ogg = 15
    oga = 15
    mogg = 15
    picture = 20
    jpg
    jpeg = 21
    png
    video = 40
    mpg
    mpeg = 41
    avi
    m4v
}
```

`GetEnumNames()`Метод возвращает список меток для перечисления.

```powershell
[MediaTypes].GetEnumNames()
unknown
music
mp3
aac
ogg
oga
mogg
picture
jpg
jpeg
png
video
mpg
mpeg
avi
m4v
```

`GetEnumValues()`Метод возвращает список значений для перечисления.

```powershell
[MediaTypes].GetEnumValues()
unknown
music
mp3
aac
oga
oga
oga
picture
jpeg
jpeg
png
video
mpeg
mpeg
avi
m4v
```

**Примечание**. Похоже, что жетенумнамес () и жетенумвалуес () возвращают те же результаты.
Однако для внутренних целей PowerShell изменяет значения на метки. Внимательно прочтите список, и вы заметите, что `oga` и `mogg` они упоминаются в результатах "Get Names", но не ниже, чем в выходных данных "получение значений" для `jpg` , `jpeg` и `mpg` `mpeg` .

```powershell
[MediaTypes].GetEnumName(15)
oga

[MediaTypes].GetEnumNames() | ForEach-Object {
  "{0,-10} {1}" -f $_,[int]([MediaTypes]::$_)
}
unknown    0
music      10
mp3        11
aac        12
ogg        15
oga        15
mogg       15
picture    20
jpg        21
jpeg       21
png        22
video      40
mpg        41
mpeg       41
avi        42
m4v        43
```

## <a name="enumerations-as-flags"></a>Перечисления в качестве флагов

Перечисления могут быть определены как коллекция битовых флагов.
Где, в любой момент, перечисление представляет один или несколько включенных флагов.

Для правильной работы перечислений в качестве флагов каждая метка должна иметь степень двух значений.

## <a name="syntax-flags"></a>Синтаксис (флаги)

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a>Пример использования флагов

В следующем примере создается перечисление *FileAttributes* .

```powershell
[Flags()] enum FileAttributes {
    Archive = 1
    Compressed = 2
    Device = 4
    Directory = 8
    Encrypted = 16
    Hidden = 32
}

[FileAttributes]$file1 = [FileAttributes]::Archive
[FileAttributes]$file1 +=[FileAttributes]::Compressed
[FileAttributes]$file1 +=  [FileAttributes]::Device
"file1 attributes are: $file1"

[FileAttributes]$file2 = [FileAttributes]28 ## => 16 + 8 + 4
"file2 attributes are: $file2"
```

```output
file1 attributes are: Archive, Compressed, Device
file2 attributes are: Device, Directory, Encrypted
```

Для проверки того, что определено конкретное значение, можно использовать бинарный оператор сравнения `-band` . В этом примере мы проверяем для **устройства** и атрибуты **архива** в значении `$file2` .

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```
