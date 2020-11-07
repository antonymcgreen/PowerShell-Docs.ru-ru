---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 56fe7affdc6b64af53f179b438375fcec8f01227
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344139"
---
# <span data-ttu-id="b905a-103">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="b905a-103">Unblock-File</span></span>

## <span data-ttu-id="b905a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b905a-104">SYNOPSIS</span></span>
<span data-ttu-id="b905a-105">Разблокирует файлы, скачанные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b905a-105">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="b905a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b905a-106">SYNTAX</span></span>

### <span data-ttu-id="b905a-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b905a-107">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b905a-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b905a-108">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b905a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b905a-109">DESCRIPTION</span></span>

<span data-ttu-id="b905a-110">`Unblock-File`Командлет позволяет открывать файлы, загруженные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b905a-110">The `Unblock-File` cmdlet lets you open files that were downloaded from the Internet.</span></span> <span data-ttu-id="b905a-111">Он разблокирует файлы скриптов PowerShell, загруженные из Интернета, чтобы их можно было запустить даже в том случае, если политика выполнения PowerShell **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="b905a-111">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="b905a-112">По умолчанию эти файлы блокируются для защиты компьютера от ненадежных файлов.</span><span class="sxs-lookup"><span data-stu-id="b905a-112">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="b905a-113">Перед использованием `Unblock-File` командлета проверьте файл и его источник и убедитесь, что он является надежным для открытия.</span><span class="sxs-lookup"><span data-stu-id="b905a-113">Before using the `Unblock-File` cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="b905a-114">На внутреннем уровне `Unblock-File` командлет удаляет зону. идентификатор альтернативного потока данных, который имеет значение 3, чтобы указать, что он был загружен из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b905a-114">Internally, the `Unblock-File` cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="b905a-115">Дополнительные сведения о политиках выполнения PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="b905a-115">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="b905a-116">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b905a-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b905a-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="b905a-117">EXAMPLES</span></span>

### <span data-ttu-id="b905a-118">Пример 1. Разблокировка файла</span><span class="sxs-lookup"><span data-stu-id="b905a-118">Example 1: Unblock a file</span></span>

<span data-ttu-id="b905a-119">Эта команда разблокирует файл PowerShellTips.chm.</span><span class="sxs-lookup"><span data-stu-id="b905a-119">This command unblocks the PowerShellTips.chm file.</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### <span data-ttu-id="b905a-120">Пример 2. Разблокировка нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="b905a-120">Example 2: Unblock multiple files</span></span>

<span data-ttu-id="b905a-121">Эта команда разблокирует все файлы в `C:\Downloads` каталоге, имена которых содержат "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="b905a-121">This command unblocks all of the files in the `C:\Downloads` directory whose names include "PowerShell".</span></span> <span data-ttu-id="b905a-122">Не выполняйте подобную команду, пока не убедитесь в безопасности всех файлов.</span><span class="sxs-lookup"><span data-stu-id="b905a-122">Do not run a command like this one until you have verified that all files are safe.</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### <span data-ttu-id="b905a-123">Пример 3. скрипты поиска и разблокировки</span><span class="sxs-lookup"><span data-stu-id="b905a-123">Example 3: Find and unblock scripts</span></span>

<span data-ttu-id="b905a-124">Эта команда показывает, как найти и разблокировать скрипты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b905a-124">This command shows how to find and unblock PowerShell scripts.</span></span>

<span data-ttu-id="b905a-125">Первая команда использует параметр **Stream** командлета *Get-Item* для получения файлов с помощью потока зоны. identifier.</span><span class="sxs-lookup"><span data-stu-id="b905a-125">The first command uses the **Stream** parameter of the *Get-Item* cmdlet get files with the Zone.Identifier stream.</span></span>

<span data-ttu-id="b905a-126">Вторая команда показывает, что происходит при запуске заблокированного скрипта в сеансе PowerShell, в котором политика выполнения — **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="b905a-126">The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="b905a-127">Политика RemoteSigned запрещает выполнение сценариев, загруженных из Интернета, если они не имеют цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="b905a-127">The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.</span></span>

<span data-ttu-id="b905a-128">Третья команда использует командлет, `Unblock-File` чтобы разблокировать скрипт, чтобы он мог выполняться в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b905a-128">The third command uses the `Unblock-File` cmdlet to unblock the script so it can run in the session.</span></span>

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## <span data-ttu-id="b905a-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b905a-129">PARAMETERS</span></span>

### <span data-ttu-id="b905a-130">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b905a-130">-LiteralPath</span></span>

<span data-ttu-id="b905a-131">Указывает файлы для разблокирования.</span><span class="sxs-lookup"><span data-stu-id="b905a-131">Specifies the files to unblock.</span></span> <span data-ttu-id="b905a-132">В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="b905a-132">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="b905a-133">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b905a-133">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b905a-134">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b905a-134">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b905a-135">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b905a-135">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b905a-136">-Path</span><span class="sxs-lookup"><span data-stu-id="b905a-136">-Path</span></span>

<span data-ttu-id="b905a-137">Указывает файлы для разблокирования.</span><span class="sxs-lookup"><span data-stu-id="b905a-137">Specifies the files to unblock.</span></span> <span data-ttu-id="b905a-138">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b905a-138">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b905a-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b905a-139">-Confirm</span></span>

<span data-ttu-id="b905a-140">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b905a-140">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b905a-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b905a-141">-WhatIf</span></span>

<span data-ttu-id="b905a-142">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b905a-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b905a-143">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b905a-143">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b905a-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b905a-144">CommonParameters</span></span>

<span data-ttu-id="b905a-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b905a-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b905a-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b905a-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b905a-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b905a-147">INPUTS</span></span>

### <span data-ttu-id="b905a-148">System.String</span><span class="sxs-lookup"><span data-stu-id="b905a-148">System.String</span></span>

<span data-ttu-id="b905a-149">Путь к файлу можно передать по конвейеру `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="b905a-149">You can pipe a file path to `Unblock-File`.</span></span>

## <span data-ttu-id="b905a-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b905a-150">OUTPUTS</span></span>

### <span data-ttu-id="b905a-151">Нет</span><span class="sxs-lookup"><span data-stu-id="b905a-151">None</span></span>

<span data-ttu-id="b905a-152">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b905a-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b905a-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b905a-153">NOTES</span></span>

- <span data-ttu-id="b905a-154">В PowerShell 7 добавлена поддержка macOS.</span><span class="sxs-lookup"><span data-stu-id="b905a-154">Support for macOS was added in PowerShell 7.</span></span>
- <span data-ttu-id="b905a-155">`Unblock-File`Командлет работает только на дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="b905a-155">The `Unblock-File` cmdlet works only in file system drives.</span></span>
- <span data-ttu-id="b905a-156">`Unblock-File` выполняет ту же операцию, что и кнопка **разблокировать** в диалоговом окне " **свойства** " в проводнике.</span><span class="sxs-lookup"><span data-stu-id="b905a-156">`Unblock-File` performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
- <span data-ttu-id="b905a-157">При использовании `Unblock-File` командлета для незаблокированного файла команда не влияет на неблокируемый файл, и командлет не создает ошибки.</span><span class="sxs-lookup"><span data-stu-id="b905a-157">If you use the `Unblock-File` cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="b905a-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b905a-158">RELATED LINKS</span></span>

[<span data-ttu-id="b905a-159">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="b905a-159">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="b905a-160">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b905a-160">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="b905a-161">Out-File</span><span class="sxs-lookup"><span data-stu-id="b905a-161">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="b905a-162">Поставщик FileSystem</span><span class="sxs-lookup"><span data-stu-id="b905a-162">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
