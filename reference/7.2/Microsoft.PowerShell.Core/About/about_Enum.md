---
description: '`enum`Оператор используется для объявления перечисления. Перечисление — это отдельный тип, состоящий из набора именованных меток, которые называются списком перечислителей.'
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 5572a717bbf9b546a30b227b3baf215196c4145d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602295"
---
# <a name="about-enum"></a><span data-ttu-id="8bfff-104">О перечислении</span><span class="sxs-lookup"><span data-stu-id="8bfff-104">About Enum</span></span>

## <a name="short-description"></a><span data-ttu-id="8bfff-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8bfff-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8bfff-106">`enum`Оператор используется для объявления перечисления.</span><span class="sxs-lookup"><span data-stu-id="8bfff-106">The `enum` statement is used to declare an enumeration.</span></span> <span data-ttu-id="8bfff-107">Перечисление — это отдельный тип, состоящий из набора именованных меток, которые называются списком перечислителей.</span><span class="sxs-lookup"><span data-stu-id="8bfff-107">An enumeration is a distinct type that consists of a set of named labels called the enumerator list.</span></span>

## <a name="long-description"></a><span data-ttu-id="8bfff-108">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8bfff-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="8bfff-109">`enum`Оператор позволяет создать строго типизированный набор меток.</span><span class="sxs-lookup"><span data-stu-id="8bfff-109">The `enum` statement allows you to create a strongly typed set of labels.</span></span> <span data-ttu-id="8bfff-110">Это перечисление может использоваться в коде без необходимости анализировать или проверять орфографические ошибки.</span><span class="sxs-lookup"><span data-stu-id="8bfff-110">That enumeration can be used in the code without having to parse or check for spelling errors.</span></span>

<span data-ttu-id="8bfff-111">Перечисления внутренне представляются как целые числа с начальным значением 0.</span><span class="sxs-lookup"><span data-stu-id="8bfff-111">Enumerations are internally represented as integers with a starting value of zero.</span></span> <span data-ttu-id="8bfff-112">Первой метке в списке присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="8bfff-112">The first label in the list is assigned the value zero.</span></span> <span data-ttu-id="8bfff-113">Остальные метки присваиваются последовательным числам.</span><span class="sxs-lookup"><span data-stu-id="8bfff-113">The remaining labels are assigned with consecutive numbers.</span></span>

<span data-ttu-id="8bfff-114">В определении меткам можно присвоить любое целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="8bfff-114">In the definition, labels can be given any integer value.</span></span> <span data-ttu-id="8bfff-115">Метки без присвоения значения принимают следующее целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="8bfff-115">Labels with no value assigned take the next integer value.</span></span>

## <a name="syntax-basic"></a><span data-ttu-id="8bfff-116">Синтаксис (базовый)</span><span class="sxs-lookup"><span data-stu-id="8bfff-116">Syntax (basic)</span></span>

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a><span data-ttu-id="8bfff-117">Пример использования</span><span class="sxs-lookup"><span data-stu-id="8bfff-117">Usage example</span></span>

<span data-ttu-id="8bfff-118">В следующем примере показано перечисление объектов, которые можно увидеть как файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8bfff-118">The following example shows an enumeration of objects that can be seen as media files.</span></span> <span data-ttu-id="8bfff-119">Определение присваивает явные значения базовым значениям `music` , `picture` , `video` .</span><span class="sxs-lookup"><span data-stu-id="8bfff-119">The definition assigns explicit values to the underlying values of `music`, `picture`, `video`.</span></span> <span data-ttu-id="8bfff-120">Метки сразу после явного присваивания получают следующее целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="8bfff-120">Labels immediately following an explicit assignment get the next integer value.</span></span> <span data-ttu-id="8bfff-121">Синонимы можно создать, назначив одно и то же значение другой метке. см. сформированные значения для: `ogg` , `oga` , `mogg` или `jpg` , `jpeg` или, `mpg` `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="8bfff-121">Synonyms can be created by assigning the same value to another label; see the constructed values for: `ogg`, `oga`, `mogg`, or `jpg`, `jpeg`, or `mpg`, `mpeg`.</span></span>

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

<span data-ttu-id="8bfff-122">`GetEnumNames()`Метод возвращает список меток для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8bfff-122">The `GetEnumNames()` method returns the list of the labels for the enumeration.</span></span>

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

<span data-ttu-id="8bfff-123">`GetEnumValues()`Метод возвращает список значений для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8bfff-123">The `GetEnumValues()` method returns the list of the values for the enumeration.</span></span>

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

<span data-ttu-id="8bfff-124">**Примечание**. Похоже, что жетенумнамес () и жетенумвалуес () возвращают те же результаты.</span><span class="sxs-lookup"><span data-stu-id="8bfff-124">**Note**: GetEnumNames() and GetEnumValues() seem to return the same results.</span></span>
<span data-ttu-id="8bfff-125">Однако для внутренних целей PowerShell изменяет значения на метки.</span><span class="sxs-lookup"><span data-stu-id="8bfff-125">However, internally, PowerShell is changing values into labels.</span></span> <span data-ttu-id="8bfff-126">Внимательно прочтите список, и вы заметите, что `oga` и `mogg` они упоминаются в результатах "Get Names", но не ниже, чем в выходных данных "получение значений" для `jpg` , `jpeg` и `mpg` `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="8bfff-126">Read the list carefully and you'll notice that `oga` and `mogg` are mentioned under the 'Get Names' results, but not under the 'Get Values' similar output for `jpg`, `jpeg`, and `mpg`, `mpeg`.</span></span>

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

## <a name="enumerations-as-flags"></a><span data-ttu-id="8bfff-127">Перечисления в качестве флагов</span><span class="sxs-lookup"><span data-stu-id="8bfff-127">Enumerations as flags</span></span>

<span data-ttu-id="8bfff-128">Перечисления могут быть определены как коллекция битовых флагов.</span><span class="sxs-lookup"><span data-stu-id="8bfff-128">Enumerations can be defined as a collection of bit flags.</span></span>
<span data-ttu-id="8bfff-129">Где, в любой момент, перечисление представляет один или несколько включенных флагов.</span><span class="sxs-lookup"><span data-stu-id="8bfff-129">Where, at any given point the enumeration represents one or more of those flags turned on.</span></span>

<span data-ttu-id="8bfff-130">Для правильной работы перечислений в качестве флагов каждая метка должна иметь степень двух значений.</span><span class="sxs-lookup"><span data-stu-id="8bfff-130">For enumerations as flags to work properly, each label should have a power of two value.</span></span>

## <a name="syntax-flags"></a><span data-ttu-id="8bfff-131">Синтаксис (флаги)</span><span class="sxs-lookup"><span data-stu-id="8bfff-131">Syntax (flags)</span></span>

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a><span data-ttu-id="8bfff-132">Пример использования флагов</span><span class="sxs-lookup"><span data-stu-id="8bfff-132">Flags usage example</span></span>

<span data-ttu-id="8bfff-133">В следующем примере создается перечисление *FileAttributes* .</span><span class="sxs-lookup"><span data-stu-id="8bfff-133">In the following example the *FileAttributes* enumeration is created.</span></span>

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

<span data-ttu-id="8bfff-134">Для проверки того, что определено конкретное значение, можно использовать бинарный оператор сравнения `-band` .</span><span class="sxs-lookup"><span data-stu-id="8bfff-134">To test that a specific is set, you can use the binary comparison operator `-band`.</span></span> <span data-ttu-id="8bfff-135">В этом примере мы проверяем для **устройства** и атрибуты **архива** в значении `$file2` .</span><span class="sxs-lookup"><span data-stu-id="8bfff-135">In this example, we test for the **Device** and the **Archive** attributes in the value of `$file2`.</span></span>

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```

