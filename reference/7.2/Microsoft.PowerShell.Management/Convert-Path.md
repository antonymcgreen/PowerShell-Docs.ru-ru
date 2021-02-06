---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: 3d39ea9498cec2669fa075d4630b7691671fea32
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602500"
---
# <span data-ttu-id="f6820-102">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="f6820-102">Convert-Path</span></span>

## <span data-ttu-id="f6820-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f6820-103">SYNOPSIS</span></span>
<span data-ttu-id="f6820-104">Преобразует путь из пути PowerShell в путь поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6820-104">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="f6820-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f6820-105">SYNTAX</span></span>

### <span data-ttu-id="f6820-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f6820-106">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="f6820-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f6820-107">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="f6820-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f6820-108">DESCRIPTION</span></span>

<span data-ttu-id="f6820-109">`Convert-Path`Командлет преобразует путь из пути PowerShell в путь поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6820-109">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="f6820-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="f6820-110">EXAMPLES</span></span>

### <span data-ttu-id="f6820-111">Пример 1. преобразование рабочего каталога в стандартный путь файловой системы</span><span class="sxs-lookup"><span data-stu-id="f6820-111">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="f6820-112">В этом примере текущий рабочий каталог, представленный точкой (), преобразуется `.` в стандартный путь файловой системы.</span><span class="sxs-lookup"><span data-stu-id="f6820-112">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="f6820-113">Пример 2. преобразование пути поставщика в стандартный путь реестра</span><span class="sxs-lookup"><span data-stu-id="f6820-113">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="f6820-114">В этом примере путь к поставщику PowerShell преобразуется в стандартный путь реестра.</span><span class="sxs-lookup"><span data-stu-id="f6820-114">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="f6820-115">Пример 3. преобразование пути в строку</span><span class="sxs-lookup"><span data-stu-id="f6820-115">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="f6820-116">В этом примере путь преобразуется в корневой каталог текущего поставщика, который является поставщиком FileSystem, в строку.</span><span class="sxs-lookup"><span data-stu-id="f6820-116">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="f6820-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f6820-117">PARAMETERS</span></span>

### <span data-ttu-id="f6820-118">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f6820-118">-LiteralPath</span></span>

<span data-ttu-id="f6820-119">Указывает преобразуемый путь в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="f6820-119">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="f6820-120">Значение параметра **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="f6820-120">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f6820-121">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="f6820-121">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f6820-122">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="f6820-122">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f6820-123">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f6820-123">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f6820-124">-Path</span><span class="sxs-lookup"><span data-stu-id="f6820-124">-Path</span></span>

<span data-ttu-id="f6820-125">Указывает путь PowerShell для преобразования.</span><span class="sxs-lookup"><span data-stu-id="f6820-125">Specifies the PowerShell path to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f6820-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f6820-126">CommonParameters</span></span>

<span data-ttu-id="f6820-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f6820-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f6820-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f6820-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f6820-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f6820-129">INPUTS</span></span>

### <span data-ttu-id="f6820-130">System.String</span><span class="sxs-lookup"><span data-stu-id="f6820-130">System.String</span></span>

<span data-ttu-id="f6820-131">В этот командлет можно передать по конвейеру путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="f6820-131">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="f6820-132">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f6820-132">OUTPUTS</span></span>

### <span data-ttu-id="f6820-133">System.String</span><span class="sxs-lookup"><span data-stu-id="f6820-133">System.String</span></span>

<span data-ttu-id="f6820-134">Этот командлет возвращает строку, содержащую преобразованный путь.</span><span class="sxs-lookup"><span data-stu-id="f6820-134">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="f6820-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f6820-135">NOTES</span></span>

<span data-ttu-id="f6820-136">Командлеты, которые содержат существительное пути, управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6820-136">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="f6820-137">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="f6820-137">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="f6820-138">Используйте их, например **dirname**, **нормпас**, **реалпас**, **Join** или другие манипуляторы пути.</span><span class="sxs-lookup"><span data-stu-id="f6820-138">Use them like you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

<span data-ttu-id="f6820-139">Командлеты для работы с путями можно использовать с различными поставщиками, включая FileSystem, Registry и Certificate.</span><span class="sxs-lookup"><span data-stu-id="f6820-139">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="f6820-140">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="f6820-140">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f6820-141">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="f6820-141">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="f6820-142">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f6820-142">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="f6820-143">`Convert-Path` преобразует только существующие пути.</span><span class="sxs-lookup"><span data-stu-id="f6820-143">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="f6820-144">Его нельзя использовать для преобразования расположения, которое еще не существует.</span><span class="sxs-lookup"><span data-stu-id="f6820-144">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="f6820-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f6820-145">RELATED LINKS</span></span>

[<span data-ttu-id="f6820-146">Join-Path</span><span class="sxs-lookup"><span data-stu-id="f6820-146">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="f6820-147">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="f6820-147">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="f6820-148">Split-Path</span><span class="sxs-lookup"><span data-stu-id="f6820-148">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="f6820-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="f6820-149">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="f6820-150">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f6820-150">Get-PSProvider</span></span>](Get-PSProvider.md)

