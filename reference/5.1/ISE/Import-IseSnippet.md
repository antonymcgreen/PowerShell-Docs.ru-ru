---
external help file: ISE-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226857"
---
# <span data-ttu-id="e4600-103">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="e4600-103">Import-IseSnippet</span></span>

## <span data-ttu-id="e4600-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e4600-104">SYNOPSIS</span></span>
<span data-ttu-id="e4600-105">Импортирует фрагменты кода интегрированной среды сценариев в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e4600-105">Imports ISE snippets into the current session</span></span>

## <span data-ttu-id="e4600-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4600-106">SYNTAX</span></span>

### <span data-ttu-id="e4600-107">Фромфолдер (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e4600-107">FromFolder (Default)</span></span>

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### <span data-ttu-id="e4600-108">фроммодуле</span><span class="sxs-lookup"><span data-stu-id="e4600-108">FromModule</span></span>

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="e4600-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4600-109">DESCRIPTION</span></span>

<span data-ttu-id="e4600-110">`Import-IseSnippet`Командлет импортирует многократно используемые текстовые фрагменты из модуля или каталога в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e4600-110">The `Import-IseSnippet` cmdlet imports reusable text "snippets" from a module or a directory into the current session.</span></span> <span data-ttu-id="e4600-111">Фрагменты кода немедленно доступны для использования в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4600-111">The snippets are immediately available for use in Windows PowerShell ISE.</span></span> <span data-ttu-id="e4600-112">Этот командлет работает только в интегрированной среде сценариев (ISE) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4600-112">This cmdlet works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="e4600-113">Чтобы просмотреть и использовать импортированные фрагменты, в меню " **Правка** " интегрированной среды сценариев Windows PowerShell нажмите кнопку " **начать фрагменты** " или нажмите клавиши <kbd>CTRL</kbd> + <kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e4600-113">To view and use the imported snippets, from the Windows PowerShell ISE **Edit** menu, click **Start Snippets** or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="e4600-114">Импортированные фрагменты кода доступны только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="e4600-114">Imported snippets are available only in the current session.</span></span> <span data-ttu-id="e4600-115">Чтобы импортировать фрагменты во все сеансы интегрированной среды сценариев Windows PowerShell, добавьте `Import-IseSnippet` команду в профиль Windows PowerShell или скопируйте файлы фрагментов в каталог локальных фрагментов `$home\Documents\WindowsPowershell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="e4600-115">To import the snippets into all Windows PowerShell ISE sessions, add an `Import-IseSnippet` command to your Windows PowerShell profile or copy the snippet files to your local snippets directory `$home\Documents\WindowsPowershell\Snippets`.</span></span>

<span data-ttu-id="e4600-116">Чтобы импортировать фрагменты кода, они должны быть правильно отформатированы во фрагментах кода XML для интегрированной среды сценариев Windows PowerShell и сохранены в файлах Snippet.ps1XML.</span><span class="sxs-lookup"><span data-stu-id="e4600-116">To import snippets, they must be properly formatted in the snippet XML for Windows PowerShell ISE snippets and saved in Snippet.ps1xml files.</span></span> <span data-ttu-id="e4600-117">Чтобы создать подходящие фрагменты кода, используйте `New-IseSnippet` командлет.</span><span class="sxs-lookup"><span data-stu-id="e4600-117">To create eligible snippets, use the `New-IseSnippet` cmdlet.</span></span> <span data-ttu-id="e4600-118">`New-IseSnippet` создает `<SnippetTitle>.Snippets.ps1xml` файл в `$home\Documents\WindowsPowerShell\Snippets` каталоге.</span><span class="sxs-lookup"><span data-stu-id="e4600-118">`New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span> <span data-ttu-id="e4600-119">Можно переместить или скопировать фрагменты кода в каталог Snippets модуля Windows PowerShell или в любой другой каталог.</span><span class="sxs-lookup"><span data-stu-id="e4600-119">You can move or copy the snippets to the Snippets directory of a Windows PowerShell module, or to any other directory.</span></span>

<span data-ttu-id="e4600-120">`Get-IseSnippet`Командлет, который получает созданные пользователем фрагменты в каталоге локальных фрагментов, не получает импортированные фрагменты.</span><span class="sxs-lookup"><span data-stu-id="e4600-120">The `Get-IseSnippet` cmdlet, which gets user-created snippets in the local snippets directory, does not get imported snippets.</span></span>

<span data-ttu-id="e4600-121">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e4600-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="e4600-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="e4600-122">EXAMPLES</span></span>

### <span data-ttu-id="e4600-123">Пример 1. Импорт фрагментов из каталога</span><span class="sxs-lookup"><span data-stu-id="e4600-123">Example 1: Import snippets from a directory</span></span>

<span data-ttu-id="e4600-124">В этом примере фрагменты кода импортируются из `\\Server01\Public\Snippets` каталога в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e4600-124">This example imports the snippets from the `\\Server01\Public\Snippets` directory into the current session.</span></span> <span data-ttu-id="e4600-125">Он использует параметр **рекурсии** для получения фрагментов из всех подкаталогов каталога фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="e4600-125">It uses the **Recurse** parameter to get snippets from all subdirectories of the Snippets directory.</span></span>

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### <span data-ttu-id="e4600-126">Пример 2. Импорт фрагментов кода из модуля</span><span class="sxs-lookup"><span data-stu-id="e4600-126">Example 2: Import snippets from a module</span></span>

<span data-ttu-id="e4600-127">В этом примере выполняется импорт фрагментов кода из модуля **сниппетмодуле** .</span><span class="sxs-lookup"><span data-stu-id="e4600-127">This example imports the snippets from the **SnippetModule** module.</span></span> <span data-ttu-id="e4600-128">Команда использует параметр **ListAvailable** для импорта фрагментов, даже если модуль **сниппетмодуле** не импортируется в сеанс пользователя при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="e4600-128">The command uses the **ListAvailable** parameter to import the snippets even if the **SnippetModule** module is not imported into the user's session when the command runs.</span></span>

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### <span data-ttu-id="e4600-129">Пример 3. Поиск фрагментов в модулях</span><span class="sxs-lookup"><span data-stu-id="e4600-129">Example 3: Find snippets in modules</span></span>

<span data-ttu-id="e4600-130">Этот пример получает фрагменты во всех установленных модулях в переменной среды PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="e4600-130">This example gets snippets in all installed modules in the PSModulePath environment variable.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### <span data-ttu-id="e4600-131">Пример 4. импорт всех фрагментов модулей</span><span class="sxs-lookup"><span data-stu-id="e4600-131">Example 4: Import all module snippets</span></span>

<span data-ttu-id="e4600-132">В этом примере выполняется импорт всех фрагментов кода из всех установленных модулей в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e4600-132">This example imports all snippets from all installed modules into the current session.</span></span> <span data-ttu-id="e4600-133">Как правило, выполнять такую команду не требуется, так как модули с фрагментами кода будут использовать `Import-IseSnippet` командлет для импорта при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="e4600-133">Typically, you don't need to run a command like this because modules that have snippets will use the `Import-IseSnippet` cmdlet to import them for you when the module is imported.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### <span data-ttu-id="e4600-134">Пример 5. копирование всех фрагментов модулей</span><span class="sxs-lookup"><span data-stu-id="e4600-134">Example 5: Copy all module snippets</span></span>

<span data-ttu-id="e4600-135">В этом примере файлы фрагментов кода копируются из всех установленных модулей в Каталог фрагментов текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e4600-135">This example copies the snippet files from all installed modules into the Snippets directory of the current user.</span></span> <span data-ttu-id="e4600-136">В отличие от импортированных фрагменты кода, влияющие только на текущий сеанс, скопированные фрагменты доступны в каждом сеансе интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4600-136">Unlike imported snippets, which affect only the current session, copied snippets are available in every Windows PowerShell ISE session.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## <span data-ttu-id="e4600-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4600-137">PARAMETERS</span></span>

### <span data-ttu-id="e4600-138">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="e4600-138">-ListAvailable</span></span>

<span data-ttu-id="e4600-139">Указывает, что этот командлет получает фрагменты кода из модулей, установленных на компьютере, даже если модули не импортируются в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e4600-139">Indicates that this cmdlet gets snippets from modules that are installed on the computer, even if the modules are not imported into the current session.</span></span> <span data-ttu-id="e4600-140">Если этот параметр не указан и модуль, указанный в параметре **module** , не импортируется в текущий сеанс, попытка получить фрагменты кода из модуля завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e4600-140">If this parameter is omitted, and the module that is specified by the **Module** parameter is not imported into the current session, the attempt to get the snippets from the module fails.</span></span>

<span data-ttu-id="e4600-141">Этот параметр активен, только если в команде также используется параметр **Module**.</span><span class="sxs-lookup"><span data-stu-id="e4600-141">This parameter is valid only when the **Module** parameter is used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4600-142">-Module</span><span class="sxs-lookup"><span data-stu-id="e4600-142">-Module</span></span>

<span data-ttu-id="e4600-143">Импортирует фрагменты кода из указанного модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e4600-143">Imports snippets from the specified module into the current session.</span></span> <span data-ttu-id="e4600-144">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e4600-144">Wildcard characters are not supported.</span></span>

<span data-ttu-id="e4600-145">Этот параметр импортирует фрагменты кода из файлов Snippet.ps1XML во вложенном каталоге фрагментов кода в пути к модулю, например `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="e4600-145">This parameter imports snippets from Snippet.ps1xml files in the Snippets subdirectory in the module path, such as `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets`.</span></span>

<span data-ttu-id="e4600-146">Этот параметр предназначен для использования авторами модулей в сценарии запуска, например, в сценарии, указанном в ключе **ScriptsToProcess** манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="e4600-146">This parameter is designed to be used by module authors in a startup script, such as a script specified in the **ScriptsToProcess** key of a module manifest.</span></span> <span data-ttu-id="e4600-147">Фрагменты кода в модуле не импортируются автоматически вместе с модулем, но `Import-IseSnippet` для их импорта можно использовать команду.</span><span class="sxs-lookup"><span data-stu-id="e4600-147">Snippets in a module are not automatically imported with the module, but you can use an `Import-IseSnippet` command to import them.</span></span>

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4600-148">-Path</span><span class="sxs-lookup"><span data-stu-id="e4600-148">-Path</span></span>

<span data-ttu-id="e4600-149">Указывает путь к каталогу фрагментов кода, в котором этот командлет импортирует фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="e4600-149">Specifies the path to the snippets directory in which this cmdlet imports snippets.</span></span>

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e4600-150">-Recurse</span><span class="sxs-lookup"><span data-stu-id="e4600-150">-Recurse</span></span>

<span data-ttu-id="e4600-151">Указывает, что этот командлет импортирует фрагменты кода из всех подкаталогов значения параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="e4600-151">Indicates that this cmdlet imports snippets from all subdirectories of the value of the **Path** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4600-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e4600-152">CommonParameters</span></span>

<span data-ttu-id="e4600-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4600-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4600-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e4600-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4600-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e4600-155">INPUTS</span></span>

### <span data-ttu-id="e4600-156">Нет</span><span class="sxs-lookup"><span data-stu-id="e4600-156">None</span></span>

<span data-ttu-id="e4600-157">Этот командлет не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e4600-157">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="e4600-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e4600-158">OUTPUTS</span></span>

### <span data-ttu-id="e4600-159">Нет</span><span class="sxs-lookup"><span data-stu-id="e4600-159">None</span></span>

<span data-ttu-id="e4600-160">Этот командлет не создает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e4600-160">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="e4600-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e4600-161">NOTES</span></span>

- <span data-ttu-id="e4600-162">Командлет нельзя использовать `Get-IseSnippet` для получения импортированных фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="e4600-162">You cannot use the `Get-IseSnippet` cmdlet to get imported snippets.</span></span> <span data-ttu-id="e4600-163">`Get-IseSnippet` Возвращает только фрагменты кода в `$home\Documents\WindowsPowerShell\Snippets` каталоге.</span><span class="sxs-lookup"><span data-stu-id="e4600-163">`Get-IseSnippet` gets only snippets in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
- <span data-ttu-id="e4600-164">`Import-IseSnippet` использует статический метод **Load** объектов **Microsoft. PowerShell. host. ISE. ISESnippetCollection** .</span><span class="sxs-lookup"><span data-stu-id="e4600-164">`Import-IseSnippet` uses the **Load** static method of **Microsoft.PowerShell.Host.ISE.ISESnippetCollection** objects.</span></span> <span data-ttu-id="e4600-165">Также можно использовать метод **Load** фрагментов кода в объектной модели интегрированной среды сценариев Windows PowerShell: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span><span class="sxs-lookup"><span data-stu-id="e4600-165">You can also use the **Load** method of snippets in the Windows PowerShell ISE object model: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span></span>
- <span data-ttu-id="e4600-166">`New-IseSnippet`Командлет сохраняет новые созданные пользователем фрагменты в неподписанных файлах. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="e4600-166">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="e4600-167">Таким образом, Windows PowerShell не может загрузить их в сеанс, для которого действует политика выполнения **AllSigned** или **Restricted**.</span><span class="sxs-lookup"><span data-stu-id="e4600-167">As such, Windows PowerShell cannot load them into a session in which the execution policy is **AllSigned** or **Restricted**.</span></span> <span data-ttu-id="e4600-168">В сеансе **Restricted** или **AllSigned** можно создать, получить и импортировать созданные пользователем неподписанные фрагменты кода, но их нельзя использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e4600-168">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="e4600-169">Чтобы использовать неподписанные пользовательские фрагменты кода, `Import-IseSnippet` возвращаемые командлетом, измените политику выполнения, а затем перезапустите интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4600-169">To use unsigned user-created snippets that the `Import-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="e4600-170">Дополнительные сведения о политиках выполнения Windows PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4600-170">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="e4600-171">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e4600-171">RELATED LINKS</span></span>

[<span data-ttu-id="e4600-172">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="e4600-172">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="e4600-173">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="e4600-173">New-IseSnippet</span></span>](New-IseSnippet.md)
