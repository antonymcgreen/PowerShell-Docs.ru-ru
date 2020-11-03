---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: a442d8ff9f021e1ec05671d9190d35ef97ff4d72
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228437"
---
# <span data-ttu-id="bfbce-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="bfbce-103">Convert-Path</span></span>

## <span data-ttu-id="bfbce-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bfbce-104">SYNOPSIS</span></span>
<span data-ttu-id="bfbce-105">Преобразует путь из пути PowerShell в путь поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfbce-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="bfbce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bfbce-106">SYNTAX</span></span>

### <span data-ttu-id="bfbce-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bfbce-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="bfbce-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bfbce-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="bfbce-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bfbce-109">DESCRIPTION</span></span>

<span data-ttu-id="bfbce-110">`Convert-Path`Командлет преобразует путь из пути PowerShell в путь поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfbce-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="bfbce-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="bfbce-111">EXAMPLES</span></span>

### <span data-ttu-id="bfbce-112">Пример 1. преобразование рабочего каталога в стандартный путь файловой системы</span><span class="sxs-lookup"><span data-stu-id="bfbce-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="bfbce-113">В этом примере текущий рабочий каталог, представленный точкой (), преобразуется `.` в стандартный путь файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bfbce-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="bfbce-114">Пример 2. преобразование пути поставщика в стандартный путь реестра</span><span class="sxs-lookup"><span data-stu-id="bfbce-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="bfbce-115">В этом примере путь к поставщику PowerShell преобразуется в стандартный путь реестра.</span><span class="sxs-lookup"><span data-stu-id="bfbce-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="bfbce-116">Пример 3. преобразование пути в строку</span><span class="sxs-lookup"><span data-stu-id="bfbce-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="bfbce-117">В этом примере путь преобразуется в корневой каталог текущего поставщика, который является поставщиком FileSystem, в строку.</span><span class="sxs-lookup"><span data-stu-id="bfbce-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="bfbce-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bfbce-118">PARAMETERS</span></span>

### <span data-ttu-id="bfbce-119">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bfbce-119">-LiteralPath</span></span>

<span data-ttu-id="bfbce-120">Указывает преобразуемый путь в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="bfbce-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="bfbce-121">Значение параметра **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="bfbce-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="bfbce-122">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="bfbce-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="bfbce-123">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="bfbce-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="bfbce-124">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="bfbce-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bfbce-125">-Path</span><span class="sxs-lookup"><span data-stu-id="bfbce-125">-Path</span></span>

<span data-ttu-id="bfbce-126">Указывает путь PowerShell для преобразования.</span><span class="sxs-lookup"><span data-stu-id="bfbce-126">Specifies the PowerShell path to be converted.</span></span>

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

### <span data-ttu-id="bfbce-127">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="bfbce-127">-UseTransaction</span></span>
<span data-ttu-id="bfbce-128">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="bfbce-128">Includes the command in the active transaction.</span></span>
<span data-ttu-id="bfbce-129">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="bfbce-129">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="bfbce-130">Дополнительные сведения см. в разделе about_transactions.</span><span class="sxs-lookup"><span data-stu-id="bfbce-130">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bfbce-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bfbce-131">CommonParameters</span></span>

<span data-ttu-id="bfbce-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bfbce-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bfbce-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bfbce-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bfbce-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bfbce-134">INPUTS</span></span>

### <span data-ttu-id="bfbce-135">System.String</span><span class="sxs-lookup"><span data-stu-id="bfbce-135">System.String</span></span>

<span data-ttu-id="bfbce-136">В этот командлет можно передать по конвейеру путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="bfbce-136">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="bfbce-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bfbce-137">OUTPUTS</span></span>

### <span data-ttu-id="bfbce-138">System.String</span><span class="sxs-lookup"><span data-stu-id="bfbce-138">System.String</span></span>

<span data-ttu-id="bfbce-139">Этот командлет возвращает строку, содержащую преобразованный путь.</span><span class="sxs-lookup"><span data-stu-id="bfbce-139">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="bfbce-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bfbce-140">NOTES</span></span>

<span data-ttu-id="bfbce-141">Командлеты, которые содержат существительное пути, управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfbce-141">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="bfbce-142">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="bfbce-142">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="bfbce-143">Используйте их, например **dirname** , **нормпас** , **реалпас** , **Join** или другие манипуляторы пути.</span><span class="sxs-lookup"><span data-stu-id="bfbce-143">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="bfbce-144">Командлеты для работы с путями можно использовать с различными поставщиками, включая FileSystem, Registry и Certificate.</span><span class="sxs-lookup"><span data-stu-id="bfbce-144">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="bfbce-145">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="bfbce-145">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="bfbce-146">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="bfbce-146">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="bfbce-147">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="bfbce-147">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="bfbce-148">`Convert-Path` преобразует только существующие пути.</span><span class="sxs-lookup"><span data-stu-id="bfbce-148">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="bfbce-149">Его нельзя использовать для преобразования расположения, которое еще не существует.</span><span class="sxs-lookup"><span data-stu-id="bfbce-149">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="bfbce-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bfbce-150">RELATED LINKS</span></span>

[<span data-ttu-id="bfbce-151">Join-Path</span><span class="sxs-lookup"><span data-stu-id="bfbce-151">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="bfbce-152">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="bfbce-152">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="bfbce-153">Split-Path</span><span class="sxs-lookup"><span data-stu-id="bfbce-153">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="bfbce-154">Test-Path</span><span class="sxs-lookup"><span data-stu-id="bfbce-154">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="bfbce-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="bfbce-155">Get-PSProvider</span></span>](Get-PSProvider.md)
