---
description: '`enum`Оператор используется для объявления перечисления. Перечисление — это отдельный тип, состоящий из набора именованных меток, которые называются списком перечислителей.'
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 2b363f1d2dfcf45ec69d863a50f5f359ddf8e284
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231509"
---
# <a name="about-enum"></a><span data-ttu-id="8c97b-105">О перечислении</span><span class="sxs-lookup"><span data-stu-id="8c97b-105">About Enum</span></span>

## <a name="short-description"></a><span data-ttu-id="8c97b-106">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8c97b-106">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8c97b-107">`enum`Оператор используется для объявления перечисления.</span><span class="sxs-lookup"><span data-stu-id="8c97b-107">The `enum` statement is used to declare an enumeration.</span></span> <span data-ttu-id="8c97b-108">Перечисление — это отдельный тип, состоящий из набора именованных меток, которые называются списком перечислителей.</span><span class="sxs-lookup"><span data-stu-id="8c97b-108">An enumeration is a distinct type that consists of a set of named labels called the enumerator list.</span></span>

## <a name="long-description"></a><span data-ttu-id="8c97b-109">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8c97b-109">LONG DESCRIPTION</span></span>

<span data-ttu-id="8c97b-110">`enum`Оператор позволяет создать строго типизированный набор меток.</span><span class="sxs-lookup"><span data-stu-id="8c97b-110">The `enum` statement allows you to create a strongly typed set of labels.</span></span> <span data-ttu-id="8c97b-111">Это перечисление может использоваться в коде без необходимости анализировать или проверять орфографические ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c97b-111">That enumeration can be used in the code without having to parse or check for spelling errors.</span></span>

<span data-ttu-id="8c97b-112">Перечисления внутренне представляются как целые числа с начальным значением 0.</span><span class="sxs-lookup"><span data-stu-id="8c97b-112">Enumerations are internally represented as integers with a starting value of zero.</span></span> <span data-ttu-id="8c97b-113">Первой метке в списке присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="8c97b-113">The first label in the list is assigned the value zero.</span></span> <span data-ttu-id="8c97b-114">Остальные метки присваиваются последовательным числам.</span><span class="sxs-lookup"><span data-stu-id="8c97b-114">The remaining labels are assigned with consecutive numbers.</span></span>

<span data-ttu-id="8c97b-115">В определении меткам можно присвоить любое целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="8c97b-115">In the definition, labels can be given any integer value.</span></span> <span data-ttu-id="8c97b-116">Метки без присвоения значения принимают следующее целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="8c97b-116">Labels with no value assigned take the next integer value.</span></span>

## <a name="syntax-basic"></a><span data-ttu-id="8c97b-117">Синтаксис (базовый)</span><span class="sxs-lookup"><span data-stu-id="8c97b-117">Syntax (basic)</span></span>

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a><span data-ttu-id="8c97b-118">Пример использования</span><span class="sxs-lookup"><span data-stu-id="8c97b-118">Usage example</span></span>

<span data-ttu-id="8c97b-119">В следующем примере показано перечисление объектов, которые можно увидеть как файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8c97b-119">The following example shows an enumeration of objects that can be seen as media files.</span></span> <span data-ttu-id="8c97b-120">Определение присваивает явные значения базовым значениям `music` , `picture` , `video` .</span><span class="sxs-lookup"><span data-stu-id="8c97b-120">The definition assigns explicit values to the underlying values of `music`, `picture`, `video`.</span></span> <span data-ttu-id="8c97b-121">Метки сразу после явного присваивания получают следующее целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="8c97b-121">Labels immediately following an explicit assignment get the next integer value.</span></span> <span data-ttu-id="8c97b-122">Синонимы можно создать, назначив одно и то же значение другой метке. см. сформированные значения для: `ogg` , `oga` , `mogg` или `jpg` , `jpeg` или, `mpg` `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="8c97b-122">Synonyms can be created by assigning the same value to another label; see the constructed values for: `ogg`, `oga`, `mogg`, or `jpg`, `jpeg`, or `mpg`, `mpeg`.</span></span>

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

<span data-ttu-id="8c97b-123">`GetEnumNames()`Метод возвращает список меток для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8c97b-123">The `GetEnumNames()` method returns the list of the labels for the enumeration.</span></span>

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

<span data-ttu-id="8c97b-124">`GetEnumValues()`Метод возвращает список значений для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8c97b-124">The `GetEnumValues()` method returns the list of the values for the enumeration.</span></span>

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

<span data-ttu-id="8c97b-125">**Примечание**. Похоже, что жетенумнамес () и жетенумвалуес () возвращают те же результаты.</span><span class="sxs-lookup"><span data-stu-id="8c97b-125">**Note** : GetEnumNames() and GetEnumValues() seem to return the same results.</span></span>
<span data-ttu-id="8c97b-126">Однако для внутренних целей PowerShell изменяет значения на метки.</span><span class="sxs-lookup"><span data-stu-id="8c97b-126">However, internally, PowerShell is changing values into labels.</span></span> <span data-ttu-id="8c97b-127">Внимательно прочтите список, и вы заметите, что `oga` и `mogg` они упоминаются в результатах "Get Names", но не ниже, чем в выходных данных "получение значений" для `jpg` , `jpeg` и `mpg` `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="8c97b-127">Read the list carefully and you'll notice that `oga` and `mogg` are mentioned under the 'Get Names' results, but not under the 'Get Values' similar output for `jpg`, `jpeg`, and `mpg`, `mpeg`.</span></span>

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

## <a name="enumerations-as-flags"></a><span data-ttu-id="8c97b-128">Перечисления в качестве флагов</span><span class="sxs-lookup"><span data-stu-id="8c97b-128">Enumerations as flags</span></span>

<span data-ttu-id="8c97b-129">Перечисления могут быть определены как коллекция битовых флагов.</span><span class="sxs-lookup"><span data-stu-id="8c97b-129">Enumerations can be defined as a collection of bit flags.</span></span>
<span data-ttu-id="8c97b-130">Где, в любой момент, перечисление представляет один или несколько включенных флагов.</span><span class="sxs-lookup"><span data-stu-id="8c97b-130">Where, at any given point the enumeration represents one or more of those flags turned on.</span></span>

<span data-ttu-id="8c97b-131">Для правильной работы перечислений в качестве флагов каждая метка должна иметь степень двух значений.</span><span class="sxs-lookup"><span data-stu-id="8c97b-131">For enumerations as flags to work properly, each label should have a power of two value.</span></span>

## <a name="syntax-flags"></a><span data-ttu-id="8c97b-132">Синтаксис (флаги)</span><span class="sxs-lookup"><span data-stu-id="8c97b-132">Syntax (flags)</span></span>

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a><span data-ttu-id="8c97b-133">Пример использования флагов</span><span class="sxs-lookup"><span data-stu-id="8c97b-133">Flags usage example</span></span>

<span data-ttu-id="8c97b-134">В следующем примере создается перечисление *FileAttributes* .</span><span class="sxs-lookup"><span data-stu-id="8c97b-134">In the following example the *FileAttributes* enumeration is created.</span></span>

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

<span data-ttu-id="8c97b-135">Для проверки того, что определено конкретное значение, можно использовать бинарный оператор сравнения `-band` .</span><span class="sxs-lookup"><span data-stu-id="8c97b-135">To test that a specific is set, you can use the binary comparison operator `-band`.</span></span> <span data-ttu-id="8c97b-136">В этом примере мы проверяем для **устройства** и атрибуты **архива** в значении `$file2` .</span><span class="sxs-lookup"><span data-stu-id="8c97b-136">In this example, we test for the **Device** and the **Archive** attributes in the value of `$file2`.</span></span>

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```
