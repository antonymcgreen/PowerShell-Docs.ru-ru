---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 97d342d9f5d7227fb831794055c2cfa75b8cf765
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233166"
---
# <span data-ttu-id="1b52c-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="1b52c-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="1b52c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1b52c-104">SYNOPSIS</span></span>
<span data-ttu-id="1b52c-105">Привязывает ключи к функциям, определяемым пользователем или PSReadLine Key.</span><span class="sxs-lookup"><span data-stu-id="1b52c-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="1b52c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1b52c-106">SYNTAX</span></span>

### <span data-ttu-id="1b52c-107">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="1b52c-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="1b52c-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="1b52c-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="1b52c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1b52c-109">DESCRIPTION</span></span>

<span data-ttu-id="1b52c-110">`Set-PSReadLineKeyHandler`Командлет настраивает результат при нажатии клавиши или последовательности клавиш.</span><span class="sxs-lookup"><span data-stu-id="1b52c-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="1b52c-111">С помощью пользовательских привязок клавиш можно практически все, что можно сделать в сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b52c-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="1b52c-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="1b52c-112">EXAMPLES</span></span>

### <span data-ttu-id="1b52c-113">Пример 1. Привязка клавиши со стрелкой к функции</span><span class="sxs-lookup"><span data-stu-id="1b52c-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="1b52c-114">Эта команда привязывает клавишу Стрелка вверх к функции **хисторисеарчбакквард** .</span><span class="sxs-lookup"><span data-stu-id="1b52c-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="1b52c-115">Эта функция выполняет поиск в журнале команд командных строк, начинающихся с текущего содержимого командной строки.</span><span class="sxs-lookup"><span data-stu-id="1b52c-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="1b52c-116">Пример 2. Привязка ключа к блоку сценария</span><span class="sxs-lookup"><span data-stu-id="1b52c-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="1b52c-117">В этом примере показано, как можно использовать один ключ для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="1b52c-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="1b52c-118">Команда привязывает ключ `Ctrl+B` к блоку скрипта, который очищает строку, вставляет слово «Build», а затем принимает строку.</span><span class="sxs-lookup"><span data-stu-id="1b52c-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="1b52c-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1b52c-119">PARAMETERS</span></span>

### <span data-ttu-id="1b52c-120">-Бриефдескриптион</span><span class="sxs-lookup"><span data-stu-id="1b52c-120">-BriefDescription</span></span>

<span data-ttu-id="1b52c-121">Краткое описание сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="1b52c-121">A brief description of the key binding.</span></span> <span data-ttu-id="1b52c-122">Это описание отображается `Get-PSReadLineKeyHandler` командлетом.</span><span class="sxs-lookup"><span data-stu-id="1b52c-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b52c-123">-Chord</span><span class="sxs-lookup"><span data-stu-id="1b52c-123">-Chord</span></span>

<span data-ttu-id="1b52c-124">Ключ или последовательность ключей, которые должны быть привязаны к блоку функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="1b52c-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="1b52c-125">Используйте одну строку для указания одной привязки.</span><span class="sxs-lookup"><span data-stu-id="1b52c-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="1b52c-126">Если привязка представляет собой сочетание клавиш, разделите сочетания запятой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1b52c-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

<span data-ttu-id="1b52c-127">Этот параметр принимает массив строк.</span><span class="sxs-lookup"><span data-stu-id="1b52c-127">This parameter accepts an array of strings.</span></span> <span data-ttu-id="1b52c-128">Каждая строка — это отдельная привязка, а не сочетание клавиш для одной привязки.</span><span class="sxs-lookup"><span data-stu-id="1b52c-128">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b52c-129">-Description</span><span class="sxs-lookup"><span data-stu-id="1b52c-129">-Description</span></span>

<span data-ttu-id="1b52c-130">Задает более подробное описание привязки ключа, которое отображается в выходных данных `Get-PSReadLineKeyHandler` командлета.</span><span class="sxs-lookup"><span data-stu-id="1b52c-130">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b52c-131">-Function</span><span class="sxs-lookup"><span data-stu-id="1b52c-131">-Function</span></span>

<span data-ttu-id="1b52c-132">Указывает имя существующего обработчика ключей, предоставляемого PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="1b52c-132">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="1b52c-133">Этот параметр позволяет повторно привязывать существующие привязки к ключам или привязывать обработчик, который в настоящее время не привязан.</span><span class="sxs-lookup"><span data-stu-id="1b52c-133">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b52c-134">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="1b52c-134">-ScriptBlock</span></span>

<span data-ttu-id="1b52c-135">Задает значение блока скрипта для запуска при входе в аккорд.</span><span class="sxs-lookup"><span data-stu-id="1b52c-135">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="1b52c-136">PSReadLine передает один или два параметра в этот блок сценария.</span><span class="sxs-lookup"><span data-stu-id="1b52c-136">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="1b52c-137">Первый параметр — это объект **консолекэйинфо** , представляющий нажатую клавишу.</span><span class="sxs-lookup"><span data-stu-id="1b52c-137">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="1b52c-138">Вторым аргументом может быть любой объект в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="1b52c-138">The second argument can be any object depending on the context.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b52c-139">-Вимоде</span><span class="sxs-lookup"><span data-stu-id="1b52c-139">-ViMode</span></span>

<span data-ttu-id="1b52c-140">Укажите режим VI, к которому применяется привязка.</span><span class="sxs-lookup"><span data-stu-id="1b52c-140">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="1b52c-141">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="1b52c-141">Valid values are:</span></span>

- <span data-ttu-id="1b52c-142">Вставить</span><span class="sxs-lookup"><span data-stu-id="1b52c-142">Insert</span></span>
- <span data-ttu-id="1b52c-143">Get-Help</span><span class="sxs-lookup"><span data-stu-id="1b52c-143">Command</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b52c-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1b52c-144">CommonParameters</span></span>

<span data-ttu-id="1b52c-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1b52c-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1b52c-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1b52c-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1b52c-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1b52c-147">INPUTS</span></span>

### <span data-ttu-id="1b52c-148">Нет</span><span class="sxs-lookup"><span data-stu-id="1b52c-148">None</span></span>

<span data-ttu-id="1b52c-149">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="1b52c-149">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="1b52c-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1b52c-150">OUTPUTS</span></span>

### <span data-ttu-id="1b52c-151">Нет</span><span class="sxs-lookup"><span data-stu-id="1b52c-151">None</span></span>

<span data-ttu-id="1b52c-152">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="1b52c-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1b52c-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1b52c-153">NOTES</span></span>

## <span data-ttu-id="1b52c-154">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1b52c-154">RELATED LINKS</span></span>

[<span data-ttu-id="1b52c-155">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="1b52c-155">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="1b52c-156">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="1b52c-156">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="1b52c-157">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="1b52c-157">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="1b52c-158">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="1b52c-158">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

