---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: bcba432fb52b327695b61a4475d4a93903a688a5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227998"
---
# <span data-ttu-id="0907f-103">Join-Path</span><span class="sxs-lookup"><span data-stu-id="0907f-103">Join-Path</span></span>

## <span data-ttu-id="0907f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0907f-104">SYNOPSIS</span></span>
<span data-ttu-id="0907f-105">Объединяет путь и его дочерний путь в один путь.</span><span class="sxs-lookup"><span data-stu-id="0907f-105">Combines a path and a child path into a single path.</span></span>

## <span data-ttu-id="0907f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0907f-106">SYNTAX</span></span>

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="0907f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0907f-107">DESCRIPTION</span></span>

<span data-ttu-id="0907f-108">`Join-Path`Командлет объединяет путь и дочерний путь в один путь.</span><span class="sxs-lookup"><span data-stu-id="0907f-108">The `Join-Path` cmdlet combines a path and child-path into a single path.</span></span>
<span data-ttu-id="0907f-109">Поставщик поддерживает разделители пути.</span><span class="sxs-lookup"><span data-stu-id="0907f-109">The provider supplies the path delimiters.</span></span>

## <span data-ttu-id="0907f-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="0907f-110">EXAMPLES</span></span>

### <span data-ttu-id="0907f-111">Пример 1. Объединение пути с дочерним путем</span><span class="sxs-lookup"><span data-stu-id="0907f-111">Example 1: Combine a path with a child path</span></span>

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

<span data-ttu-id="0907f-112">Эта команда использует `Join-Path` для объединения пути с ChildPath.</span><span class="sxs-lookup"><span data-stu-id="0907f-112">This command uses `Join-Path` to combine a path with a childpath.</span></span>

<span data-ttu-id="0907f-113">Так как команда выполняется от `FileSystem` поставщика, она предоставляет `\` Разделитель для объединения путей.</span><span class="sxs-lookup"><span data-stu-id="0907f-113">Since the command is executed from the `FileSystem` provider, it provides the `\` delimiter to join the paths.</span></span>

### <span data-ttu-id="0907f-114">Пример 2. объединение путей, которые уже содержат разделители каталогов</span><span class="sxs-lookup"><span data-stu-id="0907f-114">Example 2: Combine paths that already contain directory separators</span></span>

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

<span data-ttu-id="0907f-115">Существующие разделители каталогов `\` и обработаны, поэтому существует только один разделитель между `Path` и `ChildPath`</span><span class="sxs-lookup"><span data-stu-id="0907f-115">Existing directory separators `\` and handled so there is only one separator between `Path` and `ChildPath`</span></span>

### <span data-ttu-id="0907f-116">Пример 3. Отображение файлов и папок путем присоединения к пути с помощью дочернего пути</span><span class="sxs-lookup"><span data-stu-id="0907f-116">Example 3: Display files and folders by joining a path with a child path</span></span>

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

<span data-ttu-id="0907f-117">Эта команда отображает файлы и папки, на которые имеются ссылки, путем объединения \* пути к:\вин и системного \* дочернего пути.</span><span class="sxs-lookup"><span data-stu-id="0907f-117">This command displays the files and folders that are referenced by joining the C:\Win\* path and the System\* child path.</span></span>
<span data-ttu-id="0907f-118">Он отображает те же файлы и папки, что и `Get-ChildItem` , но отображает полный путь к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="0907f-118">It displays the same files and folders as `Get-ChildItem`, but it displays the fully qualified path to each item.</span></span>
<span data-ttu-id="0907f-119">В этой команде `Path` `ChildPath` имена и необязательные параметры опущены.</span><span class="sxs-lookup"><span data-stu-id="0907f-119">In this command, the `Path` and `ChildPath` optional parameter names are omitted.</span></span>

### <span data-ttu-id="0907f-120">Пример 4. Использование Join-Path с поставщиком реестра PowerShell</span><span class="sxs-lookup"><span data-stu-id="0907f-120">Example 4: Use Join-Path with the PowerShell registry provider</span></span>

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

<span data-ttu-id="0907f-121">Эта команда отображает разделы реестра `HKLM\System` , содержащиеся в подразделе реестра `ControlSet` .</span><span class="sxs-lookup"><span data-stu-id="0907f-121">This command displays the registry keys in the `HKLM\System` registry subkey that include `ControlSet`.</span></span>

<span data-ttu-id="0907f-122">`Resolve`Параметр, пытается разрешить присоединенный путь, включая подстановочные знаки из текущего пути поставщика.`HKLM:\`</span><span class="sxs-lookup"><span data-stu-id="0907f-122">The `Resolve` parameter, attempts to resolve the joined path, including wildcards from the current provider path `HKLM:\`</span></span>

### <span data-ttu-id="0907f-123">Пример 5. Объединение нескольких корней пути с помощью дочернего пути</span><span class="sxs-lookup"><span data-stu-id="0907f-123">Example 5: Combine multiple path roots with a child path</span></span>

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

<span data-ttu-id="0907f-124">Эта команда использует `Join-Path` для объединения нескольких корней пути с дочерним путем.</span><span class="sxs-lookup"><span data-stu-id="0907f-124">This command uses `Join-Path` to combine multiple path roots with a child path.</span></span>

> [!NOTE]
> <span data-ttu-id="0907f-125">Диски, указанные параметром, `Path` должны существовать, иначе соединение этой записи завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0907f-125">The Drives specified by `Path` must exist or the join of that entry will fail.</span></span>

### <span data-ttu-id="0907f-126">Пример 6. объединение корней диска файловой системы с дочерним путем</span><span class="sxs-lookup"><span data-stu-id="0907f-126">Example 6: Combine the roots of a file system drive with a child path</span></span>

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

<span data-ttu-id="0907f-127">Эта команда объединяет корни каждого диска файловой системы PowerShell в консоли с путем к дочернему каталогу SUBDIR.</span><span class="sxs-lookup"><span data-stu-id="0907f-127">This command combines the roots of each PowerShell file system drive in the console with the Subdir child path.</span></span>

<span data-ttu-id="0907f-128">Команда использует `Get-PSDrive` командлет для получения дисков PowerShell, поддерживаемых поставщиком FileSystem.</span><span class="sxs-lookup"><span data-stu-id="0907f-128">The command uses the `Get-PSDrive` cmdlet to get the PowerShell drives supported by the FileSystem provider.</span></span>
<span data-ttu-id="0907f-129">`ForEach-Object`Инструкция выбирает только свойство root `PSDriveInfo` объектов и объединяет его с указанным дочерним путем.</span><span class="sxs-lookup"><span data-stu-id="0907f-129">The `ForEach-Object` statement selects only the Root property of the `PSDriveInfo` objects and combines it with the specified child path.</span></span>

<span data-ttu-id="0907f-130">Выходные данные показывают, что диски PowerShell на компьютере включали диск, сопоставленный с каталогом C:\Program Files.</span><span class="sxs-lookup"><span data-stu-id="0907f-130">The output shows that the PowerShell drives on the computer included a drive mapped to the C:\Program Files directory.</span></span>

## <span data-ttu-id="0907f-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0907f-131">PARAMETERS</span></span>

### <span data-ttu-id="0907f-132">-ChildPath</span><span class="sxs-lookup"><span data-stu-id="0907f-132">-ChildPath</span></span>

<span data-ttu-id="0907f-133">Указывает элементы, добавляемые к значению `Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="0907f-133">Specifies the elements to append to the value of the `Path` parameter.</span></span>
<span data-ttu-id="0907f-134">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0907f-134">Wildcards are permitted.</span></span>
<span data-ttu-id="0907f-135">`ChildPath`Параметр является обязательным, хотя имя параметра ("ChildPath") является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0907f-135">The `ChildPath` parameter is required, although the parameter name ("ChildPath") is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0907f-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="0907f-136">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="0907f-137">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0907f-137">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0907f-138">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="0907f-138">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0907f-139">-Path</span><span class="sxs-lookup"><span data-stu-id="0907f-139">-Path</span></span>

<span data-ttu-id="0907f-140">Указывает основной путь (или пути), к которому добавляется дочерний путь.</span><span class="sxs-lookup"><span data-stu-id="0907f-140">Specifies the main path (or paths) to which the child-path is appended.</span></span>
<span data-ttu-id="0907f-141">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0907f-141">Wildcards are permitted.</span></span>

<span data-ttu-id="0907f-142">Значение `Path` определяет, какой поставщик соединяет пути и добавляет разделители пути.</span><span class="sxs-lookup"><span data-stu-id="0907f-142">The value of `Path` determines which provider joins the paths and adds the path delimiters.</span></span>
<span data-ttu-id="0907f-143">`Path`Параметр является обязательным, хотя имя параметра (Path) является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0907f-143">The `Path` parameter is required, although the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0907f-144">-Разрешить</span><span class="sxs-lookup"><span data-stu-id="0907f-144">-Resolve</span></span>

<span data-ttu-id="0907f-145">Указывает, что этот командлет должен попытаться разрешить присоединенный путь от текущего поставщика.</span><span class="sxs-lookup"><span data-stu-id="0907f-145">Indicates that this cmdlet should attempt to resolve the joined path from the current provider.</span></span>

- <span data-ttu-id="0907f-146">Если используются подстановочные знаки, командлет возвращает все пути, соответствующие пути к соединению.</span><span class="sxs-lookup"><span data-stu-id="0907f-146">If wildcards are used, the cmdlet returns all paths that match the joined path.</span></span>
- <span data-ttu-id="0907f-147">Если **подстановочные знаки не используются** , командлет выдаст ошибку, если путь не существует.</span><span class="sxs-lookup"><span data-stu-id="0907f-147">If **no** wildcards are used, the cmdlet will error if the path does not exist.</span></span>

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

### <span data-ttu-id="0907f-148">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="0907f-148">-UseTransaction</span></span>

<span data-ttu-id="0907f-149">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0907f-149">Includes the command in the active transaction.</span></span>
<span data-ttu-id="0907f-150">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="0907f-150">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="0907f-151">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="0907f-151">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0907f-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0907f-152">CommonParameters</span></span>

<span data-ttu-id="0907f-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0907f-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0907f-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0907f-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0907f-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0907f-155">INPUTS</span></span>

### <span data-ttu-id="0907f-156">System.String</span><span class="sxs-lookup"><span data-stu-id="0907f-156">System.String</span></span>

<span data-ttu-id="0907f-157">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="0907f-157">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="0907f-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0907f-158">OUTPUTS</span></span>

### <span data-ttu-id="0907f-159">System.String</span><span class="sxs-lookup"><span data-stu-id="0907f-159">System.String</span></span>

<span data-ttu-id="0907f-160">Этот командлет возвращает строку, содержащую результирующий путь.</span><span class="sxs-lookup"><span data-stu-id="0907f-160">This cmdlet returns a string that contains the resulting path.</span></span>

## <span data-ttu-id="0907f-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0907f-161">NOTES</span></span>

<span data-ttu-id="0907f-162">Командлеты, содержащие существительное Path (командлеты пути), управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0907f-162">The cmdlets that contain the Path noun (the Path cmdlets) manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="0907f-163">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="0907f-163">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="0907f-164">Такие командлеты дейстуют точно так же, как и другие команды для работы с путями, включая Dirname, Normpath, Realpath, Join и т. д.</span><span class="sxs-lookup"><span data-stu-id="0907f-164">Use them like you would use Dirname, Normpath, Realpath, Join, or other path manipulators.</span></span>

<span data-ttu-id="0907f-165">Командлеты Path можно использовать с несколькими поставщиками, включая `FileSystem` поставщики, `Registry` и `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="0907f-165">You can use the path cmdlets with several providers, including the `FileSystem`, `Registry`, and `Certificate` providers.</span></span>

<span data-ttu-id="0907f-166">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0907f-166">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="0907f-167">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="0907f-167">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="0907f-168">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0907f-168">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0907f-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0907f-169">RELATED LINKS</span></span>

[<span data-ttu-id="0907f-170">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="0907f-170">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="0907f-171">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="0907f-171">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="0907f-172">Split-Path</span><span class="sxs-lookup"><span data-stu-id="0907f-172">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="0907f-173">Test-Path</span><span class="sxs-lookup"><span data-stu-id="0907f-173">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="0907f-174">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="0907f-174">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="0907f-175">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="0907f-175">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="0907f-176">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0907f-176">Get-PSDrive</span></span>](Get-PSDrive.md)
