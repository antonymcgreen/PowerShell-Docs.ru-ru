---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 34e8d6edd7199921254a3835a9f13b6331c2d26e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232857"
---
# <span data-ttu-id="9f088-103">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="9f088-103">Write-Verbose</span></span>

## <span data-ttu-id="9f088-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9f088-104">SYNOPSIS</span></span>
<span data-ttu-id="9f088-105">Записывает текст в поток подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="9f088-105">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="9f088-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f088-106">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="9f088-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f088-107">DESCRIPTION</span></span>

<span data-ttu-id="9f088-108">`Write-Verbose`Командлет записывает текст в поток подробных сообщений в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f088-108">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="9f088-109">Как правило, поток подробных сообщений используется для предоставления более подробных сведений об обработке команд.</span><span class="sxs-lookup"><span data-stu-id="9f088-109">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="9f088-110">По умолчанию поток подробных сообщений не отображается, но его можно отобразить, изменив значение `$VerbosePreference` переменной или используя параметр **verbose** Common в любой команде.</span><span class="sxs-lookup"><span data-stu-id="9f088-110">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="9f088-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f088-111">EXAMPLES</span></span>

### <span data-ttu-id="9f088-112">Пример 1. запись сообщения о состоянии</span><span class="sxs-lookup"><span data-stu-id="9f088-112">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="9f088-113">Эти команды используют `Write-Verbose` командлет для вывода сообщения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="9f088-113">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="9f088-114">По умолчанию это сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="9f088-114">By default, the message is not displayed.</span></span>

<span data-ttu-id="9f088-115">Вторая команда использует параметр **verbose** Common, который отображает все подробные сообщения, независимо от значения `$VerbosePreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="9f088-115">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="9f088-116">Пример 2. Настройка $VerbosePreference и запись сообщения о состоянии</span><span class="sxs-lookup"><span data-stu-id="9f088-116">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="9f088-117">Эти команды используют `Write-Verbose` командлет для вывода сообщения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="9f088-117">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="9f088-118">По умолчанию это сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="9f088-118">By default, the message is not displayed.</span></span>

<span data-ttu-id="9f088-119">Первая команда присваивает значение Continue `$VerbosePreference` переменной предпочтения.</span><span class="sxs-lookup"><span data-stu-id="9f088-119">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="9f088-120">Значение по умолчанию, `SilentlyContinue` , подавляет подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="9f088-120">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="9f088-121">Вторая команда записывает подробное сообщение.</span><span class="sxs-lookup"><span data-stu-id="9f088-121">The second command writes a verbose message.</span></span>

## <span data-ttu-id="9f088-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f088-122">PARAMETERS</span></span>

### <span data-ttu-id="9f088-123">-Message</span><span class="sxs-lookup"><span data-stu-id="9f088-123">-Message</span></span>

<span data-ttu-id="9f088-124">Задает отображаемое сообщение.</span><span class="sxs-lookup"><span data-stu-id="9f088-124">Specifies the message to display.</span></span> <span data-ttu-id="9f088-125">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="9f088-125">This parameter is required.</span></span> <span data-ttu-id="9f088-126">Можно также передать строку сообщения в `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="9f088-126">You can also pipe a message string to `Write-Verbose`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9f088-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9f088-127">CommonParameters</span></span>

<span data-ttu-id="9f088-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f088-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f088-129">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9f088-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9f088-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9f088-130">INPUTS</span></span>

### <span data-ttu-id="9f088-131">System.String</span><span class="sxs-lookup"><span data-stu-id="9f088-131">System.String</span></span>

<span data-ttu-id="9f088-132">Строку, содержащую сообщение, можно передать в конвейер `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="9f088-132">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="9f088-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9f088-133">OUTPUTS</span></span>

### <span data-ttu-id="9f088-134">Нет</span><span class="sxs-lookup"><span data-stu-id="9f088-134">None</span></span>

<span data-ttu-id="9f088-135">`Write-Verbose` выполняет запись только в поток подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="9f088-135">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="9f088-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9f088-136">NOTES</span></span>

- <span data-ttu-id="9f088-137">Подробные сообщения возвращаются только в том случае, если в команде используется общий параметр **Verbose**.</span><span class="sxs-lookup"><span data-stu-id="9f088-137">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="9f088-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f088-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="9f088-139">В фоновых заданиях и удаленных командах Windows PowerShell `$VerbosePreference` переменная в сеансе задания и удаленный сеанс определяют, отображается ли подробное сообщение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f088-139">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="9f088-140">Дополнительные сведения о `$VerbosePreference` переменной см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9f088-140">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="9f088-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9f088-141">RELATED LINKS</span></span>

[<span data-ttu-id="9f088-142">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="9f088-142">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="9f088-143">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="9f088-143">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="9f088-144">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="9f088-144">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="9f088-145">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="9f088-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="9f088-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="9f088-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="9f088-147">Write-Information</span><span class="sxs-lookup"><span data-stu-id="9f088-147">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="9f088-148">Write-Output</span><span class="sxs-lookup"><span data-stu-id="9f088-148">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="9f088-149">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="9f088-149">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="9f088-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="9f088-150">Write-Warning</span></span>](Write-Warning.md)
