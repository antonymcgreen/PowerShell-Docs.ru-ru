---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: e0f28393c95e2c0703c489d4691edcf883b4cb05
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232814"
---
# <span data-ttu-id="4b2ae-103">Write-Information</span><span class="sxs-lookup"><span data-stu-id="4b2ae-103">Write-Information</span></span>

## <span data-ttu-id="4b2ae-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b2ae-104">SYNOPSIS</span></span>

<span data-ttu-id="4b2ae-105">Указывает, как PowerShell обрабатывает данные информационного потока для команды.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-105">Specifies how PowerShell handles information stream data for a command.</span></span>

## <span data-ttu-id="4b2ae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b2ae-106">SYNTAX</span></span>

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="4b2ae-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b2ae-107">DESCRIPTION</span></span>

<span data-ttu-id="4b2ae-108">`Write-Information`Командлет определяет, как PowerShell обрабатывает данные информационного потока для команды.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-108">The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.</span></span>

<span data-ttu-id="4b2ae-109">В Windows PowerShell 5,0 появился новый структурированный информационный поток.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-109">Windows PowerShell 5.0 introduces a new, structured information stream.</span></span> <span data-ttu-id="4b2ae-110">Этот поток можно использовать для передачи структурированных данных между скриптом и его вызывающими объектами или ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-110">You can use this stream to transmit structured data between a script and its callers or the host application.</span></span>
<span data-ttu-id="4b2ae-111">`Write-Information` позволяет добавить информационное сообщение в поток и указать, как PowerShell обрабатывает данные информационного потока для команды.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-111">`Write-Information` lets you add an informational message to the stream, and specify how PowerShell handles information stream data for a command.</span></span> <span data-ttu-id="4b2ae-112">Информационные потоки также работают для `PowerShell.Streams` , заданий и запланированных задач.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-112">Information streams also work for `PowerShell.Streams`, jobs, and scheduled tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="4b2ae-113">Информационный поток не соответствует стандартному соглашению о предисправлении сообщений с помощью "[Stream name]:".</span><span class="sxs-lookup"><span data-stu-id="4b2ae-113">The information stream does not follow the standard convention of prefixing its messages with "[Stream Name]:".</span></span> <span data-ttu-id="4b2ae-114">Это было предназначено для краткости и Visual чистоте.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-114">This was intended for brevity and visual cleanliness.</span></span>

<span data-ttu-id="4b2ae-115">`$InformationPreference`Значение переменной предпочтения определяет, отображается ли сообщение, которое вы указываете, в `Write-Information` ожидаемой точке операции скрипта.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-115">The `$InformationPreference` preference variable value determines whether the message you provide to `Write-Information` is displayed at the expected point in a script's operation.</span></span> <span data-ttu-id="4b2ae-116">Поскольку значение по умолчанию для этой переменной равно `SilentlyContinue` , по умолчанию информационные сообщения не отображаются.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-116">Because the default value of this variable is `SilentlyContinue`, by default, informational messages are not shown.</span></span> <span data-ttu-id="4b2ae-117">Если вы не хотите изменять значение `$InformationPreference` , его значение можно переопределить, добавив в `InformationAction` команду Общий параметр.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-117">If you don't want to change the value of `$InformationPreference`, you can override its value by adding the `InformationAction` common parameter to your command.</span></span> <span data-ttu-id="4b2ae-118">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) и [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4b2ae-118">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) and [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4b2ae-119">Начиная с Windows PowerShell 5,0, `Write-Host` — это оболочка для этого, которая `Write-Information` позволяет использовать `Write-Host` для отправки выходных данных в информационный поток.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-119">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="4b2ae-120">Это позволяет **записывать** или **подавить** данные, написанные с помощью, сохраняя `Write-Host` обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-120">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span> <span data-ttu-id="4b2ae-121">Дополнительные сведения см. в разделе [Write-Host](Write-Host.md) .</span><span class="sxs-lookup"><span data-stu-id="4b2ae-121">For more information see [Write-Host](Write-Host.md)</span></span>

<span data-ttu-id="4b2ae-122">`Write-Information` также является поддерживаемым действием рабочего процесса в PowerShell 5. x.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-122">`Write-Information` is also a supported workflow activity in PowerShell 5.x.</span></span>

## <span data-ttu-id="4b2ae-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b2ae-123">EXAMPLES</span></span>

### <span data-ttu-id="4b2ae-124">Пример 1. запись сведений для Get-Results</span><span class="sxs-lookup"><span data-stu-id="4b2ae-124">Example 1: Write information for Get- results</span></span>

<span data-ttu-id="4b2ae-125">В этом примере отображается информационное сообщение "получены ваши компоненты!" после выполнения `Get-WindowsFeature` команды, чтобы найти все компоненты, имя которых начинается с "p".</span><span class="sxs-lookup"><span data-stu-id="4b2ae-125">In this example, you show an informational message, "Got your features!", after running the `Get-WindowsFeature` command to find all features that have a Name value that starts with 'p'.</span></span>
<span data-ttu-id="4b2ae-126">Так как `$InformationPreference` переменная по-прежнему имеет значение по умолчанию, `SilentlyContinue` вы добавляете `InformationAction` параметр для переопределения `$InformationPreference` значения и отображает сообщение.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-126">Because the `$InformationPreference` variable is still set to its default, `SilentlyContinue`, you add the `InformationAction` parameter to override the `$InformationPreference` value, and show the message.</span></span> <span data-ttu-id="4b2ae-127">Значение Continue, означающее, что `InformationAction` сообщение отображается, но скрипт или команда продолжают работу, если она еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-127">The `InformationAction` value is Continue, which means that your message is shown, but the script or command continues, if it is not yet finished.</span></span>

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### <span data-ttu-id="4b2ae-128">Пример 2. запись сведений и пометка их</span><span class="sxs-lookup"><span data-stu-id="4b2ae-128">Example 2: Write information and tag it</span></span>

<span data-ttu-id="4b2ae-129">В этом примере вы будете использовать, `Write-Information` чтобы сообщить пользователям, что им потребуется выполнить другую команду после выполнения текущей команды.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-129">In this example, you use `Write-Information` to let users know they'll need to run another command after they're done running the current command.</span></span> <span data-ttu-id="4b2ae-130">В этом примере в информационное сообщение добавляются инструкции тегов.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-130">The example adds the tag Instructions to the informational message.</span></span> <span data-ttu-id="4b2ae-131">После выполнения этой команды при поиске в информационном потоке инструкций, помеченных как сообщения, указанное здесь сообщение будет среди результатов.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-131">After running this command, if you search the information stream for messages tagged Instructions, the message specified here would be among the results.</span></span>

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### <span data-ttu-id="4b2ae-132">Пример 3. запись сведений в файл</span><span class="sxs-lookup"><span data-stu-id="4b2ae-132">Example 3: Write information to a file</span></span>

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

## <span data-ttu-id="4b2ae-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b2ae-133">PARAMETERS</span></span>

### <span data-ttu-id="4b2ae-134">-MessageData</span><span class="sxs-lookup"><span data-stu-id="4b2ae-134">-MessageData</span></span>

<span data-ttu-id="4b2ae-135">Указывает информационное сообщение, которое будет отображаться для пользователей при выполнении сценария или команды.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-135">Specifies an informational message that you want to display to users as they run a script or command.</span></span> <span data-ttu-id="4b2ae-136">Для достижения лучших результатов заключите информационное сообщение в кавычки.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-136">For best results, enclose the informational message in quotation marks.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b2ae-137">-Теги</span><span class="sxs-lookup"><span data-stu-id="4b2ae-137">-Tags</span></span>

<span data-ttu-id="4b2ae-138">Задает простую строку, которую можно использовать для сортировки и фильтрации сообщений, добавленных в информационный поток в `Write-Information` .</span><span class="sxs-lookup"><span data-stu-id="4b2ae-138">Specifies a simple string that you can use to sort and filter messages that you have added to the information stream with `Write-Information`.</span></span> <span data-ttu-id="4b2ae-139">Этот параметр работает аналогично параметру **Tags** в `New-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="4b2ae-139">This parameter works similarly to the **Tags** parameter in `New-ModuleManifest`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b2ae-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b2ae-140">CommonParameters</span></span>

<span data-ttu-id="4b2ae-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b2ae-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b2ae-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b2ae-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b2ae-143">INPUTS</span></span>

### <span data-ttu-id="4b2ae-144">Нет</span><span class="sxs-lookup"><span data-stu-id="4b2ae-144">None</span></span>

<span data-ttu-id="4b2ae-145">`Write-Information` не принимает входные данные о перенаправлении.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-145">`Write-Information` does not accept piped input.</span></span>

## <span data-ttu-id="4b2ae-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b2ae-146">OUTPUTS</span></span>

### <span data-ttu-id="4b2ae-147">System. Management. Automation. Информатионрекорд</span><span class="sxs-lookup"><span data-stu-id="4b2ae-147">System.Management.Automation.InformationRecord</span></span>

## <span data-ttu-id="4b2ae-148">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b2ae-148">NOTES</span></span>

## <span data-ttu-id="4b2ae-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b2ae-149">RELATED LINKS</span></span>

[<span data-ttu-id="4b2ae-150">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="4b2ae-150">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="4b2ae-151">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="4b2ae-151">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="4b2ae-152">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4b2ae-152">about_CommonParameters</span></span>](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[<span data-ttu-id="4b2ae-153">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="4b2ae-153">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="4b2ae-154">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="4b2ae-154">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="4b2ae-155">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="4b2ae-155">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="4b2ae-156">Write-Host</span><span class="sxs-lookup"><span data-stu-id="4b2ae-156">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="4b2ae-157">Write-Information</span><span class="sxs-lookup"><span data-stu-id="4b2ae-157">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="4b2ae-158">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="4b2ae-158">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="4b2ae-159">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="4b2ae-159">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="4b2ae-160">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="4b2ae-160">Write-Warning</span></span>](Write-Warning.md)

[<span data-ttu-id="4b2ae-161">Write-Output</span><span class="sxs-lookup"><span data-stu-id="4b2ae-161">Write-Output</span></span>](Write-Output.md)
