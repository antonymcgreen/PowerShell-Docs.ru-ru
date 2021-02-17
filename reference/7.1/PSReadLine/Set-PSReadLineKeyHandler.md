---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 02/16/2021
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: a6b3d437917e26909f5dd116f3d0afa944f4138d
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563331"
---
# <span data-ttu-id="98053-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="98053-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="98053-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="98053-104">SYNOPSIS</span></span>
<span data-ttu-id="98053-105">Привязывает ключи к функциям, определяемым пользователем или PSReadLine Key.</span><span class="sxs-lookup"><span data-stu-id="98053-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="98053-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="98053-106">SYNTAX</span></span>

### <span data-ttu-id="98053-107">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="98053-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="98053-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="98053-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="98053-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="98053-109">DESCRIPTION</span></span>

<span data-ttu-id="98053-110">`Set-PSReadLineKeyHandler`Командлет настраивает результат при нажатии клавиши или последовательности клавиш.</span><span class="sxs-lookup"><span data-stu-id="98053-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="98053-111">С помощью пользовательских привязок клавиш можно практически все, что можно сделать в сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98053-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="98053-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="98053-112">EXAMPLES</span></span>

### <span data-ttu-id="98053-113">Пример 1. Привязка клавиши со стрелкой к функции</span><span class="sxs-lookup"><span data-stu-id="98053-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="98053-114">Эта команда привязывает клавишу Стрелка вверх к функции **хисторисеарчбакквард** .</span><span class="sxs-lookup"><span data-stu-id="98053-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="98053-115">Эта функция выполняет поиск в журнале команд командных строк, начинающихся с текущего содержимого командной строки.</span><span class="sxs-lookup"><span data-stu-id="98053-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="98053-116">Пример 2. Привязка ключа к блоку сценария</span><span class="sxs-lookup"><span data-stu-id="98053-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="98053-117">В этом примере показано, как можно использовать один ключ для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="98053-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="98053-118">Команда привязывает ключ `Ctrl+B` к блоку скрипта, который очищает строку, вставляет слово «Build», а затем принимает строку.</span><span class="sxs-lookup"><span data-stu-id="98053-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="98053-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="98053-119">PARAMETERS</span></span>

### <span data-ttu-id="98053-120">-Бриефдескриптион</span><span class="sxs-lookup"><span data-stu-id="98053-120">-BriefDescription</span></span>

<span data-ttu-id="98053-121">Краткое описание сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="98053-121">A brief description of the key binding.</span></span> <span data-ttu-id="98053-122">Это описание отображается `Get-PSReadLineKeyHandler` командлетом.</span><span class="sxs-lookup"><span data-stu-id="98053-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="98053-123">-Chord</span><span class="sxs-lookup"><span data-stu-id="98053-123">-Chord</span></span>

<span data-ttu-id="98053-124">Ключ или последовательность ключей, которые должны быть привязаны к блоку функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="98053-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="98053-125">Используйте одну строку для указания одной привязки.</span><span class="sxs-lookup"><span data-stu-id="98053-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="98053-126">Если привязка представляет собой сочетание клавиш, разделите сочетания запятой, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="98053-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

> [!NOTE]
> <span data-ttu-id="98053-127">Начиная с PSReadLine 2.0.0, параметр **аккорд** **учитывает регистр**.</span><span class="sxs-lookup"><span data-stu-id="98053-127">As of PSReadLine 2.0.0, the **Chord** parameter is **case-sensitive**.</span></span> <span data-ttu-id="98053-128">Это означает, что `Ctrl+X` и `Ctrl+x` создаст разные привязки.</span><span class="sxs-lookup"><span data-stu-id="98053-128">Meaning, `Ctrl+X` and `Ctrl+x` will create different bindings.</span></span>

<span data-ttu-id="98053-129">Этот параметр принимает массив строк.</span><span class="sxs-lookup"><span data-stu-id="98053-129">This parameter accepts an array of strings.</span></span> <span data-ttu-id="98053-130">Каждая строка — это отдельная привязка, а не сочетание клавиш для одной привязки.</span><span class="sxs-lookup"><span data-stu-id="98053-130">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="98053-131">-Description</span><span class="sxs-lookup"><span data-stu-id="98053-131">-Description</span></span>

<span data-ttu-id="98053-132">Задает более подробное описание привязки ключа, которое отображается в выходных данных `Get-PSReadLineKeyHandler` командлета.</span><span class="sxs-lookup"><span data-stu-id="98053-132">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="98053-133">-Function</span><span class="sxs-lookup"><span data-stu-id="98053-133">-Function</span></span>

<span data-ttu-id="98053-134">Указывает имя существующего обработчика ключей, предоставляемого PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="98053-134">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="98053-135">Этот параметр позволяет повторно привязывать существующие привязки к ключам или привязывать обработчик, который в настоящее время не привязан.</span><span class="sxs-lookup"><span data-stu-id="98053-135">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

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

### <span data-ttu-id="98053-136">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="98053-136">-ScriptBlock</span></span>

<span data-ttu-id="98053-137">Задает значение блока скрипта для запуска при входе в аккорд.</span><span class="sxs-lookup"><span data-stu-id="98053-137">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="98053-138">PSReadLine передает один или два параметра в этот блок сценария.</span><span class="sxs-lookup"><span data-stu-id="98053-138">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="98053-139">Первый параметр — это объект **консолекэйинфо** , представляющий нажатую клавишу.</span><span class="sxs-lookup"><span data-stu-id="98053-139">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="98053-140">Вторым аргументом может быть любой объект в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="98053-140">The second argument can be any object depending on the context.</span></span>

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

### <span data-ttu-id="98053-141">-Вимоде</span><span class="sxs-lookup"><span data-stu-id="98053-141">-ViMode</span></span>

<span data-ttu-id="98053-142">Укажите режим VI, к которому применяется привязка.</span><span class="sxs-lookup"><span data-stu-id="98053-142">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="98053-143">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="98053-143">Valid values are:</span></span>

- <span data-ttu-id="98053-144">Атрибут Insert</span><span class="sxs-lookup"><span data-stu-id="98053-144">Insert</span></span>
- <span data-ttu-id="98053-145">Get-Help</span><span class="sxs-lookup"><span data-stu-id="98053-145">Command</span></span>

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

### <span data-ttu-id="98053-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="98053-146">CommonParameters</span></span>

<span data-ttu-id="98053-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="98053-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="98053-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="98053-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="98053-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="98053-149">INPUTS</span></span>

### <span data-ttu-id="98053-150">None</span><span class="sxs-lookup"><span data-stu-id="98053-150">None</span></span>

<span data-ttu-id="98053-151">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="98053-151">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="98053-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="98053-152">OUTPUTS</span></span>

### <span data-ttu-id="98053-153">None</span><span class="sxs-lookup"><span data-stu-id="98053-153">None</span></span>

<span data-ttu-id="98053-154">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="98053-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="98053-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="98053-155">NOTES</span></span>

## <span data-ttu-id="98053-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="98053-156">RELATED LINKS</span></span>

[<span data-ttu-id="98053-157">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="98053-157">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="98053-158">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="98053-158">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="98053-159">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="98053-159">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="98053-160">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="98053-160">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

