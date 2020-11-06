---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: c0ee5552e33792f208faba63dc05ddb93473bc49
ms.sourcegitcommit: 9a53e53e7a3ef9ac0a212c61005efff9e9902452
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "93230473"
---
# <span data-ttu-id="74012-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="74012-103">Split-Path</span></span>

## <span data-ttu-id="74012-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="74012-104">SYNOPSIS</span></span>
<span data-ttu-id="74012-105">Возвращает указанную часть пути.</span><span class="sxs-lookup"><span data-stu-id="74012-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="74012-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74012-106">SYNTAX</span></span>

### <span data-ttu-id="74012-107">Родительский элемент (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="74012-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="74012-108">Конечный элемент</span><span class="sxs-lookup"><span data-stu-id="74012-108">LeafSet</span></span>

```
Split-Path [-Path] <String[]> -Leaf [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="74012-109">леафбасесет</span><span class="sxs-lookup"><span data-stu-id="74012-109">LeafBaseSet</span></span>

```
Split-Path [-Path] <String[]> -LeafBase [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="74012-110">Расширение</span><span class="sxs-lookup"><span data-stu-id="74012-110">ExtensionSet</span></span>

```
Split-Path [-Path] <String[]> -Extension [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="74012-111">куалифиерсет</span><span class="sxs-lookup"><span data-stu-id="74012-111">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> -Qualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="74012-112">нокуалифиерсет</span><span class="sxs-lookup"><span data-stu-id="74012-112">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> -NoQualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="74012-113">Absolute</span><span class="sxs-lookup"><span data-stu-id="74012-113">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] -IsAbsolute [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="74012-114">литералпассет</span><span class="sxs-lookup"><span data-stu-id="74012-114">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="74012-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="74012-115">DESCRIPTION</span></span>

<span data-ttu-id="74012-116">`Split-Path`Командлет возвращает только указанную часть пути, например родительскую папку, подпапку или имя файла.</span><span class="sxs-lookup"><span data-stu-id="74012-116">The `Split-Path` cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span> <span data-ttu-id="74012-117">Он также может получать элементы, на которые ссылается Split Path, и определять, является ли путь относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="74012-117">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="74012-118">Этот командлет можно использовать для получения или отправки только выбранной части пути.</span><span class="sxs-lookup"><span data-stu-id="74012-118">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="74012-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="74012-119">EXAMPLES</span></span>

### <span data-ttu-id="74012-120">Пример 1. получение квалификатора пути</span><span class="sxs-lookup"><span data-stu-id="74012-120">Example 1: Get the qualifier of a path</span></span>

```powershell
Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
```

```Output
HKCU:
```

<span data-ttu-id="74012-121">Эта команда возвращает только квалификатор пути.</span><span class="sxs-lookup"><span data-stu-id="74012-121">This command returns only the qualifier of the path.</span></span> <span data-ttu-id="74012-122">Квалификатор — это диск.</span><span class="sxs-lookup"><span data-stu-id="74012-122">The qualifier is the drive.</span></span>

### <span data-ttu-id="74012-123">Пример 2. Отображение имен файлов</span><span class="sxs-lookup"><span data-stu-id="74012-123">Example 2: Display file names</span></span>

```powershell
Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
```

```Output
Pass1.log
Pass2.log
...
```

<span data-ttu-id="74012-124">Эта команда отображает файлы, на которые ссылается разделенный путь.</span><span class="sxs-lookup"><span data-stu-id="74012-124">This command displays the files that are referenced by the split path.</span></span> <span data-ttu-id="74012-125">Поскольку этот путь разбивается на последний элемент, также известный как лист, команда отображает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="74012-125">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="74012-126">Параметр **Resolve** сообщает, `Split-Path` что необходимо отобразить элементы, на которые ссылается путь разбиения, вместо отображения пути разбиения.</span><span class="sxs-lookup"><span data-stu-id="74012-126">The **Resolve** parameter tells `Split-Path` to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="74012-127">Как и все `Split-Path` команды, эта команда возвращает строки.</span><span class="sxs-lookup"><span data-stu-id="74012-127">Like all `Split-Path` commands, this command returns strings.</span></span> <span data-ttu-id="74012-128">Он не возвращает объекты **FileInfo** , представляющие файлы.</span><span class="sxs-lookup"><span data-stu-id="74012-128">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="74012-129">Пример 3. получение родительского контейнера</span><span class="sxs-lookup"><span data-stu-id="74012-129">Example 3: Get the parent container</span></span>

```powershell
Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
```

```Output
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="74012-130">Эта команда возвращает только родительские контейнеры пути.</span><span class="sxs-lookup"><span data-stu-id="74012-130">This command returns only the parent containers of the path.</span></span> <span data-ttu-id="74012-131">Так как он не включает параметры для указания разбиения, `Split-Path` использует расположение разбиения по умолчанию, которое является **родительским** .</span><span class="sxs-lookup"><span data-stu-id="74012-131">Because it does not include any parameters to specify the split, `Split-Path` uses the split location default, which is **Parent** .</span></span>

### <span data-ttu-id="74012-132">Пример 4. определяет, является ли путь абсолютным</span><span class="sxs-lookup"><span data-stu-id="74012-132">Example 4: Determines whether a path is absolute</span></span>

```powershell
Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
```

```Output
False
```

<span data-ttu-id="74012-133">Эта команда определяет, является ли путь относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="74012-133">This command determines whether the path is relative or absolute.</span></span> <span data-ttu-id="74012-134">В этом случае, поскольку путь задается относительно текущей папки, которая представляется точкой ( `.` ), она возвращает `$False` .</span><span class="sxs-lookup"><span data-stu-id="74012-134">In this case, because the path is relative to the current folder, which is represented by a dot (`.`), it returns `$False`.</span></span>

### <span data-ttu-id="74012-135">Пример 5. изменение расположения по указанному пути</span><span class="sxs-lookup"><span data-stu-id="74012-135">Example 5: Change location to a specified path</span></span>

```powershell
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="74012-136">Эта команда изменяет расположение на папку, содержащую профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74012-136">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="74012-137">Команда в круглых скобках использует `Split-Path` для возвращения только родителя пути, хранящегося во встроенной `$Profile` переменной.</span><span class="sxs-lookup"><span data-stu-id="74012-137">The command in parentheses uses `Split-Path` to return only the parent of the path stored in the built-in `$Profile` variable.</span></span> <span data-ttu-id="74012-138">**Родительский** параметр — это параметр расположения разбиения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="74012-138">The **Parent** parameter is the default split location parameter.</span></span>
<span data-ttu-id="74012-139">Поэтому его можно опустить из команды.</span><span class="sxs-lookup"><span data-stu-id="74012-139">Therefore, you can omit it from the command.</span></span> <span data-ttu-id="74012-140">Круглые скобки указывают PowerShell для выполнения команды в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="74012-140">The parentheses direct PowerShell to run the command first.</span></span> <span data-ttu-id="74012-141">Это удобный способ перехода в папку, имеющую длинное имя пути.</span><span class="sxs-lookup"><span data-stu-id="74012-141">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="74012-142">Пример 6. разбиение пути с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="74012-142">Example 6: Split a path by using the pipeline</span></span>

```powershell
'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
```

```Output
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="74012-143">Эта команда использует конвейерный оператор ( `|` ) для отправки пути `Split-Path` .</span><span class="sxs-lookup"><span data-stu-id="74012-143">This command uses a pipeline operator (`|`) to send a path to `Split-Path`.</span></span> <span data-ttu-id="74012-144">Заключенный в кавычки путь означает, что это единичный маркер.</span><span class="sxs-lookup"><span data-stu-id="74012-144">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="74012-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74012-145">PARAMETERS</span></span>

### <span data-ttu-id="74012-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="74012-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="74012-147">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74012-147">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="74012-148">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="74012-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="74012-149">-Extension</span><span class="sxs-lookup"><span data-stu-id="74012-149">-Extension</span></span>

<span data-ttu-id="74012-150">Указывает, что этот командлет возвращает только расширение конечного объекта.</span><span class="sxs-lookup"><span data-stu-id="74012-150">Indicates that this cmdlet returns only the extension of the leaf.</span></span> <span data-ttu-id="74012-151">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `.log` .</span><span class="sxs-lookup"><span data-stu-id="74012-151">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.</span></span>

<span data-ttu-id="74012-152">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="74012-152">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-153">-Absolute</span><span class="sxs-lookup"><span data-stu-id="74012-153">-IsAbsolute</span></span>

<span data-ttu-id="74012-154">Указывает, что этот командлет возвращает $True, если путь является абсолютным, и $False, если он является относительным.</span><span class="sxs-lookup"><span data-stu-id="74012-154">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span> <span data-ttu-id="74012-155">Абсолютный путь имеет длину больше нуля и не использует точку ( `.` ) для указания текущего пути.</span><span class="sxs-lookup"><span data-stu-id="74012-155">An absolute path has a length greater than zero and does not use a dot (`.`) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="74012-156">-Конечный элемент</span><span class="sxs-lookup"><span data-stu-id="74012-156">-Leaf</span></span>

<span data-ttu-id="74012-157">Указывает, что этот командлет возвращает только последний элемент или контейнер в пути.</span><span class="sxs-lookup"><span data-stu-id="74012-157">Indicates that this cmdlet returns only the last item or container in the path.</span></span> <span data-ttu-id="74012-158">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только Pass1. log.</span><span class="sxs-lookup"><span data-stu-id="74012-158">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-159">-Леафбасе</span><span class="sxs-lookup"><span data-stu-id="74012-159">-LeafBase</span></span>

<span data-ttu-id="74012-160">Указывает, что этот командлет возвращает только базовое имя конечного объекта.</span><span class="sxs-lookup"><span data-stu-id="74012-160">Indicates that this cmdlet returns only base name of the leaf.</span></span> <span data-ttu-id="74012-161">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `Pass1` .</span><span class="sxs-lookup"><span data-stu-id="74012-161">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.</span></span>

<span data-ttu-id="74012-162">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="74012-162">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-163">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="74012-163">-LiteralPath</span></span>

<span data-ttu-id="74012-164">Указывает путь для разделения.</span><span class="sxs-lookup"><span data-stu-id="74012-164">Specifies the paths to be split.</span></span> <span data-ttu-id="74012-165">В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="74012-165">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="74012-166">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="74012-166">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="74012-167">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="74012-167">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="74012-168">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="74012-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-169">-Квалификатор</span><span class="sxs-lookup"><span data-stu-id="74012-169">-NoQualifier</span></span>

<span data-ttu-id="74012-170">Указывает, что этот командлет возвращает путь без квалификатора.</span><span class="sxs-lookup"><span data-stu-id="74012-170">Indicates that this cmdlet returns the path without the qualifier.</span></span> <span data-ttu-id="74012-171">Квалификатором для файловой системы или поставщиков реестра является диск пути поставщика, например `C:` или `HKCU:` .</span><span class="sxs-lookup"><span data-stu-id="74012-171">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span> <span data-ttu-id="74012-172">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `\Test\Logs\Pass1.log` .</span><span class="sxs-lookup"><span data-stu-id="74012-172">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `\Test\Logs\Pass1.log`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-173">— Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="74012-173">-Parent</span></span>

<span data-ttu-id="74012-174">Указывает, что этот командлет возвращает только родительские контейнеры элемента или контейнера, заданного путем.</span><span class="sxs-lookup"><span data-stu-id="74012-174">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span> <span data-ttu-id="74012-175">Например, в пути `C:\Test\Logs\Pass1.log` возвращается `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="74012-175">For example, in the path `C:\Test\Logs\Pass1.log`, it returns `C:\Test\Logs`.</span></span>
<span data-ttu-id="74012-176">**Родительский** параметр — это параметр расположения разбиения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="74012-176">The **Parent** parameter is the default split location parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-177">-Path</span><span class="sxs-lookup"><span data-stu-id="74012-177">-Path</span></span>

<span data-ttu-id="74012-178">Указывает путь для разделения.</span><span class="sxs-lookup"><span data-stu-id="74012-178">Specifies the paths to be split.</span></span> <span data-ttu-id="74012-179">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="74012-179">Wildcard characters are permitted.</span></span> <span data-ttu-id="74012-180">Если путь содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="74012-180">If the path includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="74012-181">Можно также передать по конвейеру путь к этому командлету.</span><span class="sxs-lookup"><span data-stu-id="74012-181">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="74012-182">-Квалификатор</span><span class="sxs-lookup"><span data-stu-id="74012-182">-Qualifier</span></span>

<span data-ttu-id="74012-183">Указывает, что этот командлет возвращает только квалификатор указанного пути.</span><span class="sxs-lookup"><span data-stu-id="74012-183">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span> <span data-ttu-id="74012-184">Квалификатором для файловой системы или поставщиков реестра является диск пути поставщика, например `C:` или `HKCU:` .</span><span class="sxs-lookup"><span data-stu-id="74012-184">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74012-185">-Разрешить</span><span class="sxs-lookup"><span data-stu-id="74012-185">-Resolve</span></span>

<span data-ttu-id="74012-186">Указывает, что этот командлет отображает элементы, на которые ссылается результирующий разделяемый путь, вместо отображения элементов пути.</span><span class="sxs-lookup"><span data-stu-id="74012-186">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="74012-187">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="74012-187">CommonParameters</span></span>

<span data-ttu-id="74012-188">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="74012-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74012-189">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="74012-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74012-190">Входные данные</span><span class="sxs-lookup"><span data-stu-id="74012-190">INPUTS</span></span>

### <span data-ttu-id="74012-191">System.String</span><span class="sxs-lookup"><span data-stu-id="74012-191">System.String</span></span>

<span data-ttu-id="74012-192">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="74012-192">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="74012-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="74012-193">OUTPUTS</span></span>

### <span data-ttu-id="74012-194">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="74012-194">System.String, System.Boolean</span></span>

<span data-ttu-id="74012-195">`Split-Path` Возвращает текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="74012-195">`Split-Path` returns text strings.</span></span> <span data-ttu-id="74012-196">При указании параметра **Resolve** `Split-Path` возвращает строку, описывающую расположение элементов. она не возвращает объекты, представляющие такие элементы, как **FileInfo** или **RegistryKey** .</span><span class="sxs-lookup"><span data-stu-id="74012-196">When you specify the **Resolve** parameter, `Split-Path` returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="74012-197">При указании параметра **Absolute** `Split-Path` возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="74012-197">When you specify the **IsAbsolute** parameter, `Split-Path` returns a **Boolean** value.</span></span>

## <span data-ttu-id="74012-198">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="74012-198">NOTES</span></span>

- <span data-ttu-id="74012-199">Параметры раздельного расположения ( **квалификатор** , **родительский элемент** , **расширение** , **конечный** объект, **леафбасе** и **квалификатор** ) являются эксклюзивными.</span><span class="sxs-lookup"><span data-stu-id="74012-199">The split location parameters ( **Qualifier** , **Parent** , **Extension** , **Leaf** , **LeafBase** , and **NoQualifier** ) are exclusive.</span></span> <span data-ttu-id="74012-200">Можно использовать только один из них в каждой команде.</span><span class="sxs-lookup"><span data-stu-id="74012-200">You can use only one in each command.</span></span>

- <span data-ttu-id="74012-201">Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74012-201">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="74012-202">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="74012-202">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="74012-203">Используйте их в том виде, в котором будут использоваться **dirname** , **нормпас** , **реалпас** , **Join** или другие манипуляторы пути.</span><span class="sxs-lookup"><span data-stu-id="74012-203">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

- <span data-ttu-id="74012-204">Командлеты **path** можно использовать вместе с несколькими поставщиками.</span><span class="sxs-lookup"><span data-stu-id="74012-204">You can use the **Path** cmdlets together with several providers.</span></span> <span data-ttu-id="74012-205">К ним относятся файловая система, реестр и поставщики сертификатов.</span><span class="sxs-lookup"><span data-stu-id="74012-205">These include the FileSystem, Registry, and Certificate providers.</span></span>

- <span data-ttu-id="74012-206">`Split-Path` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="74012-206">`Split-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="74012-207">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="74012-207">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="74012-208">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="74012-208">For more information, see about_Providers.</span></span>

## <span data-ttu-id="74012-209">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="74012-209">RELATED LINKS</span></span>

[<span data-ttu-id="74012-210">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="74012-210">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="74012-211">Join-Path</span><span class="sxs-lookup"><span data-stu-id="74012-211">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="74012-212">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="74012-212">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="74012-213">Test-Path</span><span class="sxs-lookup"><span data-stu-id="74012-213">Test-Path</span></span>](Test-Path.md)