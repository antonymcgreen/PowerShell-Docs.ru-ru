---
title: Приложение А. Синтаксис справки
description: В этой статье объясняется, как читать и распознавать синтаксис командлета, представленного Get-Help.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: b8fe218f2a9af1ad1ee6b88740414ecede0194bd
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99605515"
---
# <a name="appendix-a---help-syntax"></a><span data-ttu-id="8a7b4-103">Приложение А. Синтаксис справки</span><span class="sxs-lookup"><span data-stu-id="8a7b4-103">Appendix A - Help Syntax</span></span>

<span data-ttu-id="8a7b4-104">В следующем примере показан раздел справки **SYNTAX** командлета `Get-EventLog`.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-104">The following example shows the **SYNTAX** section of the help for the `Get-EventLog` cmdlet.</span></span>

```powershell
help Get-EventLog
```

```Output
NAME
    Get-EventLog

SYNOPSIS
    Gets the events in an event log, or a list of the event logs, on the local or remote
    computers.


SYNTAX
    Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>]
    [-AsBaseObject] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType {Error |
    Information | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message
    <String>] [-Newest <Int32>] [-Source <String[]>] [-UserName <String[]>]
    [<CommonParameters>]

    Get-EventLog [-AsString] [-ComputerName <String[]>] [-List] [<CommonParameters>]
```

<span data-ttu-id="8a7b4-105">В этом примере показана только соответствующая часть справки.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-105">Only the relevant portion of the help is shown in this example.</span></span>

<span data-ttu-id="8a7b4-106">Синтаксис в основном состоит из нескольких наборов открывающих и закрывающих скобок (`[]`).</span><span class="sxs-lookup"><span data-stu-id="8a7b4-106">The syntax is primarily made up of several sets of opening and closing brackets (`[]`).</span></span> <span data-ttu-id="8a7b4-107">Они имеют два разных значения в зависимости от способа использования.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-107">These have two different meanings depending on how they're used.</span></span> <span data-ttu-id="8a7b4-108">Любые символы, заключенные в квадратные скобки, являются необязательными, если только это не набор пустых квадратных скобок `[]`.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-108">Anything contained within square brackets is optional unless they're a set of empty square brackets `[]`.</span></span> <span data-ttu-id="8a7b4-109">Пустые квадратные скобки появляются только после того, как указывается такой тип данных, как `<string[]>`.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-109">Empty square brackets only appear after a datatype such as `<string[]>`.</span></span> <span data-ttu-id="8a7b4-110">Это означает, что именно этот параметр может принимать более одного значения указанного типа данных.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-110">This means that particular parameter can accept more than one value of that type.</span></span>

<span data-ttu-id="8a7b4-111">Первым параметром в первом наборе параметров `Get-EventLog` является **LogName**.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-111">The first parameter in the first parameter set of `Get-EventLog` is **LogName**.</span></span> <span data-ttu-id="8a7b4-112">Параметр LogName заключен в квадратные скобки, а это значит, что он позиционный.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-112">LogName is surrounded by square brackets which means that it's a positional parameter.</span></span> <span data-ttu-id="8a7b4-113">Другими словами, указывать имя самого параметра необязательно, если оно указано в правильном положении.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-113">In other words, specifying the name of the parameter itself is optional as long as it's specified in the correct position.</span></span> <span data-ttu-id="8a7b4-114">Данные в угловых скобках (`<>`) после имени параметра означают, что для него требуется указать отдельное **строковое** значение.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-114">The information in the angle brackets (`<>`) after the parameter name indicates that it needs a single **string** value.</span></span> <span data-ttu-id="8a7b4-115">Имя параметра целиком и тип данных не заключены в квадратные скобки, поэтому при использовании этого набора параметров требуется указать параметр **LogName**.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-115">The entire parameter name and datatype are not surrounded by square brackets so the **LogName** parameter is required when using this parameter set.</span></span>

```powershell
Get-EventLog [-LogName] <String>
```

<span data-ttu-id="8a7b4-116">Вторым параметром является **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-116">The second parameter is **InstanceId**.</span></span> <span data-ttu-id="8a7b4-117">Заметьте, что и имя параметра, и тип данных полностью заключены в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-117">Notice that the parameter name and the datatype are both completely surrounded by square brackets.</span></span> <span data-ttu-id="8a7b4-118">Это означает, что параметр **InstanceId** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-118">This means that the **InstanceId** parameter is optional, not mandatory.</span></span> <span data-ttu-id="8a7b4-119">Кроме того, заметьте, что параметр **InstanceId** заключен в собственный набор квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-119">Also notice that **InstanceId** is surrounded by its own set of square brackets.</span></span> <span data-ttu-id="8a7b4-120">Как и в случае с параметром **LogName**, это означает, что он позиционный.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-120">As with the **LogName** parameter, this means the parameter is positional.</span></span> <span data-ttu-id="8a7b4-121">После типа данных указан последний набор квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-121">There's one last set of square brackets after the datatype.</span></span> <span data-ttu-id="8a7b4-122">Это означает, что он может принимать более одного значения в виде массива или списка, элементы которого разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-122">This means that it can accept more than one value in the form of an array or a comma-separated list.</span></span>

```
[[-InstanceId] <Int64[]>]
```

<span data-ttu-id="8a7b4-123">Второй набор параметров содержит параметр **List**.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-123">The second parameter set has a **List** parameter.</span></span> <span data-ttu-id="8a7b4-124">Это параметр-переключатель, потому что после имени параметра тип данных не указан.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-124">It's a switch parameter because there's no datatype following the parameter name.</span></span> <span data-ttu-id="8a7b4-125">Если параметр **List** указан, появится значение **True**,</span><span class="sxs-lookup"><span data-stu-id="8a7b4-125">When the **List** parameter is specified, the value is **True**.</span></span> <span data-ttu-id="8a7b4-126">если не указан, появится значение **False**.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-126">When it's not specified, the value is **False**.</span></span>

```
[-List]
```

<span data-ttu-id="8a7b4-127">Сведения о синтаксисе для команды также можно получить с помощью `Get-Command` с использованием параметра **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-127">The syntax information for a command can also be retrieved using `Get-Command` using the **Syntax** parameter.</span></span> <span data-ttu-id="8a7b4-128">Это удобный ярлык, который я постоянно использую.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-128">This is a handy shortcut that I use all the time.</span></span> <span data-ttu-id="8a7b4-129">Он позволяет мне быстро узнать, как использовать команду, не вынуждая проверять несколько страниц справочной информации.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-129">It allows me to quickly learn how to use a command without having to sift through multiple pages of help information.</span></span> <span data-ttu-id="8a7b4-130">Если мне в итоге потребуются дополнительные сведения, я буду использовать фактическое содержимое справки.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-130">If I end up needing more information, then I'll revert to using the actual help content.</span></span>

```powershell
Get-Command -Name Get-EventLog -Syntax
```

```Output
Get-EventLog [-LogName] <string> [[-InstanceId] <long[]>] [-ComputerName <string[]>] [-Newest <int>]
 [-After <datetime>] [-Before <datetime>] [-UserName <string[]>] [-Index <int[]> ]
 [-EntryType <string[]>] [-Source <string[]>] [-Message <string>] [-AsBaseObject]
 [<CommonParameters>]

Get-EventLog [-ComputerName <string[]>] [-List] [-AsString] [<CommonParameters>]
```

<span data-ttu-id="8a7b4-131">Чем чаще вы используете справочную систему в PowerShell, тем проще становится запомнить разные нюансы.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-131">The more you use the help system in PowerShell, the easier remembering all of the different nuances becomes.</span></span> <span data-ttu-id="8a7b4-132">Когда вы освоите систему, использовать ее будет привычным делом.</span><span class="sxs-lookup"><span data-stu-id="8a7b4-132">Before you know it, using it becomes second nature.</span></span>
