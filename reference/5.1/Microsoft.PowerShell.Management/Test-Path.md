---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: ced5a5db05674c15fefada73ab55969d724117e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227830"
---
# <span data-ttu-id="99e58-103">Test-Path</span><span class="sxs-lookup"><span data-stu-id="99e58-103">Test-Path</span></span>

## <span data-ttu-id="99e58-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="99e58-104">SYNOPSIS</span></span>
<span data-ttu-id="99e58-105">Определяет, все ли элементы пути существуют.</span><span class="sxs-lookup"><span data-stu-id="99e58-105">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="99e58-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99e58-106">SYNTAX</span></span>

### <span data-ttu-id="99e58-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="99e58-107">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>] [-UseTransaction]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="99e58-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="99e58-108">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>] [-UseTransaction]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="99e58-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99e58-109">DESCRIPTION</span></span>

<span data-ttu-id="99e58-110">`Test-Path`Командлет определяет, существуют ли все элементы пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-110">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="99e58-111">Он возвращает значение `$True` , если все элементы существуют и `$False` отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="99e58-111">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="99e58-112">Он также может определить, является ли синтаксис пути допустимым, и указывает, ведет ли путь к контейнеру или элементу терминала или листу.</span><span class="sxs-lookup"><span data-stu-id="99e58-112">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="99e58-113">Если `Path` является пробелом, `$False` возвращается.</span><span class="sxs-lookup"><span data-stu-id="99e58-113">If the `Path` is whitespace, then `$False` is returned.</span></span> <span data-ttu-id="99e58-114">Если `Path` представляет собой пустую строку, `$null` массив `$null` или пустой массив, возвращается Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="99e58-114">If the `Path` is an empty string, `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="99e58-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="99e58-115">EXAMPLES</span></span>

### <span data-ttu-id="99e58-116">Пример 1. Проверка пути</span><span class="sxs-lookup"><span data-stu-id="99e58-116">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="99e58-117">Эта команда проверяет, существуют ли все элементы в пути, т. е. каталог C:, каталог Documents и Settings и каталог Давидк.</span><span class="sxs-lookup"><span data-stu-id="99e58-117">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="99e58-118">Если таковые отсутствуют, командлет возвращает `$False` .</span><span class="sxs-lookup"><span data-stu-id="99e58-118">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="99e58-119">В противном случае она возвращает `$True`.</span><span class="sxs-lookup"><span data-stu-id="99e58-119">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="99e58-120">Пример 2. Проверка пути к профилю</span><span class="sxs-lookup"><span data-stu-id="99e58-120">Example 2: Test the path of a profile</span></span>

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

<span data-ttu-id="99e58-121">Эти команды проверяют путь к профилю PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99e58-121">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="99e58-122">Первая команда определяет, существуют ли все элементы пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-122">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="99e58-123">Вторая команда определяет, правилен ли синтаксис пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-123">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="99e58-124">В этом случае путь имеет значение `$False` , но синтаксис правильный `$True` .</span><span class="sxs-lookup"><span data-stu-id="99e58-124">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="99e58-125">Эти команды используют `$profile` , автоматически изменяемую переменную, указывающую на расположение профиля, даже если профиль не существует.</span><span class="sxs-lookup"><span data-stu-id="99e58-125">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="99e58-126">Подробнее об автоматических переменных см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="99e58-126">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="99e58-127">Пример 3. Проверка наличия файлов, кроме указанного типа</span><span class="sxs-lookup"><span data-stu-id="99e58-127">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="99e58-128">Эта команда проверяет наличие в каталоге коммерческих зданий файлов, отличных от файлов DWG.</span><span class="sxs-lookup"><span data-stu-id="99e58-128">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="99e58-129">Команда использует параметр **path** для указания пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-129">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="99e58-130">Так как путь содержит пробел, путь заключается в кавычки.</span><span class="sxs-lookup"><span data-stu-id="99e58-130">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="99e58-131">Звездочка в конце пути означает содержимое каталога Commercial Building.</span><span class="sxs-lookup"><span data-stu-id="99e58-131">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="99e58-132">При использовании длинных путей, например, введите первые несколько букв пути, а затем используйте клавишу TAB для завершения пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-132">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="99e58-133">Команда задает параметр **Exclude** для указания файлов, которые будут пропущены при вычислении.</span><span class="sxs-lookup"><span data-stu-id="99e58-133">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="99e58-134">В этом случае, поскольку каталог содержит только файлы. DWG, результатом будет `$False` .</span><span class="sxs-lookup"><span data-stu-id="99e58-134">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="99e58-135">Пример 4. Проверка файла</span><span class="sxs-lookup"><span data-stu-id="99e58-135">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="99e58-136">Эта команда проверяет, ведет ли путь, хранящийся в `$profile` переменной, в файл.</span><span class="sxs-lookup"><span data-stu-id="99e58-136">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="99e58-137">В этом случае, поскольку профиль PowerShell является `.ps1` файлом, командлет возвращает `$True` .</span><span class="sxs-lookup"><span data-stu-id="99e58-137">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="99e58-138">Пример 5. Проверка путей в реестре</span><span class="sxs-lookup"><span data-stu-id="99e58-138">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="99e58-139">Эти команды используются `Test-Path` с поставщиком реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99e58-139">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="99e58-140">Первая команда проверяет, правильно ли указан путь реестра в разделе реестра **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="99e58-140">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="99e58-141">Если PowerShell установлен правильно, командлет возвращает `$True` .</span><span class="sxs-lookup"><span data-stu-id="99e58-141">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99e58-142">`Test-Path` не работает правильно со всеми поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99e58-142">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="99e58-143">Например, можно использовать `Test-Path` для проверки пути к разделу реестра, но при его использовании для проверки пути к записи реестра он всегда возвращает значение `$False` , даже если имеется запись реестра.</span><span class="sxs-lookup"><span data-stu-id="99e58-143">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### <span data-ttu-id="99e58-144">Пример 6. Проверка, является ли файл более новым, чем указанная дата</span><span class="sxs-lookup"><span data-stu-id="99e58-144">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="99e58-145">Эта команда использует динамический параметр **неверсан** , чтобы определить, новее ли файл "PowerShell.exe" на компьютере, чем "13 июля, 2009".</span><span class="sxs-lookup"><span data-stu-id="99e58-145">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="99e58-146">Параметр NewerThan работает только на дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="99e58-146">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="99e58-147">Пример 7. Проверка пути со значением NULL в качестве значения</span><span class="sxs-lookup"><span data-stu-id="99e58-147">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="99e58-148">Ошибка, возвращенная для `null` , массив `null` или пустой массив, является неустранимой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="99e58-148">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="99e58-149">Его можно отключить с помощью `-ErrorAction SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="99e58-149">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="99e58-150">В следующем примере показаны все случаи, которые возвращают `NullPathNotPermitted` ошибку.</span><span class="sxs-lookup"><span data-stu-id="99e58-150">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### <span data-ttu-id="99e58-151">Пример 8. Проверка пути с пробелом в качестве значения</span><span class="sxs-lookup"><span data-stu-id="99e58-151">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="99e58-152">Если для параметра указана пустая строка `-Path` , возвращается **значение true** .</span><span class="sxs-lookup"><span data-stu-id="99e58-152">When a whitespace string is provided for the the `-Path` parameter, it returns **True** .</span></span> <span data-ttu-id="99e58-153">Если указана пустая строка, функция `Test-Path` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="99e58-153">When an empty string is provided, `Test-Path` returns an error.</span></span> <span data-ttu-id="99e58-154">В следующем примере показаны пробелы и пустая строка.</span><span class="sxs-lookup"><span data-stu-id="99e58-154">The following example shows whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
True
Test-Path : Cannot bind argument to parameter 'Path' because it is an empty string.
At line:1 char:11
+ Test-Path ''
+           ~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorEmptyStringNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

## <span data-ttu-id="99e58-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99e58-155">PARAMETERS</span></span>

### <span data-ttu-id="99e58-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="99e58-156">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="99e58-157">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99e58-157">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="99e58-158">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="99e58-158">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="99e58-159">-Exclude</span><span class="sxs-lookup"><span data-stu-id="99e58-159">-Exclude</span></span>

<span data-ttu-id="99e58-160">Указывает элементы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="99e58-160">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="99e58-161">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="99e58-161">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="99e58-162">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="99e58-162">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="99e58-163">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99e58-163">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="99e58-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="99e58-164">-Filter</span></span>

<span data-ttu-id="99e58-165">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="99e58-165">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="99e58-166">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="99e58-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="99e58-167">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="99e58-167">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="99e58-168">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов вместо того, чтобы использовать PowerShell для фильтрации объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="99e58-168">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="99e58-169">-Include</span><span class="sxs-lookup"><span data-stu-id="99e58-169">-Include</span></span>

<span data-ttu-id="99e58-170">Указывает пути, которые проверяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="99e58-170">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="99e58-171">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="99e58-171">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="99e58-172">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="99e58-172">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="99e58-173">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99e58-173">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="99e58-174">-IsValid</span><span class="sxs-lookup"><span data-stu-id="99e58-174">-IsValid</span></span>

<span data-ttu-id="99e58-175">Указывает, что этот командлет проверяет синтаксис пути независимо от того, существуют ли элементы пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-175">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="99e58-176">Этот командлет возвращает значение, `$True` Если синтаксис пути допустим, и `$False` Если нет.</span><span class="sxs-lookup"><span data-stu-id="99e58-176">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

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

### <span data-ttu-id="99e58-177">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="99e58-177">-LiteralPath</span></span>

<span data-ttu-id="99e58-178">Указывает проверяемый путь.</span><span class="sxs-lookup"><span data-stu-id="99e58-178">Specifies a path to be tested.</span></span> <span data-ttu-id="99e58-179">В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="99e58-179">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="99e58-180">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99e58-180">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="99e58-181">Если путь содержит символы, которые могут интерпретироваться в PowerShell как escape-последовательности, необходимо заключить путь в одинарные кавычки, чтобы они не были интерпретированы.</span><span class="sxs-lookup"><span data-stu-id="99e58-181">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99e58-182">-Неверсан</span><span class="sxs-lookup"><span data-stu-id="99e58-182">-NewerThan</span></span>

<span data-ttu-id="99e58-183">Укажите время в качестве объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="99e58-183">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99e58-184">-Олдерсан</span><span class="sxs-lookup"><span data-stu-id="99e58-184">-OlderThan</span></span>

<span data-ttu-id="99e58-185">Укажите время в качестве объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="99e58-185">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99e58-186">-Path</span><span class="sxs-lookup"><span data-stu-id="99e58-186">-Path</span></span>

<span data-ttu-id="99e58-187">Указывает проверяемый путь.</span><span class="sxs-lookup"><span data-stu-id="99e58-187">Specifies a path to be tested.</span></span> <span data-ttu-id="99e58-188">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99e58-188">Wildcard characters are permitted.</span></span> <span data-ttu-id="99e58-189">Если путь содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="99e58-189">If the path includes spaces, enclose it in quotation marks.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="99e58-190">-Пастипе</span><span class="sxs-lookup"><span data-stu-id="99e58-190">-PathType</span></span>

<span data-ttu-id="99e58-191">Задает тип последнего элемента в пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-191">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="99e58-192">Этот командлет возвращает, `$True` Если элемент имеет указанный тип и `$False` не имеет значение.</span><span class="sxs-lookup"><span data-stu-id="99e58-192">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="99e58-193">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="99e58-193">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="99e58-194">Контейнер.</span><span class="sxs-lookup"><span data-stu-id="99e58-194">Container.</span></span>
  <span data-ttu-id="99e58-195">элемент, содержащий другие элементы, например каталог или раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="99e58-195">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="99e58-196">Конечного.</span><span class="sxs-lookup"><span data-stu-id="99e58-196">Leaf.</span></span>
  <span data-ttu-id="99e58-197">элемент, который не содержит другие элементы, например файл.</span><span class="sxs-lookup"><span data-stu-id="99e58-197">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="99e58-198">Всеми.</span><span class="sxs-lookup"><span data-stu-id="99e58-198">Any.</span></span>
  <span data-ttu-id="99e58-199">или контейнер, или конечный элемент.</span><span class="sxs-lookup"><span data-stu-id="99e58-199">Either a container or a leaf.</span></span>

<span data-ttu-id="99e58-200">Определяет, имеет ли конечный элемент пути определенный тип.</span><span class="sxs-lookup"><span data-stu-id="99e58-200">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="99e58-201">До PowerShell версии 6.1.2, когда параметры **IsValid** и **пастипе** указаны вместе, `Test-Path` командлет игнорирует параметр **пастипе** и проверяет только синтаксическую путь без проверки типа пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-201">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="99e58-202">В соответствии с [#8607 проблемы](https://github.com/PowerShell/PowerShell/issues/8607)исправление этого поведения может быть критическим изменением в будущей версии, где параметры **IsValid** и **пастипе** относятся к отдельным наборам параметров, и поэтому не могут использоваться совместно, избегая этой путаницы.</span><span class="sxs-lookup"><span data-stu-id="99e58-202">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99e58-203">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="99e58-203">-UseTransaction</span></span>

<span data-ttu-id="99e58-204">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="99e58-204">Includes the command in the active transaction.</span></span> <span data-ttu-id="99e58-205">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="99e58-205">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="99e58-206">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span><span class="sxs-lookup"><span data-stu-id="99e58-206">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span></span>

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

### <span data-ttu-id="99e58-207">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="99e58-207">CommonParameters</span></span>

<span data-ttu-id="99e58-208">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="99e58-208">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="99e58-209">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="99e58-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="99e58-210">Входные данные</span><span class="sxs-lookup"><span data-stu-id="99e58-210">INPUTS</span></span>

### <span data-ttu-id="99e58-211">System.String</span><span class="sxs-lookup"><span data-stu-id="99e58-211">System.String</span></span>

<span data-ttu-id="99e58-212">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="99e58-212">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="99e58-213">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="99e58-213">OUTPUTS</span></span>

### <span data-ttu-id="99e58-214">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="99e58-214">System.Boolean</span></span>

<span data-ttu-id="99e58-215">Командлет возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="99e58-215">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="99e58-216">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="99e58-216">NOTES</span></span>

<span data-ttu-id="99e58-217">Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99e58-217">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="99e58-218">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="99e58-218">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="99e58-219">Используйте их, как при использовании **dirname** , **нормпас** , **реалпас** , **Join** или других манипуляторов пути.</span><span class="sxs-lookup"><span data-stu-id="99e58-219">Use them as you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="99e58-220">Объект `Test-Path` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="99e58-220">The `Test-Path` is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="99e58-221">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="99e58-221">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="99e58-222">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="99e58-222">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="99e58-223">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="99e58-223">RELATED LINKS</span></span>

[<span data-ttu-id="99e58-224">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="99e58-224">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="99e58-225">Join-Path</span><span class="sxs-lookup"><span data-stu-id="99e58-225">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="99e58-226">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="99e58-226">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="99e58-227">Split-Path</span><span class="sxs-lookup"><span data-stu-id="99e58-227">Split-Path</span></span>](Split-Path.md)
