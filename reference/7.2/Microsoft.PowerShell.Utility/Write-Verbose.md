---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 177e32106f37c59593bbecac13843f6603327cc9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605294"
---
# <span data-ttu-id="8df98-102">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="8df98-102">Write-Verbose</span></span>

## <span data-ttu-id="8df98-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8df98-103">SYNOPSIS</span></span>
<span data-ttu-id="8df98-104">Записывает текст в поток подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="8df98-104">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="8df98-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8df98-105">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="8df98-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8df98-106">DESCRIPTION</span></span>

<span data-ttu-id="8df98-107">`Write-Verbose`Командлет записывает текст в поток подробных сообщений в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8df98-107">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="8df98-108">Как правило, поток подробных сообщений используется для предоставления более подробных сведений об обработке команд.</span><span class="sxs-lookup"><span data-stu-id="8df98-108">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="8df98-109">По умолчанию поток подробных сообщений не отображается, но его можно отобразить, изменив значение `$VerbosePreference` переменной или используя параметр **verbose** Common в любой команде.</span><span class="sxs-lookup"><span data-stu-id="8df98-109">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="8df98-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="8df98-110">EXAMPLES</span></span>

### <span data-ttu-id="8df98-111">Пример 1. запись сообщения о состоянии</span><span class="sxs-lookup"><span data-stu-id="8df98-111">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="8df98-112">Эти команды используют `Write-Verbose` командлет для вывода сообщения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="8df98-112">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="8df98-113">По умолчанию это сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="8df98-113">By default, the message is not displayed.</span></span>

<span data-ttu-id="8df98-114">Вторая команда использует параметр **verbose** Common, который отображает все подробные сообщения, независимо от значения `$VerbosePreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="8df98-114">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="8df98-115">Пример 2. Настройка $VerbosePreference и запись сообщения о состоянии</span><span class="sxs-lookup"><span data-stu-id="8df98-115">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="8df98-116">Эти команды используют `Write-Verbose` командлет для вывода сообщения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="8df98-116">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="8df98-117">По умолчанию это сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="8df98-117">By default, the message is not displayed.</span></span>

<span data-ttu-id="8df98-118">Первая команда присваивает значение Continue `$VerbosePreference` переменной предпочтения.</span><span class="sxs-lookup"><span data-stu-id="8df98-118">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="8df98-119">Значение по умолчанию, `SilentlyContinue` , подавляет подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="8df98-119">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="8df98-120">Вторая команда записывает подробное сообщение.</span><span class="sxs-lookup"><span data-stu-id="8df98-120">The second command writes a verbose message.</span></span>

## <span data-ttu-id="8df98-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8df98-121">PARAMETERS</span></span>

### <span data-ttu-id="8df98-122">-Message</span><span class="sxs-lookup"><span data-stu-id="8df98-122">-Message</span></span>

<span data-ttu-id="8df98-123">Задает отображаемое сообщение.</span><span class="sxs-lookup"><span data-stu-id="8df98-123">Specifies the message to display.</span></span> <span data-ttu-id="8df98-124">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8df98-124">This parameter is required.</span></span> <span data-ttu-id="8df98-125">Можно также передать строку сообщения в `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="8df98-125">You can also pipe a message string to `Write-Verbose`.</span></span>

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

### <span data-ttu-id="8df98-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8df98-126">CommonParameters</span></span>

<span data-ttu-id="8df98-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8df98-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8df98-128">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8df98-128">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8df98-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8df98-129">INPUTS</span></span>

### <span data-ttu-id="8df98-130">System.String</span><span class="sxs-lookup"><span data-stu-id="8df98-130">System.String</span></span>

<span data-ttu-id="8df98-131">Строку, содержащую сообщение, можно передать в конвейер `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="8df98-131">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="8df98-132">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8df98-132">OUTPUTS</span></span>

### <span data-ttu-id="8df98-133">None</span><span class="sxs-lookup"><span data-stu-id="8df98-133">None</span></span>

<span data-ttu-id="8df98-134">`Write-Verbose` выполняет запись только в поток подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="8df98-134">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="8df98-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8df98-135">NOTES</span></span>

- <span data-ttu-id="8df98-136">Подробные сообщения возвращаются только в том случае, если в команде используется общий параметр **Verbose**.</span><span class="sxs-lookup"><span data-stu-id="8df98-136">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="8df98-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8df98-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="8df98-138">В фоновых заданиях и удаленных командах Windows PowerShell `$VerbosePreference` переменная в сеансе задания и удаленный сеанс определяют, отображается ли подробное сообщение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8df98-138">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="8df98-139">Дополнительные сведения о `$VerbosePreference` переменной см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8df98-139">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="8df98-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8df98-140">RELATED LINKS</span></span>

[<span data-ttu-id="8df98-141">О потоках вывода</span><span class="sxs-lookup"><span data-stu-id="8df98-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="8df98-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="8df98-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="8df98-143">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="8df98-143">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="8df98-144">Write-Error</span><span class="sxs-lookup"><span data-stu-id="8df98-144">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="8df98-145">Write-Host</span><span class="sxs-lookup"><span data-stu-id="8df98-145">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="8df98-146">Write-Information</span><span class="sxs-lookup"><span data-stu-id="8df98-146">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="8df98-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="8df98-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="8df98-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="8df98-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="8df98-149">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="8df98-149">Write-Warning</span></span>](Write-Warning.md)
