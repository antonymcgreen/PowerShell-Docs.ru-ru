---
external help file: ISE-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226854"
---
# <span data-ttu-id="c1e11-103">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="c1e11-103">New-IseSnippet</span></span>

## <span data-ttu-id="c1e11-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c1e11-104">SYNOPSIS</span></span>
<span data-ttu-id="c1e11-105">Создает фрагмент кода интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-105">Creates a Windows PowerShell ISE code snippet.</span></span>

## <span data-ttu-id="c1e11-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1e11-106">SYNTAX</span></span>

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="c1e11-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1e11-107">DESCRIPTION</span></span>

<span data-ttu-id="c1e11-108">`New-ISESnippet`Командлет создает многократно используемый текст "Snippet" для интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-108">The `New-ISESnippet` cmdlet creates a reusable text "snippet" for Windows PowerShell ISE.</span></span> <span data-ttu-id="c1e11-109">Фрагменты кода можно использовать для добавления текста в области сценариев или команд интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-109">You can use snippets to add text to the Script pane or Command pane in Windows PowerShell ISE.</span></span> <span data-ttu-id="c1e11-110">Этот командлет доступен только в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-110">This cmdlet is available only in Windows PowerShell ISE.</span></span>

<span data-ttu-id="c1e11-111">Начиная с Windows PowerShell 3.0, интегрированная среда сценариев Windows PowerShell содержит набор встроенных фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="c1e11-111">Beginning in Windows PowerShell 3.0, Windows PowerShell ISE includes a collection of built-in snippets.</span></span> <span data-ttu-id="c1e11-112">`New-ISESnippet`Командлет позволяет создавать собственные фрагменты кода для добавления во встроенную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="c1e11-112">The `New-ISESnippet` cmdlet lets you create your own snippets to add to the built-in collection.</span></span> <span data-ttu-id="c1e11-113">Можно просмотреть, изменить, добавить, удалить и совместно использовать файлы фрагментов кода и включать их в модули Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-113">You can view, change, add, delete, and share snippet files and include them in Windows PowerShell modules.</span></span> <span data-ttu-id="c1e11-114">Чтобы просмотреть фрагменты в интегрированной среде сценариев Windows PowerShell, в меню **Правка** выберите команду **начать фрагменты** или нажмите клавиши <kbd>CTRL</kbd> + <kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="c1e11-114">To see snippets in Windows PowerShell ISE, from the **Edit** menu, select **Start Snippets** or press <kbd>CTRL</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="c1e11-115">`New-ISESnippet`Командлет создает `<Title>.Snippets.ps1xml` файл в `$home\Documents\WindowsPowerShell\Snippets` каталоге с указанным заголовком.</span><span class="sxs-lookup"><span data-stu-id="c1e11-115">The `New-ISESnippet` cmdlet creates a `<Title>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory with the title that you specify.</span></span> <span data-ttu-id="c1e11-116">Чтобы включить файл фрагмента кода в модуль, который вы создаете, добавьте этот файл в подкаталог Snippets вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="c1e11-116">To include a snippet file in a module that you are authoring, add the snippet file to a Snippets subdirectory of your module directory.</span></span>

<span data-ttu-id="c1e11-117">В сеансе, в котором политика выполнения **ограничена** или **AllSigned** , нельзя использовать созданные пользователем фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="c1e11-117">You cannot use user-created snippets in a session in which the execution policy is **Restricted** or **AllSigned**.</span></span>

<span data-ttu-id="c1e11-118">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c1e11-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c1e11-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1e11-119">EXAMPLES</span></span>

### <span data-ttu-id="c1e11-120">Пример 1. Создание Comment-Based фрагмента справки</span><span class="sxs-lookup"><span data-stu-id="c1e11-120">Example 1: Create a Comment-Based help snippet</span></span>

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

<span data-ttu-id="c1e11-121">Эта команда создает фрагмент Comment-BasedHelp для интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-121">This command creates a Comment-BasedHelp snippet for Windows PowerShell ISE.</span></span> <span data-ttu-id="c1e11-122">Он создает файл с именем `Comment-BasedHelp.snippets.ps1xml` в каталоге фрагментов пользователя `$home\Documents\WindowsPowerShell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="c1e11-122">It creates a file named `Comment-BasedHelp.snippets.ps1xml` in the user's Snippets directory `$home\Documents\WindowsPowerShell\Snippets`.</span></span>

### <span data-ttu-id="c1e11-123">Пример 2. Создание обязательного фрагмента кода</span><span class="sxs-lookup"><span data-stu-id="c1e11-123">Example 2: Create a mandatory snippet</span></span>

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

<span data-ttu-id="c1e11-124">В этом примере создается фрагмент кода с именем " **обязательный** " для интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-124">This example creates a snippet named **Mandatory** for Windows PowerShell ISE.</span></span> <span data-ttu-id="c1e11-125">Первая команда сохраняет текст фрагмента в `$M` переменной.</span><span class="sxs-lookup"><span data-stu-id="c1e11-125">The first command saves the snippet text in the `$M` variable.</span></span> <span data-ttu-id="c1e11-126">Вторая команда использует `New-ISESnippet` командлет для создания фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="c1e11-126">The second command uses the `New-ISESnippet` cmdlet to create the snippet.</span></span> <span data-ttu-id="c1e11-127">Команда использует параметр **Force** для перезаписи предыдущего фрагмента с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c1e11-127">The command uses the **Force** parameter to overwrite a previous snippet with the same name.</span></span>

### <span data-ttu-id="c1e11-128">Пример 3. копирование обязательного фрагмента из папки в папку назначения</span><span class="sxs-lookup"><span data-stu-id="c1e11-128">Example 3: Copy a mandatory snippet from a folder to a destination folder</span></span>

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

<span data-ttu-id="c1e11-129">Эта команда использует `Copy-Item` командлет для копирования **обязательного** фрагмента из папки, в которой `New-ISESnippet` он размещается в общей папке Server\Share.</span><span class="sxs-lookup"><span data-stu-id="c1e11-129">This command uses the `Copy-Item` cmdlet to copy the **Mandatory** snippet from the folder where `New-ISESnippet` places it to the Server\Share file share.</span></span>

## <span data-ttu-id="c1e11-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1e11-130">PARAMETERS</span></span>

### <span data-ttu-id="c1e11-131">-Author</span><span class="sxs-lookup"><span data-stu-id="c1e11-131">-Author</span></span>

<span data-ttu-id="c1e11-132">Указывает автора фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="c1e11-132">Specifies the author of the snippet.</span></span> <span data-ttu-id="c1e11-133">Поле автора отображается в файле фрагмента кода, но не отображается при выборе имени фрагмента в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-133">The author field appears in the snippet file, but it does not appear when you click the snippet name in Windows PowerShell ISE.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1e11-134">-Каретоффсет</span><span class="sxs-lookup"><span data-stu-id="c1e11-134">-CaretOffset</span></span>

<span data-ttu-id="c1e11-135">Задает символ текста фрагмента, на который этот командлет помещает курсор.</span><span class="sxs-lookup"><span data-stu-id="c1e11-135">Specifies the character of the snippet text that this cmdlet places the cursor on.</span></span> <span data-ttu-id="c1e11-136">Введите целое число, представляющее позицию курсора (значение 1 представляет первый символ текста).</span><span class="sxs-lookup"><span data-stu-id="c1e11-136">Enter an integer that represents the cursor position, with "1" representing the first character of text.</span></span> <span data-ttu-id="c1e11-137">Значение по умолчанию — 0 (ноль) — помещает курсор непосредственно перед первым символом в тексте.</span><span class="sxs-lookup"><span data-stu-id="c1e11-137">The default value, 0 (zero), places the cursor immediately before the first character of text.</span></span> <span data-ttu-id="c1e11-138">Этот параметр создает отступ для текста фрагмента.</span><span class="sxs-lookup"><span data-stu-id="c1e11-138">This parameter does not indent the snippet text.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1e11-139">-Description</span><span class="sxs-lookup"><span data-stu-id="c1e11-139">-Description</span></span>

<span data-ttu-id="c1e11-140">Задает описание фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="c1e11-140">Specifies a description of the snippet.</span></span> <span data-ttu-id="c1e11-141">Значение описания отображается при выборе имени фрагмента в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-141">The description value appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="c1e11-142">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="c1e11-142">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1e11-143">-Force</span><span class="sxs-lookup"><span data-stu-id="c1e11-143">-Force</span></span>

<span data-ttu-id="c1e11-144">Указывает, что этот командлет перезаписывает файлы фрагментов кода с тем же именем в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="c1e11-144">Indicates that this cmdlet overwrites snippet files with the same name in the same location.</span></span> <span data-ttu-id="c1e11-145">По умолчанию не `New-ISESnippet` перезаписывает файлы.</span><span class="sxs-lookup"><span data-stu-id="c1e11-145">By default, `New-ISESnippet` does not overwrite files.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1e11-146">— Текст</span><span class="sxs-lookup"><span data-stu-id="c1e11-146">-Text</span></span>

<span data-ttu-id="c1e11-147">Указывает текстовое значение, которое добавляется при выборе фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="c1e11-147">Specifies the text value that is added when you select the snippet.</span></span> <span data-ttu-id="c1e11-148">Текст фрагмента отображается при выборе имени фрагмента в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-148">The snippet text appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="c1e11-149">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="c1e11-149">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1e11-150">-Title</span><span class="sxs-lookup"><span data-stu-id="c1e11-150">-Title</span></span>

<span data-ttu-id="c1e11-151">Указывает заголовок или имя фрагмента.</span><span class="sxs-lookup"><span data-stu-id="c1e11-151">Specifies a title or name for the snippet.</span></span> <span data-ttu-id="c1e11-152">Заголовок также выступает в качестве имени файла фрагмента.</span><span class="sxs-lookup"><span data-stu-id="c1e11-152">The title also names the snippet file.</span></span> <span data-ttu-id="c1e11-153">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="c1e11-153">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1e11-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c1e11-154">CommonParameters</span></span>

<span data-ttu-id="c1e11-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1e11-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1e11-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1e11-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1e11-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c1e11-157">INPUTS</span></span>

### <span data-ttu-id="c1e11-158">Нет</span><span class="sxs-lookup"><span data-stu-id="c1e11-158">None</span></span>

<span data-ttu-id="c1e11-159">Этот командлет не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c1e11-159">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="c1e11-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c1e11-160">OUTPUTS</span></span>

### <span data-ttu-id="c1e11-161">Нет</span><span class="sxs-lookup"><span data-stu-id="c1e11-161">None</span></span>

<span data-ttu-id="c1e11-162">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c1e11-162">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c1e11-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c1e11-163">NOTES</span></span>

<span data-ttu-id="c1e11-164">`New-IseSnippet` сохраняет новые созданные пользователем фрагменты в неподписанных файлах. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="c1e11-164">`New-IseSnippet` stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="c1e11-165">Таким образом, Windows PowerShell не может добавить их в сеанс, для которого действует политика выполнения **AllSigned** или **Restricted**.</span><span class="sxs-lookup"><span data-stu-id="c1e11-165">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted**.</span></span> <span data-ttu-id="c1e11-166">В сеансе **Restricted** или **AllSigned** можно создать, получить и импортировать созданные пользователем неподписанные фрагменты кода, но их нельзя использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c1e11-166">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

<span data-ttu-id="c1e11-167">При использовании `New-IseSnippet` командлета в **ограниченном** или **AllSigned** сеансе создается фрагмент, но при попытке Windows PowerShell добавить в сеанс только что созданный фрагмент кода появляется сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c1e11-167">If you use the `New-IseSnippet` cmdlet in a **Restricted** or **AllSigned** session, the snippet is created, but an error message appears when Windows PowerShell tries to add the newly created snippet to the session.</span></span> <span data-ttu-id="c1e11-168">Чтобы использовать новый фрагмент кода (и другие созданные пользователем неподписанные фрагменты), измените политику выполнения и перезагрузите интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-168">To use the new snippet (and other unsigned user-created snippets), change the execution policy, and then restart Windows PowerShell ISE.</span></span>

<span data-ttu-id="c1e11-169">Дополнительные сведения о политиках выполнения Windows PowerShell см. в разделе about_Execution_Policies.</span><span class="sxs-lookup"><span data-stu-id="c1e11-169">For more information about Windows PowerShell execution policies, see about_Execution_Policies.</span></span>

- <span data-ttu-id="c1e11-170">Чтобы изменить фрагмент, измените файл фрагмента.</span><span class="sxs-lookup"><span data-stu-id="c1e11-170">To change a snippet, edit the snippet file.</span></span> <span data-ttu-id="c1e11-171">Файлы фрагментов кода можно изменить на панели скриптов ИНТЕГРИРОВАНной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-171">You can edit snippet files in the Script pane of Windows PowerShell ISE.</span></span>
- <span data-ttu-id="c1e11-172">Чтобы удалить добавленный фрагмент, удалите файл фрагмента.</span><span class="sxs-lookup"><span data-stu-id="c1e11-172">To delete a snippet that you added, delete the snippet file.</span></span>
- <span data-ttu-id="c1e11-173">Нельзя удалить встроенный фрагмент, но можно скрыть все встроенные фрагменты с помощью $psise. Команда Options. Шовдефаултсниппетс = $false ".</span><span class="sxs-lookup"><span data-stu-id="c1e11-173">You cannot delete a built-in snippet, but you can hide all built-in snippets by using the "$psise.Options.ShowDefaultSnippets=$false" command.</span></span>
- <span data-ttu-id="c1e11-174">Можно создать фрагмент кода с тем же именем, что и у встроенного фрагмента.</span><span class="sxs-lookup"><span data-stu-id="c1e11-174">You can create a snippet that has the same name as a built-in snippet.</span></span> <span data-ttu-id="c1e11-175">Оба фрагмента отображаются в меню фрагментов интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e11-175">Both snippets appear in the snippet menu in Windows PowerShell ISE.</span></span>

## <span data-ttu-id="c1e11-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c1e11-176">RELATED LINKS</span></span>

[<span data-ttu-id="c1e11-177">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="c1e11-177">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="c1e11-178">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="c1e11-178">Import-IseSnippet</span></span>](Import-IseSnippet.md)
