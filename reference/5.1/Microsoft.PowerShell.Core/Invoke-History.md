---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 613b460678186380b518a0bc04abc426c1038a84
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226657"
---
# <span data-ttu-id="806c3-103">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="806c3-103">Invoke-History</span></span>

## <span data-ttu-id="806c3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="806c3-104">SYNOPSIS</span></span>
<span data-ttu-id="806c3-105">Выполняет команды из журнала сеанса.</span><span class="sxs-lookup"><span data-stu-id="806c3-105">Runs commands from the session history.</span></span>

## <span data-ttu-id="806c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="806c3-106">SYNTAX</span></span>

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="806c3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="806c3-107">DESCRIPTION</span></span>

<span data-ttu-id="806c3-108">`Invoke-History`Командлет запускает команды из журнала сеанса.</span><span class="sxs-lookup"><span data-stu-id="806c3-108">The `Invoke-History` cmdlet runs commands from the session history.</span></span> <span data-ttu-id="806c3-109">Можно передать объекты, представляющие команды, из Get-History в `Invoke-History` или же можно указать команды в текущем журнале, используя их **идентификационный** номер.</span><span class="sxs-lookup"><span data-stu-id="806c3-109">You can pass objects representing the commands from Get-History to `Invoke-History`, or you can identify commands in the current history by using their **Id** number.</span></span> <span data-ttu-id="806c3-110">Чтобы найти идентификационный номер команды, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="806c3-110">To find the identification number of a command, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="806c3-111">Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="806c3-111">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="806c3-112">Оба журнала доступны в сеансах, где загружен **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="806c3-112">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="806c3-113">Этот командлет работает только с журналом сеанса.</span><span class="sxs-lookup"><span data-stu-id="806c3-113">This cmdlet only works with the session history.</span></span> <span data-ttu-id="806c3-114">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="806c3-114">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="806c3-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="806c3-115">EXAMPLES</span></span>

### <span data-ttu-id="806c3-116">Пример 1. запуск последней команды в журнале</span><span class="sxs-lookup"><span data-stu-id="806c3-116">Example 1: Run the most recent command in the history</span></span>

<span data-ttu-id="806c3-117">В этом примере выполняется последняя или самая последняя команда в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="806c3-117">This example runs the last, or most recent, command in the session history.</span></span> <span data-ttu-id="806c3-118">Можно сократить эту команду, например `r` , псевдоним для `Invoke-History` .</span><span class="sxs-lookup"><span data-stu-id="806c3-118">You can abbreviate this command as `r`, the alias for `Invoke-History`.</span></span>

```powershell
Invoke-History
```

### <span data-ttu-id="806c3-119">Пример 2. выполнение команды с указанным ИДЕНТИФИКАТОРом</span><span class="sxs-lookup"><span data-stu-id="806c3-119">Example 2: Run the command that has a specified ID</span></span>

<span data-ttu-id="806c3-120">В этом примере выполняется команда в журнале сеанса с **идентификатором** 132.</span><span class="sxs-lookup"><span data-stu-id="806c3-120">This example runs the command in the session history with **Id** 132.</span></span> <span data-ttu-id="806c3-121">Поскольку имя параметра **ID** является необязательным, можно сократить эту команду следующим образом: `Invoke-History 132` , `ihy 132` или `r 132` .</span><span class="sxs-lookup"><span data-stu-id="806c3-121">Because the name of the **Id** parameter is optional, you can abbreviate this command as the following: `Invoke-History 132`, `ihy 132`, or `r 132`.</span></span>

```powershell
Invoke-History -Id 132
```

### <span data-ttu-id="806c3-122">Пример 3. запуск последней команды с помощью текста команды</span><span class="sxs-lookup"><span data-stu-id="806c3-122">Example 3: Run the most recent command by using the command text</span></span>

<span data-ttu-id="806c3-123">В этом примере выполняется последняя `Get-Process` команда в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="806c3-123">This example runs the most recent `Get-Process` command in the session history.</span></span> <span data-ttu-id="806c3-124">При вводе символов для параметра **ID** `Invoke-History` выполняет первую найденную команду, совпадающую с шаблоном, начиная с самых последних команд.</span><span class="sxs-lookup"><span data-stu-id="806c3-124">When you type characters for the **Id** parameter, `Invoke-History` runs the first command that it finds that matches the pattern, starting with the most recent commands.</span></span>

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> <span data-ttu-id="806c3-125">Сопоставление шаблонов не учитывает регистр, но шаблон соответствует началу строки.</span><span class="sxs-lookup"><span data-stu-id="806c3-125">Pattern matching is case-insensitive, but the pattern matches the beginning of the line.</span></span>

### <span data-ttu-id="806c3-126">Пример 4. выполнение последовательности команд из журнала</span><span class="sxs-lookup"><span data-stu-id="806c3-126">Example 4: Run a sequence of commands from the history</span></span>

<span data-ttu-id="806c3-127">В этом примере выполняются команды от 16 до 24.</span><span class="sxs-lookup"><span data-stu-id="806c3-127">This example runs commands 16 through 24.</span></span> <span data-ttu-id="806c3-128">Так как вы можете вывести только одно значение **идентификатора** , команда использует `ForEach-Object` командлет для выполнения `Invoke-History` команды один раз для каждого значения **идентификатора** .</span><span class="sxs-lookup"><span data-stu-id="806c3-128">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command one time for each **Id** value.</span></span>

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### <span data-ttu-id="806c3-129">Пример 5</span><span class="sxs-lookup"><span data-stu-id="806c3-129">Example 5</span></span>

<span data-ttu-id="806c3-130">В этом примере выполняются семь команд в журнале, которые заканчиваются командой 255 (от 249 до 255).</span><span class="sxs-lookup"><span data-stu-id="806c3-130">This example runs the seven commands in the history that end with command 255 (249 through 255).</span></span> <span data-ttu-id="806c3-131">Он использует `Get-History` командлет для получения команд.</span><span class="sxs-lookup"><span data-stu-id="806c3-131">It uses the `Get-History` cmdlet to retrieve the commands.</span></span> <span data-ttu-id="806c3-132">Так как можно вывести только одно значение **идентификатора** , команда использует `ForEach-Object` командлет для `Invoke-History` однократного выполнения команды для каждого значения **идентификатора** .</span><span class="sxs-lookup"><span data-stu-id="806c3-132">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command once for each **Id** value.</span></span>

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## <span data-ttu-id="806c3-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="806c3-133">PARAMETERS</span></span>

### <span data-ttu-id="806c3-134">-Id</span><span class="sxs-lookup"><span data-stu-id="806c3-134">-Id</span></span>

<span data-ttu-id="806c3-135">Указывает **идентификатор** команды в журнале.</span><span class="sxs-lookup"><span data-stu-id="806c3-135">Specifies the **Id** of a command in the history.</span></span> <span data-ttu-id="806c3-136">Можно ввести **идентификационный** номер команды или несколько первых символов команды.</span><span class="sxs-lookup"><span data-stu-id="806c3-136">You can type the **Id** number of the command or the first few characters of the command.</span></span>

<span data-ttu-id="806c3-137">Если ввести символы, `Invoke-History` сначала будет соответствовать последним командам.</span><span class="sxs-lookup"><span data-stu-id="806c3-137">If you type characters, `Invoke-History` matches the most recent commands first.</span></span> <span data-ttu-id="806c3-138">Если этот параметр не указан, `Invoke-History` выполняет последнюю или последнюю команду.</span><span class="sxs-lookup"><span data-stu-id="806c3-138">If you omit this parameter, `Invoke-History` runs the last, or most recent, command.</span></span> <span data-ttu-id="806c3-139">Чтобы найти **идентификационный** номер команды, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="806c3-139">To find the **Id** number of a command, use the `Get-History` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="806c3-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="806c3-140">-Confirm</span></span>

<span data-ttu-id="806c3-141">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="806c3-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="806c3-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="806c3-142">-WhatIf</span></span>

<span data-ttu-id="806c3-143">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="806c3-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="806c3-144">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="806c3-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="806c3-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="806c3-145">CommonParameters</span></span>

<span data-ttu-id="806c3-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="806c3-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="806c3-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="806c3-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="806c3-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="806c3-148">INPUTS</span></span>

### <span data-ttu-id="806c3-149">System.String</span><span class="sxs-lookup"><span data-stu-id="806c3-149">System.String</span></span>

<span data-ttu-id="806c3-150">**Идентификатор** журнала можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="806c3-150">You can pipe a history **Id** to this cmdlet.</span></span>

## <span data-ttu-id="806c3-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="806c3-151">OUTPUTS</span></span>

### <span data-ttu-id="806c3-152">Нет</span><span class="sxs-lookup"><span data-stu-id="806c3-152">None</span></span>

<span data-ttu-id="806c3-153">Этот командлет не создает никаких выходных данных, но выходные данные могут создаваться командами, `Invoke-History` запускающими.</span><span class="sxs-lookup"><span data-stu-id="806c3-153">This cmdlet does not generate any output, but output might be generated by the commands that `Invoke-History` runs.</span></span>

## <span data-ttu-id="806c3-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="806c3-154">NOTES</span></span>

<span data-ttu-id="806c3-155">Журнал сеанса — это список команд, введенных за время сеанса.</span><span class="sxs-lookup"><span data-stu-id="806c3-155">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="806c3-156">В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="806c3-156">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="806c3-157">По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="806c3-157">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="806c3-158">Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="806c3-158">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="806c3-159">Также можно ссылаться `Invoke-History` по встроенным псевдонимам `r` и `ihy` .</span><span class="sxs-lookup"><span data-stu-id="806c3-159">You can also refer to `Invoke-History` by its built-in aliases, `r` and `ihy`.</span></span> <span data-ttu-id="806c3-160">Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="806c3-160">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="806c3-161">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="806c3-161">RELATED LINKS</span></span>

[<span data-ttu-id="806c3-162">Add-History</span><span class="sxs-lookup"><span data-stu-id="806c3-162">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="806c3-163">Clear-History</span><span class="sxs-lookup"><span data-stu-id="806c3-163">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="806c3-164">Get-History</span><span class="sxs-lookup"><span data-stu-id="806c3-164">Get-History</span></span>](Get-History.md)
