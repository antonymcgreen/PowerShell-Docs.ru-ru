---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: 5553f61038c10d0c7c251609f729d157c53b03b9
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232770"
---
# <span data-ttu-id="ffd72-103">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="ffd72-103">Write-Warning</span></span>

## <span data-ttu-id="ffd72-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ffd72-104">SYNOPSIS</span></span>
<span data-ttu-id="ffd72-105">Записывает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="ffd72-105">Writes a warning message.</span></span>

## <span data-ttu-id="ffd72-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ffd72-106">SYNTAX</span></span>

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="ffd72-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ffd72-107">DESCRIPTION</span></span>

<span data-ttu-id="ffd72-108">`Write-Warning`Командлет Записывает предупреждающее сообщение на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffd72-108">The `Write-Warning` cmdlet writes a warning message to the PowerShell host.</span></span> <span data-ttu-id="ffd72-109">Ответ на предупреждение зависит от значения `$WarningPreference` переменной пользователя и использования общего параметра **WarningAction** .</span><span class="sxs-lookup"><span data-stu-id="ffd72-109">The response to the warning depends on the value of the user's `$WarningPreference` variable and the use of the **WarningAction** common parameter.</span></span>

## <span data-ttu-id="ffd72-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="ffd72-110">EXAMPLES</span></span>

### <span data-ttu-id="ffd72-111">Пример 1. Написание предупреждающего сообщения</span><span class="sxs-lookup"><span data-stu-id="ffd72-111">Example 1: Write a warning message</span></span>

<span data-ttu-id="ffd72-112">Эта команда выводит сообщение "предупреждение: это только предупреждение теста".</span><span class="sxs-lookup"><span data-stu-id="ffd72-112">This command displays the message "WARNING: This is only a test warning."</span></span>

```powershell
Write-Warning "This is only a test warning."
```

### <span data-ttu-id="ffd72-113">Пример 2. Передача строки в Write-Warning</span><span class="sxs-lookup"><span data-stu-id="ffd72-113">Example 2: Pass a string to Write-Warning</span></span>

<span data-ttu-id="ffd72-114">Эта команда показывает, что можно использовать оператор конвейера ( `|` ) для отправки строки в `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="ffd72-114">This command shows that you can use a pipeline operator (`|`) to send a string to `Write-Warning`.</span></span>
<span data-ttu-id="ffd72-115">Можно сохранить строку в переменной, как показано в этой команде, или передать строку непосредственно в `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="ffd72-115">You can save the string in a variable, as shown in this command, or pipe the string directly to `Write-Warning`.</span></span>

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### <span data-ttu-id="ffd72-116">Пример 3. задание переменной $WarningPreference и запись предупреждения</span><span class="sxs-lookup"><span data-stu-id="ffd72-116">Example 3: Set the $WarningPreference variable and write a warning</span></span>

<span data-ttu-id="ffd72-117">В этом примере показано воздействие значения `$WarningPreference` переменной на `Write-Warning` команду.</span><span class="sxs-lookup"><span data-stu-id="ffd72-117">This example shows the effect of the value of the `$WarningPreference` variable on a `Write-Warning` command.</span></span>

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

<span data-ttu-id="ffd72-118">Первая команда отображает значение по умолчанию для `$WarningPreference` переменной, то есть `Continue` .</span><span class="sxs-lookup"><span data-stu-id="ffd72-118">The first command displays the default value of the `$WarningPreference` variable, which is `Continue`.</span></span> <span data-ttu-id="ffd72-119">В результате при записи предупреждения отображается предупреждающее сообщение и продолжается выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="ffd72-119">As a result, when you write a warning, the warning message is displayed and execution continues.</span></span>

<span data-ttu-id="ffd72-120">При изменении значения `$WarningPreference` переменной результат `Write-Warning` команды снова изменяется.</span><span class="sxs-lookup"><span data-stu-id="ffd72-120">When you change the value of the `$WarningPreference` variable, the effect of the `Write-Warning` command changes again.</span></span> <span data-ttu-id="ffd72-121">Значение `SilentlyContinue` подавляет вывод предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ffd72-121">A value of `SilentlyContinue` suppresses the warning.</span></span> <span data-ttu-id="ffd72-122">Значение `Stop` отображает предупреждение, а затем останавливает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="ffd72-122">A value of `Stop` displays the warning and then stops execution of the command.</span></span>

<span data-ttu-id="ffd72-123">Дополнительные сведения о `$WarningPreference` переменной см. в разделе [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ffd72-123">For more information about the `$WarningPreference` variable, see [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="ffd72-124">Пример 4. Установка параметра WarningAction и запись предупреждения</span><span class="sxs-lookup"><span data-stu-id="ffd72-124">Example 4: Set the WarningAction parameter and write a warning</span></span>

<span data-ttu-id="ffd72-125">В этом примере показан результат использования общего параметра **WarningAction** в `Write-Warning` команде.</span><span class="sxs-lookup"><span data-stu-id="ffd72-125">This example shows the effect of the **WarningAction** common parameter on a `Write-Warning` command.</span></span> <span data-ttu-id="ffd72-126">Вы можете использовать общий параметр **WarningAction** с любым командлетом, чтобы определить, как PowerShell реагирует на предупреждения, полученные от этой команды.</span><span class="sxs-lookup"><span data-stu-id="ffd72-126">You can use the **WarningAction** common parameter with any cmdlet to determine how PowerShell responds to warnings resulting from that command.</span></span> <span data-ttu-id="ffd72-127">Общий параметр **WarningAction** переопределяет значение `$WarningPreference` только для этой конкретной команды.</span><span class="sxs-lookup"><span data-stu-id="ffd72-127">The **WarningAction** common parameter overrides the value of the `$WarningPreference` only for that particular command.</span></span>

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="ffd72-128">Эта команда использует `Write-Warning` командлет для вывода предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ffd72-128">This command uses the `Write-Warning` cmdlet to display a warning.</span></span> <span data-ttu-id="ffd72-129">Общий параметр **WarningAction** со значением "запрос" направляет систему на запрос пользователя, когда команда выводит предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ffd72-129">The **WarningAction** common parameter with a value of Inquire directs the system to prompt the user when the command displays a warning.</span></span>

<span data-ttu-id="ffd72-130">Дополнительные сведения об общем параметре **WarningAction** см. в разделе [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ffd72-130">For more information about the **WarningAction** common parameter, see [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ffd72-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ffd72-131">PARAMETERS</span></span>

### <span data-ttu-id="ffd72-132">-Message</span><span class="sxs-lookup"><span data-stu-id="ffd72-132">-Message</span></span>
<span data-ttu-id="ffd72-133">Указывает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="ffd72-133">Specifies the warning message.</span></span>

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

### <span data-ttu-id="ffd72-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ffd72-134">CommonParameters</span></span>

<span data-ttu-id="ffd72-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ffd72-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ffd72-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ffd72-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ffd72-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ffd72-137">INPUTS</span></span>

### <span data-ttu-id="ffd72-138">System.String</span><span class="sxs-lookup"><span data-stu-id="ffd72-138">System.String</span></span>

<span data-ttu-id="ffd72-139">Строку, содержащую предупреждение, можно передать в `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="ffd72-139">You can pipe a string that contains the warning to `Write-Warning`.</span></span>

## <span data-ttu-id="ffd72-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ffd72-140">OUTPUTS</span></span>

### <span data-ttu-id="ffd72-141">Нет</span><span class="sxs-lookup"><span data-stu-id="ffd72-141">None</span></span>

<span data-ttu-id="ffd72-142">`Write-Warning` выполняет запись только в поток предупреждений.</span><span class="sxs-lookup"><span data-stu-id="ffd72-142">`Write-Warning` writes only to the warning stream.</span></span> <span data-ttu-id="ffd72-143">Он не формирует каких-либо других выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ffd72-143">It does not generate any other output.</span></span>

## <span data-ttu-id="ffd72-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ffd72-144">NOTES</span></span>

<span data-ttu-id="ffd72-145">Значением по умолчанию для `$WarningPreference` переменной является `Continue` , которое отображает предупреждение и затем возобновляет выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="ffd72-145">The default value for the `$WarningPreference` variable is `Continue`, which displays the warning and then continues executing the command.</span></span> <span data-ttu-id="ffd72-146">Чтобы определить допустимые значения для привилегированной переменной, например `$WarningPreference` , задайте для нее строку случайных символов, например "ABC".</span><span class="sxs-lookup"><span data-stu-id="ffd72-146">To determine valid values for a preference variable such as `$WarningPreference`, set it to a string of random characters, such as "abc".</span></span> <span data-ttu-id="ffd72-147">В итоговом сообщении об ошибке выводится список допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="ffd72-147">The resulting error message lists the valid values.</span></span>

## <span data-ttu-id="ffd72-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ffd72-148">RELATED LINKS</span></span>

[<span data-ttu-id="ffd72-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="ffd72-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="ffd72-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="ffd72-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="ffd72-151">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="ffd72-151">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="ffd72-152">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="ffd72-152">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="ffd72-153">Write-Host</span><span class="sxs-lookup"><span data-stu-id="ffd72-153">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="ffd72-154">Write-Information</span><span class="sxs-lookup"><span data-stu-id="ffd72-154">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="ffd72-155">Write-Output</span><span class="sxs-lookup"><span data-stu-id="ffd72-155">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="ffd72-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="ffd72-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="ffd72-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="ffd72-157">Write-Verbose</span></span>](Write-Verbose.md)
