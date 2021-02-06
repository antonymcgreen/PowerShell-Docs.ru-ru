---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: a79f12739643a873703b39d9d07e8b7db01dfbb4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603957"
---
# <span data-ttu-id="11440-102">Test-Path</span><span class="sxs-lookup"><span data-stu-id="11440-102">Test-Path</span></span>

## <span data-ttu-id="11440-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="11440-103">SYNOPSIS</span></span>
<span data-ttu-id="11440-104">Определяет, все ли элементы пути существуют.</span><span class="sxs-lookup"><span data-stu-id="11440-104">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="11440-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11440-105">SYNTAX</span></span>

### <span data-ttu-id="11440-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="11440-106">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="11440-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="11440-107">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="11440-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="11440-108">DESCRIPTION</span></span>

<span data-ttu-id="11440-109">`Test-Path`Командлет определяет, существуют ли все элементы пути.</span><span class="sxs-lookup"><span data-stu-id="11440-109">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="11440-110">Он возвращает значение `$True` , если все элементы существуют и `$False` отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="11440-110">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="11440-111">Он также может определить, является ли синтаксис пути допустимым, и указывает, ведет ли путь к контейнеру или элементу терминала или листу.</span><span class="sxs-lookup"><span data-stu-id="11440-111">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="11440-112">Если `Path` является пустой строкой, `$False` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="11440-112">If the `Path` is whitespace an empty string, then `$False` is returned.</span></span> <span data-ttu-id="11440-113">Если `Path` имеет значение `$null` , массив `$null` или пустой массив, возвращается Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="11440-113">If the `Path` is `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="11440-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="11440-114">EXAMPLES</span></span>

### <span data-ttu-id="11440-115">Пример 1. Проверка пути</span><span class="sxs-lookup"><span data-stu-id="11440-115">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="11440-116">Эта команда проверяет, существуют ли все элементы в пути, т. е. каталог C:, каталог Documents и Settings и каталог Давидк.</span><span class="sxs-lookup"><span data-stu-id="11440-116">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="11440-117">Если таковые отсутствуют, командлет возвращает `$False` .</span><span class="sxs-lookup"><span data-stu-id="11440-117">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="11440-118">В противном случае возвращается значение `$True`.</span><span class="sxs-lookup"><span data-stu-id="11440-118">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="11440-119">Пример 2. Проверка пути к профилю</span><span class="sxs-lookup"><span data-stu-id="11440-119">Example 2: Test the path of a profile</span></span>

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

<span data-ttu-id="11440-120">Эти команды проверяют путь к профилю PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11440-120">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="11440-121">Первая команда определяет, существуют ли все элементы пути.</span><span class="sxs-lookup"><span data-stu-id="11440-121">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="11440-122">Вторая команда определяет, правилен ли синтаксис пути.</span><span class="sxs-lookup"><span data-stu-id="11440-122">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="11440-123">В этом случае путь имеет значение `$False` , но синтаксис правильный `$True` .</span><span class="sxs-lookup"><span data-stu-id="11440-123">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="11440-124">Эти команды используют `$profile` , автоматически изменяемую переменную, указывающую на расположение профиля, даже если профиль не существует.</span><span class="sxs-lookup"><span data-stu-id="11440-124">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="11440-125">Подробнее об автоматических переменных см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="11440-125">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="11440-126">Пример 3. Проверка наличия файлов, кроме указанного типа</span><span class="sxs-lookup"><span data-stu-id="11440-126">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="11440-127">Эта команда проверяет наличие в каталоге коммерческих зданий файлов, отличных от файлов DWG.</span><span class="sxs-lookup"><span data-stu-id="11440-127">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="11440-128">Команда использует параметр **path** для указания пути.</span><span class="sxs-lookup"><span data-stu-id="11440-128">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="11440-129">Так как путь содержит пробел, путь заключается в кавычки.</span><span class="sxs-lookup"><span data-stu-id="11440-129">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="11440-130">Звездочка в конце пути означает содержимое каталога Commercial Building.</span><span class="sxs-lookup"><span data-stu-id="11440-130">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="11440-131">При использовании длинных путей, например, введите первые несколько букв пути, а затем используйте клавишу TAB для завершения пути.</span><span class="sxs-lookup"><span data-stu-id="11440-131">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="11440-132">Команда задает параметр **Exclude** для указания файлов, которые будут пропущены при вычислении.</span><span class="sxs-lookup"><span data-stu-id="11440-132">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="11440-133">В этом случае, поскольку каталог содержит только файлы. DWG, результатом будет `$False` .</span><span class="sxs-lookup"><span data-stu-id="11440-133">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="11440-134">Пример 4. Проверка файла</span><span class="sxs-lookup"><span data-stu-id="11440-134">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="11440-135">Эта команда проверяет, ведет ли путь, хранящийся в `$profile` переменной, в файл.</span><span class="sxs-lookup"><span data-stu-id="11440-135">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="11440-136">В этом случае, поскольку профиль PowerShell является `.ps1` файлом, командлет возвращает `$True` .</span><span class="sxs-lookup"><span data-stu-id="11440-136">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="11440-137">Пример 5. Проверка путей в реестре</span><span class="sxs-lookup"><span data-stu-id="11440-137">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="11440-138">Эти команды используются `Test-Path` с поставщиком реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11440-138">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="11440-139">Первая команда проверяет, правильно ли указан путь реестра в разделе реестра **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="11440-139">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="11440-140">Если PowerShell установлен правильно, командлет возвращает `$True` .</span><span class="sxs-lookup"><span data-stu-id="11440-140">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11440-141">`Test-Path` не работает правильно со всеми поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11440-141">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="11440-142">Например, можно использовать `Test-Path` для проверки пути к разделу реестра, но при его использовании для проверки пути к записи реестра он всегда возвращает значение `$False` , даже если имеется запись реестра.</span><span class="sxs-lookup"><span data-stu-id="11440-142">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

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

### <span data-ttu-id="11440-143">Пример 6. Проверка, является ли файл более новым, чем указанная дата</span><span class="sxs-lookup"><span data-stu-id="11440-143">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="11440-144">Эта команда использует динамический параметр **неверсан** , чтобы определить, новее ли файл "PowerShell.exe" на компьютере, чем "13 июля, 2009".</span><span class="sxs-lookup"><span data-stu-id="11440-144">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="11440-145">Параметр NewerThan работает только на дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="11440-145">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="11440-146">Пример 7. Проверка пути со значением NULL в качестве значения</span><span class="sxs-lookup"><span data-stu-id="11440-146">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="11440-147">Ошибка, возвращенная для `null` , массив `null` или пустой массив, является неустранимой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="11440-147">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="11440-148">Его можно отключить с помощью `-ErrorAction SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="11440-148">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="11440-149">В следующем примере показаны все случаи, которые возвращают `NullPathNotPermitted` ошибку.</span><span class="sxs-lookup"><span data-stu-id="11440-149">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

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

### <span data-ttu-id="11440-150">Пример 8. Проверка пути с пробелом в качестве значения</span><span class="sxs-lookup"><span data-stu-id="11440-150">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="11440-151">Если для параметра указан пробел или пустая строка `-Path` , возвращается **значение false**.</span><span class="sxs-lookup"><span data-stu-id="11440-151">When a whitespace or empty string is provided for the the `-Path` parameter, it returns **False**.</span></span>
<span data-ttu-id="11440-152">В следующем примере показаны пробелы и пустая строка.</span><span class="sxs-lookup"><span data-stu-id="11440-152">The following example show whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## <span data-ttu-id="11440-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11440-153">PARAMETERS</span></span>

### <span data-ttu-id="11440-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="11440-154">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="11440-155">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11440-155">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="11440-156">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="11440-156">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="11440-157">-Exclude</span><span class="sxs-lookup"><span data-stu-id="11440-157">-Exclude</span></span>

<span data-ttu-id="11440-158">Указывает элементы, которые пропускает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="11440-158">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="11440-159">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="11440-159">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="11440-160">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="11440-160">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="11440-161">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11440-161">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="11440-162">-Filter</span><span class="sxs-lookup"><span data-stu-id="11440-162">-Filter</span></span>

<span data-ttu-id="11440-163">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="11440-163">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="11440-164">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="11440-164">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="11440-165">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="11440-165">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="11440-166">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при извлечении объектов вместо того, чтобы использовать PowerShell для фильтрации объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="11440-166">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="11440-167">-Include</span><span class="sxs-lookup"><span data-stu-id="11440-167">-Include</span></span>

<span data-ttu-id="11440-168">Указывает пути, которые проверяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="11440-168">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="11440-169">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="11440-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="11440-170">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="11440-170">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="11440-171">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11440-171">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="11440-172">-IsValid</span><span class="sxs-lookup"><span data-stu-id="11440-172">-IsValid</span></span>

<span data-ttu-id="11440-173">Указывает, что этот командлет проверяет синтаксис пути независимо от того, существуют ли элементы пути.</span><span class="sxs-lookup"><span data-stu-id="11440-173">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="11440-174">Этот командлет возвращает значение, `$True` Если синтаксис пути допустим, и `$False` Если нет.</span><span class="sxs-lookup"><span data-stu-id="11440-174">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

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

### <span data-ttu-id="11440-175">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="11440-175">-LiteralPath</span></span>

<span data-ttu-id="11440-176">Указывает проверяемый путь.</span><span class="sxs-lookup"><span data-stu-id="11440-176">Specifies a path to be tested.</span></span> <span data-ttu-id="11440-177">В отличие от параметра **Path**, значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="11440-177">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="11440-178">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11440-178">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="11440-179">Если путь содержит символы, которые могут интерпретироваться в PowerShell как escape-последовательности, необходимо заключить путь в одинарные кавычки, чтобы они не были интерпретированы.</span><span class="sxs-lookup"><span data-stu-id="11440-179">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="11440-180">-Неверсан</span><span class="sxs-lookup"><span data-stu-id="11440-180">-NewerThan</span></span>

<span data-ttu-id="11440-181">Укажите время в качестве объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="11440-181">Specify a time as a **DateTime** object.</span></span>

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

### <span data-ttu-id="11440-182">-Олдерсан</span><span class="sxs-lookup"><span data-stu-id="11440-182">-OlderThan</span></span>

<span data-ttu-id="11440-183">Укажите время в качестве объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="11440-183">Specify a time as a **DateTime** object.</span></span>

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

### <span data-ttu-id="11440-184">-Path</span><span class="sxs-lookup"><span data-stu-id="11440-184">-Path</span></span>

<span data-ttu-id="11440-185">Указывает проверяемый путь.</span><span class="sxs-lookup"><span data-stu-id="11440-185">Specifies a path to be tested.</span></span> <span data-ttu-id="11440-186">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="11440-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="11440-187">Если путь содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="11440-187">If the path includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="11440-188">-Пастипе</span><span class="sxs-lookup"><span data-stu-id="11440-188">-PathType</span></span>

<span data-ttu-id="11440-189">Задает тип последнего элемента в пути.</span><span class="sxs-lookup"><span data-stu-id="11440-189">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="11440-190">Этот командлет возвращает, `$True` Если элемент имеет указанный тип и `$False` не имеет значение.</span><span class="sxs-lookup"><span data-stu-id="11440-190">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="11440-191">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="11440-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="11440-192">Контейнер.</span><span class="sxs-lookup"><span data-stu-id="11440-192">Container.</span></span>
  <span data-ttu-id="11440-193">элемент, содержащий другие элементы, например каталог или раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="11440-193">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="11440-194">Конечного.</span><span class="sxs-lookup"><span data-stu-id="11440-194">Leaf.</span></span>
  <span data-ttu-id="11440-195">элемент, который не содержит другие элементы, например файл.</span><span class="sxs-lookup"><span data-stu-id="11440-195">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="11440-196">Всеми.</span><span class="sxs-lookup"><span data-stu-id="11440-196">Any.</span></span>
  <span data-ttu-id="11440-197">или контейнер, или конечный элемент.</span><span class="sxs-lookup"><span data-stu-id="11440-197">Either a container or a leaf.</span></span>

<span data-ttu-id="11440-198">Определяет, имеет ли конечный элемент пути определенный тип.</span><span class="sxs-lookup"><span data-stu-id="11440-198">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="11440-199">До PowerShell версии 6.1.2, когда параметры **IsValid** и **пастипе** указаны вместе, `Test-Path` командлет игнорирует параметр **пастипе** и проверяет только синтаксическую путь без проверки типа пути.</span><span class="sxs-lookup"><span data-stu-id="11440-199">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="11440-200">В соответствии с [#8607 проблемы](https://github.com/PowerShell/PowerShell/issues/8607)исправление этого поведения может быть критическим изменением в будущей версии, где параметры **IsValid** и **пастипе** относятся к отдельным наборам параметров, и поэтому не могут использоваться совместно, избегая этой путаницы.</span><span class="sxs-lookup"><span data-stu-id="11440-200">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

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

### <span data-ttu-id="11440-201">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="11440-201">CommonParameters</span></span>

<span data-ttu-id="11440-202">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="11440-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="11440-203">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="11440-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="11440-204">Входные данные</span><span class="sxs-lookup"><span data-stu-id="11440-204">INPUTS</span></span>

### <span data-ttu-id="11440-205">System.String</span><span class="sxs-lookup"><span data-stu-id="11440-205">System.String</span></span>

<span data-ttu-id="11440-206">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="11440-206">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="11440-207">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="11440-207">OUTPUTS</span></span>

### <span data-ttu-id="11440-208">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="11440-208">System.Boolean</span></span>

<span data-ttu-id="11440-209">Командлет возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="11440-209">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="11440-210">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="11440-210">NOTES</span></span>

<span data-ttu-id="11440-211">Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11440-211">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="11440-212">Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="11440-212">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="11440-213">Используйте их, как при использовании **dirname**, **нормпас**, **реалпас**, **Join** или других манипуляторов пути.</span><span class="sxs-lookup"><span data-stu-id="11440-213">Use them as you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

<span data-ttu-id="11440-214">Объект `Test-Path` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="11440-214">The `Test-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="11440-215">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="11440-215">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="11440-216">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="11440-216">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="11440-217">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="11440-217">RELATED LINKS</span></span>

[<span data-ttu-id="11440-218">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="11440-218">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="11440-219">Join-Path</span><span class="sxs-lookup"><span data-stu-id="11440-219">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="11440-220">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="11440-220">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="11440-221">Split-Path</span><span class="sxs-lookup"><span data-stu-id="11440-221">Split-Path</span></span>](Split-Path.md)
