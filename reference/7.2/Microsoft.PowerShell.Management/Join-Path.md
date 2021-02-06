---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: 08107eecce316c3799315b1d91a0e7cdab64579f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601611"
---
# <span data-ttu-id="ed251-102">Join-Path</span><span class="sxs-lookup"><span data-stu-id="ed251-102">Join-Path</span></span>

## <span data-ttu-id="ed251-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ed251-103">SYNOPSIS</span></span>
<span data-ttu-id="ed251-104">Объединяет путь и его дочерний путь в один путь.</span><span class="sxs-lookup"><span data-stu-id="ed251-104">Combines a path and a child path into a single path.</span></span>

## <span data-ttu-id="ed251-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed251-105">SYNTAX</span></span>

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [[-AdditionalChildPath] <String[]>] [-Resolve]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="ed251-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed251-106">DESCRIPTION</span></span>

<span data-ttu-id="ed251-107">`Join-Path`Командлет объединяет путь и дочерний путь в один путь.</span><span class="sxs-lookup"><span data-stu-id="ed251-107">The `Join-Path` cmdlet combines a path and child-path into a single path.</span></span>
<span data-ttu-id="ed251-108">Поставщик поддерживает разделители пути.</span><span class="sxs-lookup"><span data-stu-id="ed251-108">The provider supplies the path delimiters.</span></span>

## <span data-ttu-id="ed251-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="ed251-109">EXAMPLES</span></span>

### <span data-ttu-id="ed251-110">Пример 1. Объединение пути с дочерним путем</span><span class="sxs-lookup"><span data-stu-id="ed251-110">Example 1: Combine a path with a child path</span></span>

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

<span data-ttu-id="ed251-111">Эта команда использует `Join-Path` для объединения пути с ChildPath.</span><span class="sxs-lookup"><span data-stu-id="ed251-111">This command uses `Join-Path` to combine a path with a childpath.</span></span>

<span data-ttu-id="ed251-112">Так как команда выполняется от `FileSystem` поставщика, она предоставляет `\` Разделитель для объединения путей.</span><span class="sxs-lookup"><span data-stu-id="ed251-112">Since the command is executed from the `FileSystem` provider, it provides the `\` delimiter to join the paths.</span></span>

### <span data-ttu-id="ed251-113">Пример 2. объединение путей, которые уже содержат разделители каталогов</span><span class="sxs-lookup"><span data-stu-id="ed251-113">Example 2: Combine paths that already contain directory separators</span></span>

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

<span data-ttu-id="ed251-114">Существующие разделители каталогов `\` и обработаны, поэтому существует только один разделитель между `Path` и `ChildPath`</span><span class="sxs-lookup"><span data-stu-id="ed251-114">Existing directory separators `\` and handled so there is only one separator between `Path` and `ChildPath`</span></span>

### <span data-ttu-id="ed251-115">Пример 3. Отображение файлов и папок путем присоединения к пути с помощью дочернего пути</span><span class="sxs-lookup"><span data-stu-id="ed251-115">Example 3: Display files and folders by joining a path with a child path</span></span>

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

<span data-ttu-id="ed251-116">Эта команда отображает файлы и папки, на которые имеются ссылки, путем объединения \* пути к:\вин и системного \* дочернего пути.</span><span class="sxs-lookup"><span data-stu-id="ed251-116">This command displays the files and folders that are referenced by joining the C:\Win\* path and the System\* child path.</span></span>
<span data-ttu-id="ed251-117">Он отображает те же файлы и папки, что и `Get-ChildItem` , но отображает полный путь к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="ed251-117">It displays the same files and folders as `Get-ChildItem`, but it displays the fully qualified path to each item.</span></span>
<span data-ttu-id="ed251-118">В этой команде `Path` `ChildPath` имена и необязательные параметры опущены.</span><span class="sxs-lookup"><span data-stu-id="ed251-118">In this command, the `Path` and `ChildPath` optional parameter names are omitted.</span></span>

### <span data-ttu-id="ed251-119">Пример 4. Использование Join-Path с поставщиком реестра PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed251-119">Example 4: Use Join-Path with the PowerShell registry provider</span></span>

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

<span data-ttu-id="ed251-120">Эта команда отображает разделы реестра `HKLM\System` , содержащиеся в подразделе реестра `ControlSet` .</span><span class="sxs-lookup"><span data-stu-id="ed251-120">This command displays the registry keys in the `HKLM\System` registry subkey that include `ControlSet`.</span></span>

<span data-ttu-id="ed251-121">`Resolve`Параметр, пытается разрешить присоединенный путь, включая подстановочные знаки из текущего пути поставщика.`HKLM:\`</span><span class="sxs-lookup"><span data-stu-id="ed251-121">The `Resolve` parameter, attempts to resolve the joined path, including wildcards from the current provider path `HKLM:\`</span></span>

### <span data-ttu-id="ed251-122">Пример 5. Объединение нескольких корней пути с помощью дочернего пути</span><span class="sxs-lookup"><span data-stu-id="ed251-122">Example 5: Combine multiple path roots with a child path</span></span>

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

<span data-ttu-id="ed251-123">Эта команда использует `Join-Path` для объединения нескольких корней пути с дочерним путем.</span><span class="sxs-lookup"><span data-stu-id="ed251-123">This command uses `Join-Path` to combine multiple path roots with a child path.</span></span>

> [!NOTE]
> <span data-ttu-id="ed251-124">Диски, указанные параметром, `Path` должны существовать, иначе соединение этой записи завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ed251-124">The Drives specified by `Path` must exist or the join of that entry will fail.</span></span>

### <span data-ttu-id="ed251-125">Пример 6. объединение корней диска файловой системы с дочерним путем</span><span class="sxs-lookup"><span data-stu-id="ed251-125">Example 6: Combine the roots of a file system drive with a child path</span></span>

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

<span data-ttu-id="ed251-126">Эта команда объединяет корни каждого диска файловой системы PowerShell в консоли с путем к дочернему каталогу SUBDIR.</span><span class="sxs-lookup"><span data-stu-id="ed251-126">This command combines the roots of each PowerShell file system drive in the console with the Subdir child path.</span></span>

<span data-ttu-id="ed251-127">Команда использует `Get-PSDrive` командлет для получения дисков PowerShell, поддерживаемых поставщиком FileSystem.</span><span class="sxs-lookup"><span data-stu-id="ed251-127">The command uses the `Get-PSDrive` cmdlet to get the PowerShell drives supported by the FileSystem provider.</span></span>
<span data-ttu-id="ed251-128">`ForEach-Object`Инструкция выбирает только свойство root `PSDriveInfo` объектов и объединяет его с указанным дочерним путем.</span><span class="sxs-lookup"><span data-stu-id="ed251-128">The `ForEach-Object` statement selects only the Root property of the `PSDriveInfo` objects and combines it with the specified child path.</span></span>

<span data-ttu-id="ed251-129">Выходные данные показывают, что диски PowerShell на компьютере включали диск, сопоставленный с каталогом C:\Program Files.</span><span class="sxs-lookup"><span data-stu-id="ed251-129">The output shows that the PowerShell drives on the computer included a drive mapped to the C:\Program Files directory.</span></span>

### <span data-ttu-id="ed251-130">Пример 7. объединение неопределенного числа путей</span><span class="sxs-lookup"><span data-stu-id="ed251-130">Example 7: Combine an indefinite number of paths</span></span>

```powershell
Join-Path a b c d e f g
```

```Output
a\b\c\d\e\f\g
```

<span data-ttu-id="ed251-131">`AdditionalChildPath`Параметр позволяет присоединить неограниченное количество путей.</span><span class="sxs-lookup"><span data-stu-id="ed251-131">The `AdditionalChildPath` parameter allows the joining of an unlimited number of paths.</span></span>

<span data-ttu-id="ed251-132">В этом примере имена параметров не используются, поэтому "a" привязывается к `Path` , "b" к `ChildPath` и "c-g" в `AdditionalChildPath`</span><span class="sxs-lookup"><span data-stu-id="ed251-132">In this example, no parameter names are used, thus "a" binds to `Path`, "b" to `ChildPath` and "c-g" to `AdditionalChildPath`</span></span>

## <span data-ttu-id="ed251-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed251-133">PARAMETERS</span></span>

### <span data-ttu-id="ed251-134">-Аддитионалчилдпас</span><span class="sxs-lookup"><span data-stu-id="ed251-134">-AdditionalChildPath</span></span>

<span data-ttu-id="ed251-135">Задает дополнительные элементы для добавления к значению параметра *path* .</span><span class="sxs-lookup"><span data-stu-id="ed251-135">Specifies additional elements to append to the value of the *Path* parameter.</span></span> <span data-ttu-id="ed251-136">`ChildPath`Параметр по-прежнему является обязательным и должен быть указан также.</span><span class="sxs-lookup"><span data-stu-id="ed251-136">The `ChildPath` parameter is still mandatory and must be specified as well.</span></span>

<span data-ttu-id="ed251-137">Этот параметр указывается со `ValueFromRemainingArguments` свойством, которое позволяет присоединить неопределенное число путей.</span><span class="sxs-lookup"><span data-stu-id="ed251-137">This parameter is specified with the `ValueFromRemainingArguments` property which enables joining an indefinite number of paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ed251-138">-ChildPath</span><span class="sxs-lookup"><span data-stu-id="ed251-138">-ChildPath</span></span>

<span data-ttu-id="ed251-139">Указывает элементы, добавляемые к значению `Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="ed251-139">Specifies the elements to append to the value of the `Path` parameter.</span></span>
<span data-ttu-id="ed251-140">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ed251-140">Wildcards are permitted.</span></span>
<span data-ttu-id="ed251-141">`ChildPath`Параметр является обязательным, хотя имя параметра ("ChildPath") является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ed251-141">The `ChildPath` parameter is required, although the parameter name ("ChildPath") is optional.</span></span>

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

### <span data-ttu-id="ed251-142">-Credential</span><span class="sxs-lookup"><span data-stu-id="ed251-142">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ed251-143">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed251-143">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="ed251-144">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="ed251-144">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="ed251-145">-Path</span><span class="sxs-lookup"><span data-stu-id="ed251-145">-Path</span></span>

<span data-ttu-id="ed251-146">Указывает основной путь (или пути), к которому добавляется дочерний путь.</span><span class="sxs-lookup"><span data-stu-id="ed251-146">Specifies the main path (or paths) to which the child-path is appended.</span></span>
<span data-ttu-id="ed251-147">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ed251-147">Wildcards are permitted.</span></span>

<span data-ttu-id="ed251-148">Значение `Path` определяет, какой поставщик соединяет пути и добавляет разделители пути.</span><span class="sxs-lookup"><span data-stu-id="ed251-148">The value of `Path` determines which provider joins the paths and adds the path delimiters.</span></span>
<span data-ttu-id="ed251-149">`Path`Параметр является обязательным, хотя имя параметра (Path) является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ed251-149">The `Path` parameter is required, although the parameter name ("Path") is optional.</span></span>

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

### <span data-ttu-id="ed251-150">-Разрешить</span><span class="sxs-lookup"><span data-stu-id="ed251-150">-Resolve</span></span>

<span data-ttu-id="ed251-151">Указывает, что этот командлет должен попытаться разрешить присоединенный путь от текущего поставщика.</span><span class="sxs-lookup"><span data-stu-id="ed251-151">Indicates that this cmdlet should attempt to resolve the joined path from the current provider.</span></span>

- <span data-ttu-id="ed251-152">Если используются подстановочные знаки, командлет возвращает все пути, соответствующие пути к соединению.</span><span class="sxs-lookup"><span data-stu-id="ed251-152">If wildcards are used, the cmdlet returns all paths that match the joined path.</span></span>
- <span data-ttu-id="ed251-153">Если **подстановочные знаки не используются** , командлет выдаст ошибку, если путь не существует.</span><span class="sxs-lookup"><span data-stu-id="ed251-153">If **no** wildcards are used, the cmdlet will error if the path does not exist.</span></span>

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

### <span data-ttu-id="ed251-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ed251-154">CommonParameters</span></span>

<span data-ttu-id="ed251-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed251-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed251-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed251-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed251-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ed251-157">INPUTS</span></span>

### <span data-ttu-id="ed251-158">System.String</span><span class="sxs-lookup"><span data-stu-id="ed251-158">System.String</span></span>

<span data-ttu-id="ed251-159">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="ed251-159">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="ed251-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ed251-160">OUTPUTS</span></span>

### <span data-ttu-id="ed251-161">System.String</span><span class="sxs-lookup"><span data-stu-id="ed251-161">System.String</span></span>

<span data-ttu-id="ed251-162">Этот командлет возвращает строку, содержащую результирующий путь.</span><span class="sxs-lookup"><span data-stu-id="ed251-162">This cmdlet returns a string that contains the resulting path.</span></span>

## <span data-ttu-id="ed251-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ed251-163">NOTES</span></span>

<span data-ttu-id="ed251-164">Командлеты, содержащие существительное Path (командлеты пути), управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed251-164">The cmdlets that contain the Path noun (the Path cmdlets) manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="ed251-165">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="ed251-165">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="ed251-166">Такие командлеты дейстуют точно так же, как и другие команды для работы с путями, включая Dirname, Normpath, Realpath, Join и т. д.</span><span class="sxs-lookup"><span data-stu-id="ed251-166">Use them like you would use Dirname, Normpath, Realpath, Join, or other path manipulators.</span></span>

<span data-ttu-id="ed251-167">Командлеты Path можно использовать с несколькими поставщиками, включая `FileSystem` поставщики, `Registry` и `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="ed251-167">You can use the path cmdlets with several providers, including the `FileSystem`, `Registry`, and `Certificate` providers.</span></span>

<span data-ttu-id="ed251-168">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="ed251-168">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="ed251-169">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="ed251-169">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="ed251-170">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ed251-170">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ed251-171">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ed251-171">RELATED LINKS</span></span>

[<span data-ttu-id="ed251-172">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="ed251-172">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="ed251-173">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="ed251-173">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="ed251-174">Split-Path</span><span class="sxs-lookup"><span data-stu-id="ed251-174">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="ed251-175">Test-Path</span><span class="sxs-lookup"><span data-stu-id="ed251-175">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="ed251-176">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="ed251-176">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="ed251-177">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="ed251-177">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="ed251-178">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="ed251-178">Get-PSDrive</span></span>](Get-PSDrive.md)

