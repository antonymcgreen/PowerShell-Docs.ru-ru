---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227697"
---
# <span data-ttu-id="f102e-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="f102e-103">Export-Clixml</span></span>

## <span data-ttu-id="f102e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f102e-104">SYNOPSIS</span></span>
<span data-ttu-id="f102e-105">Создает XML-представление объекта или объектов и сохраняет его в файл.</span><span class="sxs-lookup"><span data-stu-id="f102e-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="f102e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f102e-106">SYNTAX</span></span>

### <span data-ttu-id="f102e-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f102e-107">ByPath (Default)</span></span>

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f102e-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="f102e-108">ByLiteralPath</span></span>

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f102e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f102e-109">DESCRIPTION</span></span>

<span data-ttu-id="f102e-110">`Export-Clixml`Командлет создает Common Language Infrastructure представление объекта или объектов (CLI) на основе XML и сохраняет их в файле.</span><span class="sxs-lookup"><span data-stu-id="f102e-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="f102e-111">Затем можно использовать `Import-Clixml` командлет для повторного создания сохраненного объекта на основе содержимого этого файла.</span><span class="sxs-lookup"><span data-stu-id="f102e-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="f102e-112">Дополнительные сведения о интерфейсе командной строки см. в разделе [независимость от языка](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="f102e-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="f102e-113">Этот командлет аналогичен `ConvertTo-Xml` , за исключением того, что `Export-Clixml` сохраняет результирующий XML в файле.</span><span class="sxs-lookup"><span data-stu-id="f102e-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="f102e-114">`ConvertTo-XML` Возвращает XML, поэтому вы можете продолжить его обработку в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f102e-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="f102e-115">Важным применением `Export-Clixml` на компьютерах с Windows является экспорт учетных данных и защита строк безопасно в виде XML.</span><span class="sxs-lookup"><span data-stu-id="f102e-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="f102e-116">Пример см. в примере 3.</span><span class="sxs-lookup"><span data-stu-id="f102e-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="f102e-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="f102e-117">EXAMPLES</span></span>

### <span data-ttu-id="f102e-118">Пример 1. Экспорт строки в XML-файл</span><span class="sxs-lookup"><span data-stu-id="f102e-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="f102e-119">В этом примере создается XML-файл, хранящийся в текущем каталоге, представление строки, которая **является тестом**.</span><span class="sxs-lookup"><span data-stu-id="f102e-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test**.</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="f102e-120">Строка, в которой **тест** отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f102e-120">The string **This is a test** is sent down the pipeline.</span></span> <span data-ttu-id="f102e-121">`Export-Clixml` использует параметр **path** для создания XML-файла с именем `sample.xml` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f102e-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="f102e-122">Пример 2. экспорт объекта в XML-файл</span><span class="sxs-lookup"><span data-stu-id="f102e-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="f102e-123">В этом примере показано, как экспортировать объект в XML-файл и затем создать объект путем импорта из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="f102e-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="f102e-124">`Get-Acl`Командлет возвращает дескриптор безопасности `Test.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="f102e-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="f102e-125">Он отправляет объект по конвейеру, чтобы передать дескриптор безопасности в `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="f102e-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="f102e-126">Представление объекта, основанное на XML, хранится в файле с именем `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="f102e-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="f102e-127">`Import-Clixml`Командлет создает объект из XML- `FileACL.xml` файла в файле.</span><span class="sxs-lookup"><span data-stu-id="f102e-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="f102e-128">Затем объект сохраняется в `$fileacl` переменной.</span><span class="sxs-lookup"><span data-stu-id="f102e-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="f102e-129">Пример 3. шифрование экспортированного объекта учетных данных</span><span class="sxs-lookup"><span data-stu-id="f102e-129">Example 3: Encrypt an exported credential object</span></span>

<span data-ttu-id="f102e-130">В этом примере с учетными данными, сохраненными в `$Credential` переменной путем запуска `Get-Credential` командлета, можно выполнить `Export-Clixml` командлет, чтобы сохранить учетные данные на диске.</span><span class="sxs-lookup"><span data-stu-id="f102e-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f102e-131">`Export-Clixml` экспортирует только зашифрованные учетные данные в Windows.</span><span class="sxs-lookup"><span data-stu-id="f102e-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="f102e-132">В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="f102e-132">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="f102e-133">`Export-Clixml`Командлет шифрует объекты учетных данных с помощью [API защиты данных](/previous-versions/windows/apps/hh464970(v=win.10))Windows.</span><span class="sxs-lookup"><span data-stu-id="f102e-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="f102e-134">Шифрование гарантирует, что только учетная запись пользователя на этом компьютере сможет расшифровать содержимое объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f102e-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span> <span data-ttu-id="f102e-135">Экспортированный `CLIXML` файл нельзя использовать на другом компьютере или другом пользователе.</span><span class="sxs-lookup"><span data-stu-id="f102e-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="f102e-136">В этом примере файл, в котором хранятся учетные данные, представлен `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="f102e-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="f102e-137">Замените **TestScript** именем скрипта, с которым загружаются учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f102e-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="f102e-138">Вы отправляете объект учетных данных по конвейеру в `Export-Clixml` и сохраняете его по пути, `$Credxmlpath` указанному в первой команде.</span><span class="sxs-lookup"><span data-stu-id="f102e-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="f102e-139">Чтобы автоматически импортировать учетные данные в скрипт, выполните последние две команды.</span><span class="sxs-lookup"><span data-stu-id="f102e-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="f102e-140">Выполните команду `Import-Clixml` , чтобы импортировать защищенный объект учетных данных в скрипт.</span><span class="sxs-lookup"><span data-stu-id="f102e-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="f102e-141">Этот импорт устраняет риск предоставления в скрипте обычных текстовых паролей.</span><span class="sxs-lookup"><span data-stu-id="f102e-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="f102e-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f102e-142">PARAMETERS</span></span>

### <span data-ttu-id="f102e-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f102e-143">-Confirm</span></span>

<span data-ttu-id="f102e-144">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f102e-144">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-145">-Depth</span><span class="sxs-lookup"><span data-stu-id="f102e-145">-Depth</span></span>

<span data-ttu-id="f102e-146">Указывает, сколько уровней вложенных объектов включается в XML-представление.</span><span class="sxs-lookup"><span data-stu-id="f102e-146">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="f102e-147">Значение по умолчанию — `2`.</span><span class="sxs-lookup"><span data-stu-id="f102e-147">The default value is `2`.</span></span>

<span data-ttu-id="f102e-148">Значение по умолчанию может быть переопределено для типа объекта в `Types.ps1xml` файлах.</span><span class="sxs-lookup"><span data-stu-id="f102e-148">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="f102e-149">Дополнительные сведения см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="f102e-149">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-150">-Encoding</span><span class="sxs-lookup"><span data-stu-id="f102e-150">-Encoding</span></span>

<span data-ttu-id="f102e-151">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="f102e-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="f102e-152">Значение по умолчанию — **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="f102e-152">The default value is **Unicode**.</span></span>

<span data-ttu-id="f102e-153">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f102e-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f102e-154">`ASCII` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="f102e-154">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="f102e-155">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f102e-155">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="f102e-156">`Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="f102e-156">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="f102e-157">`OEM` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="f102e-157">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="f102e-158">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f102e-158">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="f102e-159">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="f102e-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="f102e-160">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f102e-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="f102e-161">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f102e-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-162">-Force</span><span class="sxs-lookup"><span data-stu-id="f102e-162">-Force</span></span>

<span data-ttu-id="f102e-163">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="f102e-163">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="f102e-164">В результате командлет снимает атрибут только для чтения выходного файла при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f102e-164">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="f102e-165">Командлет попытается сбросить атрибут "только для чтения" после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="f102e-165">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="f102e-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f102e-166">-InputObject</span></span>

<span data-ttu-id="f102e-167">Задает объект для преобразования.</span><span class="sxs-lookup"><span data-stu-id="f102e-167">Specifies the object to be converted.</span></span> <span data-ttu-id="f102e-168">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="f102e-168">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="f102e-169">Также можно передать объекты в `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="f102e-169">You can also pipe objects to `Export-Clixml`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-170">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f102e-170">-LiteralPath</span></span>

<span data-ttu-id="f102e-171">Указывает путь к файлу, где будет храниться XML-представление объекта.</span><span class="sxs-lookup"><span data-stu-id="f102e-171">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="f102e-172">В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="f102e-172">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="f102e-173">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="f102e-173">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f102e-174">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="f102e-174">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f102e-175">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f102e-175">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-176">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="f102e-176">-NoClobber</span></span>

<span data-ttu-id="f102e-177">Указывает, что командлет не перезаписывает содержимое существующего файла.</span><span class="sxs-lookup"><span data-stu-id="f102e-177">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="f102e-178">По умолчанию, если файл существует по указанному пути, `Export-Clixml` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f102e-178">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-179">-Path</span><span class="sxs-lookup"><span data-stu-id="f102e-179">-Path</span></span>

<span data-ttu-id="f102e-180">Указывает путь к файлу, где будет храниться XML-представление объекта.</span><span class="sxs-lookup"><span data-stu-id="f102e-180">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f102e-181">-WhatIf</span></span>

<span data-ttu-id="f102e-182">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f102e-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f102e-183">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f102e-183">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f102e-184">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f102e-184">CommonParameters</span></span>

<span data-ttu-id="f102e-185">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f102e-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f102e-186">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f102e-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f102e-187">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f102e-187">INPUTS</span></span>

### <span data-ttu-id="f102e-188">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="f102e-188">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f102e-189">Можно выполнить конвейер любого объекта в `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="f102e-189">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="f102e-190">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f102e-190">OUTPUTS</span></span>

### <span data-ttu-id="f102e-191">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="f102e-191">System.IO.FileInfo</span></span>

<span data-ttu-id="f102e-192">`Export-Clixml` создает файл, содержащий XML.</span><span class="sxs-lookup"><span data-stu-id="f102e-192">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="f102e-193">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f102e-193">NOTES</span></span>

## <span data-ttu-id="f102e-194">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f102e-194">RELATED LINKS</span></span>

[<span data-ttu-id="f102e-195">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="f102e-195">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="f102e-196">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="f102e-196">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="f102e-197">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="f102e-197">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="f102e-198">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="f102e-198">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="f102e-199">Join-Path</span><span class="sxs-lookup"><span data-stu-id="f102e-199">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

<span data-ttu-id="f102e-200">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk) (Безопасное хранение учетных данных на диске)</span><span class="sxs-lookup"><span data-stu-id="f102e-200">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)</span></span>

<span data-ttu-id="f102e-201">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/) (Передача учетных данных в устаревшие системы с помощью PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f102e-201">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)</span></span>

[<span data-ttu-id="f102e-202">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="f102e-202">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
