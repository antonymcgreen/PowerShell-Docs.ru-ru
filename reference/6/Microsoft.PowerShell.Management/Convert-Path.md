---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: c7ab1143b406af08c921d2ce27c5c60470b2f11e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226938"
---
# <span data-ttu-id="3114d-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="3114d-103">Convert-Path</span></span>

## <span data-ttu-id="3114d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3114d-104">SYNOPSIS</span></span>
<span data-ttu-id="3114d-105">Преобразует путь из пути PowerShell в путь поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3114d-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="3114d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3114d-106">SYNTAX</span></span>

### <span data-ttu-id="3114d-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3114d-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="3114d-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3114d-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="3114d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3114d-109">DESCRIPTION</span></span>

<span data-ttu-id="3114d-110">`Convert-Path`Командлет преобразует путь из пути PowerShell в путь поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3114d-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="3114d-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3114d-111">EXAMPLES</span></span>

### <span data-ttu-id="3114d-112">Пример 1. преобразование рабочего каталога в стандартный путь файловой системы</span><span class="sxs-lookup"><span data-stu-id="3114d-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="3114d-113">В этом примере текущий рабочий каталог, представленный точкой (), преобразуется `.` в стандартный путь файловой системы.</span><span class="sxs-lookup"><span data-stu-id="3114d-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="3114d-114">Пример 2. преобразование пути поставщика в стандартный путь реестра</span><span class="sxs-lookup"><span data-stu-id="3114d-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="3114d-115">В этом примере путь к поставщику PowerShell преобразуется в стандартный путь реестра.</span><span class="sxs-lookup"><span data-stu-id="3114d-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="3114d-116">Пример 3. преобразование пути в строку</span><span class="sxs-lookup"><span data-stu-id="3114d-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="3114d-117">В этом примере путь преобразуется в корневой каталог текущего поставщика, который является поставщиком FileSystem, в строку.</span><span class="sxs-lookup"><span data-stu-id="3114d-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="3114d-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3114d-118">PARAMETERS</span></span>

### <span data-ttu-id="3114d-119">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3114d-119">-LiteralPath</span></span>

<span data-ttu-id="3114d-120">Указывает преобразуемый путь в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="3114d-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="3114d-121">Значение параметра **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="3114d-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="3114d-122">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="3114d-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3114d-123">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="3114d-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3114d-124">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="3114d-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3114d-125">-Path</span><span class="sxs-lookup"><span data-stu-id="3114d-125">-Path</span></span>

<span data-ttu-id="3114d-126">Указывает путь PowerShell для преобразования.</span><span class="sxs-lookup"><span data-stu-id="3114d-126">Specifies the PowerShell path to be converted.</span></span>

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

### <span data-ttu-id="3114d-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3114d-127">CommonParameters</span></span>

<span data-ttu-id="3114d-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3114d-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3114d-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3114d-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3114d-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3114d-130">INPUTS</span></span>

### <span data-ttu-id="3114d-131">System.String</span><span class="sxs-lookup"><span data-stu-id="3114d-131">System.String</span></span>

<span data-ttu-id="3114d-132">В этот командлет можно передать по конвейеру путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="3114d-132">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="3114d-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3114d-133">OUTPUTS</span></span>

### <span data-ttu-id="3114d-134">System.String</span><span class="sxs-lookup"><span data-stu-id="3114d-134">System.String</span></span>

<span data-ttu-id="3114d-135">Этот командлет возвращает строку, содержащую преобразованный путь.</span><span class="sxs-lookup"><span data-stu-id="3114d-135">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="3114d-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3114d-136">NOTES</span></span>

<span data-ttu-id="3114d-137">Командлеты, которые содержат существительное пути, управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3114d-137">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="3114d-138">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="3114d-138">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="3114d-139">Используйте их, например **dirname** , **нормпас** , **реалпас** , **Join** или другие манипуляторы пути.</span><span class="sxs-lookup"><span data-stu-id="3114d-139">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="3114d-140">Командлеты для работы с путями можно использовать с различными поставщиками, включая FileSystem, Registry и Certificate.</span><span class="sxs-lookup"><span data-stu-id="3114d-140">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="3114d-141">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="3114d-141">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3114d-142">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="3114d-142">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3114d-143">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3114d-143">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="3114d-144">`Convert-Path` преобразует только существующие пути.</span><span class="sxs-lookup"><span data-stu-id="3114d-144">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="3114d-145">Его нельзя использовать для преобразования расположения, которое еще не существует.</span><span class="sxs-lookup"><span data-stu-id="3114d-145">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="3114d-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3114d-146">RELATED LINKS</span></span>

[<span data-ttu-id="3114d-147">Join-Path</span><span class="sxs-lookup"><span data-stu-id="3114d-147">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="3114d-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="3114d-148">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="3114d-149">Split-Path</span><span class="sxs-lookup"><span data-stu-id="3114d-149">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="3114d-150">Test-Path</span><span class="sxs-lookup"><span data-stu-id="3114d-150">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="3114d-151">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="3114d-151">Get-PSProvider</span></span>](Get-PSProvider.md)
