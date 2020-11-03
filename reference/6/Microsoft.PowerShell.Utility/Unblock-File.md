---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 617d36f61434d8b779d1161610cc7757c6a7725d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228765"
---
# <span data-ttu-id="b2c22-103">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="b2c22-103">Unblock-File</span></span>

## <span data-ttu-id="b2c22-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b2c22-104">SYNOPSIS</span></span>
<span data-ttu-id="b2c22-105">Разблокирует файлы, скачанные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b2c22-105">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="b2c22-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b2c22-106">SYNTAX</span></span>

### <span data-ttu-id="b2c22-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b2c22-107">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b2c22-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b2c22-108">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b2c22-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b2c22-109">DESCRIPTION</span></span>

<span data-ttu-id="b2c22-110">Командлет **Unblock-File** позволяет открывать файлы, загруженные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b2c22-110">The **Unblock-File** cmdlet lets you open files that were downloaded from the Internet.</span></span>
<span data-ttu-id="b2c22-111">Он разблокирует файлы скриптов PowerShell, загруженные из Интернета, чтобы их можно было запустить даже в том случае, если политика выполнения PowerShell **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="b2c22-111">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned** .</span></span>
<span data-ttu-id="b2c22-112">По умолчанию эти файлы блокируются для защиты компьютера от ненадежных файлов.</span><span class="sxs-lookup"><span data-stu-id="b2c22-112">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="b2c22-113">Перед использованием командлета **Unblock-File** просмотрите файл и его источник и убедитесь, что его открытие не нарушит безопасность.</span><span class="sxs-lookup"><span data-stu-id="b2c22-113">Before using the **Unblock-File** cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="b2c22-114">На внутреннем уровне командлет **Unblock-File** удаляет дополнительный поток данных Zone.Identifier, который имеет значение "3", указывающее на загрузку из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b2c22-114">Internally, the **Unblock-File** cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="b2c22-115">Дополнительные сведения о политиках выполнения PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2c22-115">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="b2c22-116">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b2c22-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b2c22-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="b2c22-117">EXAMPLES</span></span>

### <span data-ttu-id="b2c22-118">Пример 1. Разблокировка файла</span><span class="sxs-lookup"><span data-stu-id="b2c22-118">Example 1: Unblock a file</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

<span data-ttu-id="b2c22-119">Эта команда разблокирует файл PowerShellTips.chm.</span><span class="sxs-lookup"><span data-stu-id="b2c22-119">This command unblocks the PowerShellTips.chm file.</span></span>

### <span data-ttu-id="b2c22-120">Пример 2. Разблокировка нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="b2c22-120">Example 2: Unblock multiple files</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

<span data-ttu-id="b2c22-121">Эта команда разблокирует все файлы в каталоге C:\Downloads, имена которых содержат PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2c22-121">This command unblocks all of the files in the C:\Downloads directory whose names include "PowerShell".</span></span>
<span data-ttu-id="b2c22-122">Не выполняйте подобную команду, пока не убедитесь в безопасности всех файлов.</span><span class="sxs-lookup"><span data-stu-id="b2c22-122">Do not run a command like this one until you have verified that all files are safe.</span></span>

### <span data-ttu-id="b2c22-123">Пример 3. скрипты поиска и разблокировки</span><span class="sxs-lookup"><span data-stu-id="b2c22-123">Example 3: Find and unblock scripts</span></span>

```
The first command uses the *Stream* parameter of the Get-Item cmdlet get files with the Zone.Identifier stream.Although you could pipe the output directly to the **Unblock-File** cmdlet (Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue | ForEach {Unblock-File $_.FileName}), it is prudent to review the file and confirm that it is safe before unblocking.
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**. The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.
PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

The third command uses the **Unblock-File** cmdlet to unblock the script so it can run in the session.
PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

<span data-ttu-id="b2c22-124">Эта команда показывает, как найти и разблокировать скрипты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2c22-124">This command shows how to find and unblock PowerShell scripts.</span></span>

## <span data-ttu-id="b2c22-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b2c22-125">PARAMETERS</span></span>

### <span data-ttu-id="b2c22-126">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b2c22-126">-LiteralPath</span></span>
<span data-ttu-id="b2c22-127">Указывает файлы для разблокирования.</span><span class="sxs-lookup"><span data-stu-id="b2c22-127">Specifies the files to unblock.</span></span>
<span data-ttu-id="b2c22-128">В отличие от параметра *Path* , значение параметра *LiteralPath* используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="b2c22-128">Unlike *Path* , the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="b2c22-129">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b2c22-129">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="b2c22-130">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b2c22-130">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b2c22-131">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b2c22-131">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="b2c22-132">-Path</span><span class="sxs-lookup"><span data-stu-id="b2c22-132">-Path</span></span>
<span data-ttu-id="b2c22-133">Указывает файлы для разблокирования.</span><span class="sxs-lookup"><span data-stu-id="b2c22-133">Specifies the files to unblock.</span></span>
<span data-ttu-id="b2c22-134">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2c22-134">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="b2c22-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b2c22-135">-Confirm</span></span>

<span data-ttu-id="b2c22-136">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b2c22-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b2c22-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b2c22-137">-WhatIf</span></span>

<span data-ttu-id="b2c22-138">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b2c22-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b2c22-139">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b2c22-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b2c22-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b2c22-140">CommonParameters</span></span>

<span data-ttu-id="b2c22-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b2c22-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b2c22-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b2c22-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b2c22-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b2c22-143">INPUTS</span></span>

### <span data-ttu-id="b2c22-144">System.String</span><span class="sxs-lookup"><span data-stu-id="b2c22-144">System.String</span></span>

<span data-ttu-id="b2c22-145">В **Unblock-File** можно передать путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="b2c22-145">You can pipe a file path to **Unblock-File** .</span></span>

## <span data-ttu-id="b2c22-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b2c22-146">OUTPUTS</span></span>

### <span data-ttu-id="b2c22-147">Нет</span><span class="sxs-lookup"><span data-stu-id="b2c22-147">None</span></span>

<span data-ttu-id="b2c22-148">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b2c22-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b2c22-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b2c22-149">NOTES</span></span>

* <span data-ttu-id="b2c22-150">Командлет **Unblock-File** работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="b2c22-150">The **Unblock-File** cmdlet works only in file system drives.</span></span>
* <span data-ttu-id="b2c22-151">**Unblock-File** выполняет ту же операцию, что и кнопка **разблокировать** в диалоговом окне **Свойства** в проводнике.</span><span class="sxs-lookup"><span data-stu-id="b2c22-151">**Unblock-File** performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
* <span data-ttu-id="b2c22-152">При использовании командлета **Unblock-File** для незаблокированного файла команда не оказывает влияния на такой файл и командлет не создает ошибок.</span><span class="sxs-lookup"><span data-stu-id="b2c22-152">If you use the **Unblock-File** cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="b2c22-153">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b2c22-153">RELATED LINKS</span></span>

[<span data-ttu-id="b2c22-154">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="b2c22-154">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="b2c22-155">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b2c22-155">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="b2c22-156">Out-File</span><span class="sxs-lookup"><span data-stu-id="b2c22-156">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="b2c22-157">Поставщик FileSystem</span><span class="sxs-lookup"><span data-stu-id="b2c22-157">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
