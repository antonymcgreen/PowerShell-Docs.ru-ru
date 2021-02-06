---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: e2498c02d42123e207b49e622654d3cb881fc0fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604166"
---
# <span data-ttu-id="93f9a-102">Split-Path</span><span class="sxs-lookup"><span data-stu-id="93f9a-102">Split-Path</span></span>

## <span data-ttu-id="93f9a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="93f9a-103">SYNOPSIS</span></span>
<span data-ttu-id="93f9a-104">Возвращает указанную часть пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-104">Returns the specified part of a path.</span></span>

## <span data-ttu-id="93f9a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93f9a-105">SYNTAX</span></span>

### <span data-ttu-id="93f9a-106">Родительский элемент (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="93f9a-106">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="93f9a-107">Конечный элемент</span><span class="sxs-lookup"><span data-stu-id="93f9a-107">LeafSet</span></span>

```
Split-Path [-Path] <String[]> -Leaf [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="93f9a-108">леафбасесет</span><span class="sxs-lookup"><span data-stu-id="93f9a-108">LeafBaseSet</span></span>

```
Split-Path [-Path] <String[]> -LeafBase [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="93f9a-109">Расширение</span><span class="sxs-lookup"><span data-stu-id="93f9a-109">ExtensionSet</span></span>

```
Split-Path [-Path] <String[]> -Extension [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="93f9a-110">куалифиерсет</span><span class="sxs-lookup"><span data-stu-id="93f9a-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> -Qualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="93f9a-111">нокуалифиерсет</span><span class="sxs-lookup"><span data-stu-id="93f9a-111">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> -NoQualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="93f9a-112">Absolute</span><span class="sxs-lookup"><span data-stu-id="93f9a-112">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] -IsAbsolute [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="93f9a-113">литералпассет</span><span class="sxs-lookup"><span data-stu-id="93f9a-113">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="93f9a-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="93f9a-114">DESCRIPTION</span></span>

<span data-ttu-id="93f9a-115">`Split-Path`Командлет возвращает только указанную часть пути, например родительскую папку, подпапку или имя файла.</span><span class="sxs-lookup"><span data-stu-id="93f9a-115">The `Split-Path` cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span> <span data-ttu-id="93f9a-116">Он также может получать элементы, на которые ссылается Split Path, и определять, является ли путь относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="93f9a-116">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="93f9a-117">Этот командлет можно использовать для получения или отправки только выбранной части пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-117">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="93f9a-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="93f9a-118">EXAMPLES</span></span>

### <span data-ttu-id="93f9a-119">Пример 1. получение квалификатора пути</span><span class="sxs-lookup"><span data-stu-id="93f9a-119">Example 1: Get the qualifier of a path</span></span>

```powershell
Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
```

```Output
HKCU:
```

<span data-ttu-id="93f9a-120">Эта команда возвращает только квалификатор пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-120">This command returns only the qualifier of the path.</span></span> <span data-ttu-id="93f9a-121">Квалификатор — это диск.</span><span class="sxs-lookup"><span data-stu-id="93f9a-121">The qualifier is the drive.</span></span>

### <span data-ttu-id="93f9a-122">Пример 2. Отображение имен файлов</span><span class="sxs-lookup"><span data-stu-id="93f9a-122">Example 2: Display file names</span></span>

```powershell
Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
```

```Output
Pass1.log
Pass2.log
...
```

<span data-ttu-id="93f9a-123">Эта команда отображает файлы, на которые ссылается разделенный путь.</span><span class="sxs-lookup"><span data-stu-id="93f9a-123">This command displays the files that are referenced by the split path.</span></span> <span data-ttu-id="93f9a-124">Поскольку этот путь разбивается на последний элемент, также известный как лист, команда отображает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="93f9a-124">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="93f9a-125">Параметр **Resolve** сообщает, `Split-Path` что необходимо отобразить элементы, на которые ссылается путь разбиения, вместо отображения пути разбиения.</span><span class="sxs-lookup"><span data-stu-id="93f9a-125">The **Resolve** parameter tells `Split-Path` to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="93f9a-126">Как и все `Split-Path` команды, эта команда возвращает строки.</span><span class="sxs-lookup"><span data-stu-id="93f9a-126">Like all `Split-Path` commands, this command returns strings.</span></span> <span data-ttu-id="93f9a-127">Он не возвращает объекты **FileInfo** , представляющие файлы.</span><span class="sxs-lookup"><span data-stu-id="93f9a-127">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="93f9a-128">Пример 3. получение родительского контейнера</span><span class="sxs-lookup"><span data-stu-id="93f9a-128">Example 3: Get the parent container</span></span>

```powershell
Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
```

```Output
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="93f9a-129">Эта команда возвращает только родительские контейнеры пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-129">This command returns only the parent containers of the path.</span></span> <span data-ttu-id="93f9a-130">Так как он не включает параметры для указания разбиения, `Split-Path` использует расположение разбиения по умолчанию, которое является **родительским**.</span><span class="sxs-lookup"><span data-stu-id="93f9a-130">Because it does not include any parameters to specify the split, `Split-Path` uses the split location default, which is **Parent**.</span></span>

### <span data-ttu-id="93f9a-131">Пример 4. определяет, является ли путь абсолютным</span><span class="sxs-lookup"><span data-stu-id="93f9a-131">Example 4: Determines whether a path is absolute</span></span>

```powershell
Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
```

```Output
False
```

<span data-ttu-id="93f9a-132">Эта команда определяет, является ли путь относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="93f9a-132">This command determines whether the path is relative or absolute.</span></span> <span data-ttu-id="93f9a-133">В этом случае, поскольку путь задается относительно текущей папки, которая представляется точкой ( `.` ), она возвращает `$False` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-133">In this case, because the path is relative to the current folder, which is represented by a dot (`.`), it returns `$False`.</span></span>

### <span data-ttu-id="93f9a-134">Пример 5. изменение расположения по указанному пути</span><span class="sxs-lookup"><span data-stu-id="93f9a-134">Example 5: Change location to a specified path</span></span>

```powershell
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="93f9a-135">Эта команда изменяет расположение на папку, содержащую профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93f9a-135">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="93f9a-136">Команда в круглых скобках использует `Split-Path` для возвращения только родителя пути, хранящегося во встроенной `$Profile` переменной.</span><span class="sxs-lookup"><span data-stu-id="93f9a-136">The command in parentheses uses `Split-Path` to return only the parent of the path stored in the built-in `$Profile` variable.</span></span> <span data-ttu-id="93f9a-137">**Родительский** параметр — это параметр расположения разбиения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93f9a-137">The **Parent** parameter is the default split location parameter.</span></span>
<span data-ttu-id="93f9a-138">Поэтому его можно опустить из команды.</span><span class="sxs-lookup"><span data-stu-id="93f9a-138">Therefore, you can omit it from the command.</span></span> <span data-ttu-id="93f9a-139">Круглые скобки указывают PowerShell для выполнения команды в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="93f9a-139">The parentheses direct PowerShell to run the command first.</span></span> <span data-ttu-id="93f9a-140">Это удобный способ перехода в папку, имеющую длинное имя пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-140">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="93f9a-141">Пример 6. разбиение пути с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="93f9a-141">Example 6: Split a path by using the pipeline</span></span>

```powershell
'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
```

```Output
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="93f9a-142">Эта команда использует конвейерный оператор ( `|` ) для отправки пути `Split-Path` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-142">This command uses a pipeline operator (`|`) to send a path to `Split-Path`.</span></span> <span data-ttu-id="93f9a-143">Заключенный в кавычки путь означает, что это единичный маркер.</span><span class="sxs-lookup"><span data-stu-id="93f9a-143">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="93f9a-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93f9a-144">PARAMETERS</span></span>

### <span data-ttu-id="93f9a-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="93f9a-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="93f9a-146">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93f9a-146">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="93f9a-147">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="93f9a-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="93f9a-148">-Extension</span><span class="sxs-lookup"><span data-stu-id="93f9a-148">-Extension</span></span>

<span data-ttu-id="93f9a-149">Указывает, что этот командлет возвращает только расширение конечного объекта.</span><span class="sxs-lookup"><span data-stu-id="93f9a-149">Indicates that this cmdlet returns only the extension of the leaf.</span></span> <span data-ttu-id="93f9a-150">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `.log` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-150">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.</span></span>

<span data-ttu-id="93f9a-151">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="93f9a-151">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="93f9a-152">-Absolute</span><span class="sxs-lookup"><span data-stu-id="93f9a-152">-IsAbsolute</span></span>

<span data-ttu-id="93f9a-153">Указывает, что этот командлет возвращает $True, если путь является абсолютным, и $False, если он является относительным.</span><span class="sxs-lookup"><span data-stu-id="93f9a-153">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span> <span data-ttu-id="93f9a-154">Абсолютный путь имеет длину больше нуля и не использует точку ( `.` ) для указания текущего пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-154">An absolute path has a length greater than zero and does not use a dot (`.`) to indicate the current path.</span></span>

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

### <span data-ttu-id="93f9a-155">-Конечный элемент</span><span class="sxs-lookup"><span data-stu-id="93f9a-155">-Leaf</span></span>

<span data-ttu-id="93f9a-156">Указывает, что этот командлет возвращает только последний элемент или контейнер в пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-156">Indicates that this cmdlet returns only the last item or container in the path.</span></span> <span data-ttu-id="93f9a-157">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только Pass1. log.</span><span class="sxs-lookup"><span data-stu-id="93f9a-157">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

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

### <span data-ttu-id="93f9a-158">-Леафбасе</span><span class="sxs-lookup"><span data-stu-id="93f9a-158">-LeafBase</span></span>

<span data-ttu-id="93f9a-159">Указывает, что этот командлет возвращает только базовое имя конечного объекта.</span><span class="sxs-lookup"><span data-stu-id="93f9a-159">Indicates that this cmdlet returns only base name of the leaf.</span></span> <span data-ttu-id="93f9a-160">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `Pass1` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-160">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.</span></span>

<span data-ttu-id="93f9a-161">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="93f9a-161">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="93f9a-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="93f9a-162">-LiteralPath</span></span>

<span data-ttu-id="93f9a-163">Указывает путь для разделения.</span><span class="sxs-lookup"><span data-stu-id="93f9a-163">Specifies the paths to be split.</span></span> <span data-ttu-id="93f9a-164">В отличие от параметра **Path**, значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="93f9a-164">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="93f9a-165">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="93f9a-165">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="93f9a-166">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="93f9a-166">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="93f9a-167">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="93f9a-167">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="93f9a-168">-Квалификатор</span><span class="sxs-lookup"><span data-stu-id="93f9a-168">-NoQualifier</span></span>

<span data-ttu-id="93f9a-169">Указывает, что этот командлет возвращает путь без квалификатора.</span><span class="sxs-lookup"><span data-stu-id="93f9a-169">Indicates that this cmdlet returns the path without the qualifier.</span></span> <span data-ttu-id="93f9a-170">Квалификатором для файловой системы или поставщиков реестра является диск пути поставщика, например `C:` или `HKCU:` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-170">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span> <span data-ttu-id="93f9a-171">Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `\Test\Logs\Pass1.log` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-171">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `\Test\Logs\Pass1.log`.</span></span>

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

### <span data-ttu-id="93f9a-172">— Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="93f9a-172">-Parent</span></span>

<span data-ttu-id="93f9a-173">Указывает, что этот командлет возвращает только родительские контейнеры элемента или контейнера, заданного путем.</span><span class="sxs-lookup"><span data-stu-id="93f9a-173">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span> <span data-ttu-id="93f9a-174">Например, в пути `C:\Test\Logs\Pass1.log` возвращается `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-174">For example, in the path `C:\Test\Logs\Pass1.log`, it returns `C:\Test\Logs`.</span></span>
<span data-ttu-id="93f9a-175">**Родительский** параметр — это параметр расположения разбиения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93f9a-175">The **Parent** parameter is the default split location parameter.</span></span>

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

### <span data-ttu-id="93f9a-176">-Path</span><span class="sxs-lookup"><span data-stu-id="93f9a-176">-Path</span></span>

<span data-ttu-id="93f9a-177">Указывает путь для разделения.</span><span class="sxs-lookup"><span data-stu-id="93f9a-177">Specifies the paths to be split.</span></span> <span data-ttu-id="93f9a-178">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="93f9a-178">Wildcard characters are permitted.</span></span> <span data-ttu-id="93f9a-179">Если путь содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="93f9a-179">If the path includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="93f9a-180">Можно также передать по конвейеру путь к этому командлету.</span><span class="sxs-lookup"><span data-stu-id="93f9a-180">You can also pipe a path to this cmdlet.</span></span>

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

### <span data-ttu-id="93f9a-181">-Квалификатор</span><span class="sxs-lookup"><span data-stu-id="93f9a-181">-Qualifier</span></span>

<span data-ttu-id="93f9a-182">Указывает, что этот командлет возвращает только квалификатор указанного пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-182">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span> <span data-ttu-id="93f9a-183">Квалификатором для файловой системы или поставщиков реестра является диск пути поставщика, например `C:` или `HKCU:` .</span><span class="sxs-lookup"><span data-stu-id="93f9a-183">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span>

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

### <span data-ttu-id="93f9a-184">-Разрешить</span><span class="sxs-lookup"><span data-stu-id="93f9a-184">-Resolve</span></span>

<span data-ttu-id="93f9a-185">Указывает, что этот командлет отображает элементы, на которые ссылается результирующий разделяемый путь, вместо отображения элементов пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-185">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="93f9a-186">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="93f9a-186">CommonParameters</span></span>

<span data-ttu-id="93f9a-187">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="93f9a-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93f9a-188">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="93f9a-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="93f9a-189">Входные данные</span><span class="sxs-lookup"><span data-stu-id="93f9a-189">INPUTS</span></span>

### <span data-ttu-id="93f9a-190">System.String</span><span class="sxs-lookup"><span data-stu-id="93f9a-190">System.String</span></span>

<span data-ttu-id="93f9a-191">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="93f9a-191">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="93f9a-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="93f9a-192">OUTPUTS</span></span>

### <span data-ttu-id="93f9a-193">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="93f9a-193">System.String, System.Boolean</span></span>

<span data-ttu-id="93f9a-194">`Split-Path` Возвращает текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="93f9a-194">`Split-Path` returns text strings.</span></span> <span data-ttu-id="93f9a-195">При указании параметра **Resolve** `Split-Path` возвращает строку, описывающую расположение элементов. она не возвращает объекты, представляющие такие элементы, как **FileInfo** или **RegistryKey** .</span><span class="sxs-lookup"><span data-stu-id="93f9a-195">When you specify the **Resolve** parameter, `Split-Path` returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="93f9a-196">При указании параметра **Absolute** `Split-Path` возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="93f9a-196">When you specify the **IsAbsolute** parameter, `Split-Path` returns a **Boolean** value.</span></span>

## <span data-ttu-id="93f9a-197">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="93f9a-197">NOTES</span></span>

- <span data-ttu-id="93f9a-198">Параметры раздельного расположения (**квалификатор**, **родительский элемент**, **расширение**, **конечный** объект, **леафбасе** и **квалификатор**) являются эксклюзивными.</span><span class="sxs-lookup"><span data-stu-id="93f9a-198">The split location parameters (**Qualifier**, **Parent**, **Extension**, **Leaf**, **LeafBase**, and **NoQualifier**) are exclusive.</span></span> <span data-ttu-id="93f9a-199">Можно использовать только один из них в каждой команде.</span><span class="sxs-lookup"><span data-stu-id="93f9a-199">You can use only one in each command.</span></span>

- <span data-ttu-id="93f9a-200">Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93f9a-200">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="93f9a-201">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="93f9a-201">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="93f9a-202">Используйте их в том виде, в котором будут использоваться **dirname**, **нормпас**, **реалпас**, **Join** или другие манипуляторы пути.</span><span class="sxs-lookup"><span data-stu-id="93f9a-202">Use them in the way that you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

- <span data-ttu-id="93f9a-203">Командлеты **path** можно использовать вместе с несколькими поставщиками.</span><span class="sxs-lookup"><span data-stu-id="93f9a-203">You can use the **Path** cmdlets together with several providers.</span></span> <span data-ttu-id="93f9a-204">К ним относятся файловая система, реестр и поставщики сертификатов.</span><span class="sxs-lookup"><span data-stu-id="93f9a-204">These include the FileSystem, Registry, and Certificate providers.</span></span>

- <span data-ttu-id="93f9a-205">`Split-Path` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="93f9a-205">`Split-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="93f9a-206">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="93f9a-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="93f9a-207">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="93f9a-207">For more information, see about_Providers.</span></span>

## <span data-ttu-id="93f9a-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="93f9a-208">RELATED LINKS</span></span>

[<span data-ttu-id="93f9a-209">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="93f9a-209">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="93f9a-210">Join-Path</span><span class="sxs-lookup"><span data-stu-id="93f9a-210">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="93f9a-211">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="93f9a-211">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="93f9a-212">Test-Path</span><span class="sxs-lookup"><span data-stu-id="93f9a-212">Test-Path</span></span>](Test-Path.md)
