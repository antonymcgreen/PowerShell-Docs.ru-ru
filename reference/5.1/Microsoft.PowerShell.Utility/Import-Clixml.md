---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: 4e6d7e584350d25816dbc32ea35a50d916d9ffe4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227609"
---
# <span data-ttu-id="524d1-103">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="524d1-103">Import-Clixml</span></span>

## <span data-ttu-id="524d1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="524d1-104">SYNOPSIS</span></span>
<span data-ttu-id="524d1-105">Импортирует файл CLIXML и создает соответствующие объекты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="524d1-105">Imports a CLIXML file and creates corresponding objects in PowerShell.</span></span>

## <span data-ttu-id="524d1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="524d1-106">SYNTAX</span></span>

### <span data-ttu-id="524d1-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="524d1-107">ByPath (Default)</span></span>

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### <span data-ttu-id="524d1-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="524d1-108">ByLiteralPath</span></span>

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## <span data-ttu-id="524d1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="524d1-109">DESCRIPTION</span></span>

<span data-ttu-id="524d1-110">`Import-Clixml`Командлет импортирует XML-файл Common Language Infrastructure (CLI) с данными, представляющими объекты платформы Microsoft .NET и создает объекты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="524d1-110">The `Import-Clixml` cmdlet imports a Common Language Infrastructure (CLI) XML file with data that represents Microsoft .NET Framework objects and creates the PowerShell objects.</span></span> <span data-ttu-id="524d1-111">Дополнительные сведения о интерфейсе командной строки см. в разделе [независимость от языка](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="524d1-111">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="524d1-112">Важным применением `Import-Clixml` на компьютерах Windows является импорт учетных данных и защищенных строк, экспортированных в виде защищенного XML с помощью `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="524d1-112">A valuable use of `Import-Clixml` on Windows computers is to import credentials and secure strings that were exported as secure XML using `Export-Clixml`.</span></span> <span data-ttu-id="524d1-113">Пример см. в примере 2.</span><span class="sxs-lookup"><span data-stu-id="524d1-113">For an example, see Example 2.</span></span>

<span data-ttu-id="524d1-114">`Import-Clixml` для определения формата кодирования файла использует символ-отметку (BOM).</span><span class="sxs-lookup"><span data-stu-id="524d1-114">`Import-Clixml` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="524d1-115">Если файл не имеет BOM, предполагается, что используется кодировка UTF8.</span><span class="sxs-lookup"><span data-stu-id="524d1-115">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="524d1-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="524d1-116">EXAMPLES</span></span>

### <span data-ttu-id="524d1-117">Пример 1. Импорт сериализованного файла и повторное создание объекта</span><span class="sxs-lookup"><span data-stu-id="524d1-117">Example 1: Import a serialized file and recreate an object</span></span>

<span data-ttu-id="524d1-118">В этом примере `Export-Clixml` командлет используется для сохранения сериализованной копии сведений о процессе, возвращаемых `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="524d1-118">This example uses the `Export-Clixml` cmdlet to save a serialized copy of the process information returned by `Get-Process`.</span></span> <span data-ttu-id="524d1-119">`Import-Clixml` Извлекает содержимое сериализованного файла и повторно создает объект, хранящийся в `$Processes` переменной.</span><span class="sxs-lookup"><span data-stu-id="524d1-119">`Import-Clixml` retrieves the serialized file's contents and recreates an object that is stored in the `$Processes` variable.</span></span>

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### <span data-ttu-id="524d1-120">Пример 2. Импорт защищенного объекта учетных данных</span><span class="sxs-lookup"><span data-stu-id="524d1-120">Example 2: Import a secure credential object</span></span>

<span data-ttu-id="524d1-121">В этом примере с учетными данными, сохраненными в `$Credential` переменной путем запуска `Get-Credential` командлета, можно выполнить `Export-Clixml` командлет, чтобы сохранить учетные данные на диске.</span><span class="sxs-lookup"><span data-stu-id="524d1-121">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="524d1-122">`Export-Clixml` экспортирует только зашифрованные учетные данные в Windows.</span><span class="sxs-lookup"><span data-stu-id="524d1-122">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="524d1-123">В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="524d1-123">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="524d1-124">`Export-Clixml`Командлет шифрует объекты учетных данных с помощью [API защиты данных](/previous-versions/windows/apps/hh464970(v=win.10))Windows.</span><span class="sxs-lookup"><span data-stu-id="524d1-124">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="524d1-125">Шифрование гарантирует, что только ваша учетная запись пользователя сможет расшифровать содержимое объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="524d1-125">The encryption ensures that only your user account can decrypt the contents of the credential object.</span></span> <span data-ttu-id="524d1-126">Экспортированный `CLIXML` файл нельзя использовать на другом компьютере или другом пользователе.</span><span class="sxs-lookup"><span data-stu-id="524d1-126">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="524d1-127">В этом примере файл, в котором хранятся учетные данные, представлен `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="524d1-127">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="524d1-128">Замените **TestScript** именем скрипта, с которым загружаются учетные данные.</span><span class="sxs-lookup"><span data-stu-id="524d1-128">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="524d1-129">Вы отправляете объект учетных данных по конвейеру в `Export-Clixml` и сохраняете его по пути, `$Credxmlpath` указанному в первой команде.</span><span class="sxs-lookup"><span data-stu-id="524d1-129">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="524d1-130">Чтобы автоматически импортировать учетные данные в скрипт, выполните последние две команды.</span><span class="sxs-lookup"><span data-stu-id="524d1-130">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="524d1-131">Выполните команду `Import-Clixml` , чтобы импортировать защищенный объект учетных данных в скрипт.</span><span class="sxs-lookup"><span data-stu-id="524d1-131">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="524d1-132">Этот импорт устраняет риск предоставления в скрипте обычных текстовых паролей.</span><span class="sxs-lookup"><span data-stu-id="524d1-132">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="524d1-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="524d1-133">PARAMETERS</span></span>

### <span data-ttu-id="524d1-134">-First</span><span class="sxs-lookup"><span data-stu-id="524d1-134">-First</span></span>

<span data-ttu-id="524d1-135">Получает только указанное количество объектов.</span><span class="sxs-lookup"><span data-stu-id="524d1-135">Gets only the specified number of objects.</span></span> <span data-ttu-id="524d1-136">Введите количество объектов, которые необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="524d1-136">Enter the number of objects to get.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="524d1-137">-IncludeTotalCount</span><span class="sxs-lookup"><span data-stu-id="524d1-137">-IncludeTotalCount</span></span>

<span data-ttu-id="524d1-138">Сообщает общее число объектов в наборе данных, за которыми следуют выбранные объекты.</span><span class="sxs-lookup"><span data-stu-id="524d1-138">Reports the total number of objects in the data set followed by the selected objects.</span></span> <span data-ttu-id="524d1-139">Если командлет не может определить общее число, отображается **неизвестное общее число**.</span><span class="sxs-lookup"><span data-stu-id="524d1-139">If the cmdlet can't determine the total count, it displays **Unknown total count**.</span></span> <span data-ttu-id="524d1-140">Целочисленное значение имеет свойство **точности** , которое указывает надежность общего значения Count.</span><span class="sxs-lookup"><span data-stu-id="524d1-140">The integer has an **Accuracy** property that indicates the reliability of the total count value.</span></span> <span data-ttu-id="524d1-141">Значение **точности** в диапазоне от `0.0` до `1.0` где `0.0` означает, что командлет не может подсчитать объекты, `1.0` означает, что счетчик является точным, а значение между и указывает на более `0.0` `1.0` надежную оценку.</span><span class="sxs-lookup"><span data-stu-id="524d1-141">The value of **Accuracy** ranges from `0.0` to `1.0` where `0.0` means that the cmdlet couldn't count the objects, `1.0` means that the count is exact, and a value between `0.0` and `1.0` indicates an increasingly reliable estimate.</span></span>

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

### <span data-ttu-id="524d1-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="524d1-142">-LiteralPath</span></span>

<span data-ttu-id="524d1-143">Указывает путь к XML-файлам.</span><span class="sxs-lookup"><span data-stu-id="524d1-143">Specifies the path to the XML files.</span></span> <span data-ttu-id="524d1-144">В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="524d1-144">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="524d1-145">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="524d1-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="524d1-146">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="524d1-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="524d1-147">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="524d1-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="524d1-148">-Path</span><span class="sxs-lookup"><span data-stu-id="524d1-148">-Path</span></span>

<span data-ttu-id="524d1-149">Указывает путь к XML-файлам.</span><span class="sxs-lookup"><span data-stu-id="524d1-149">Specifies the path to the XML files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="524d1-150">-Skip</span><span class="sxs-lookup"><span data-stu-id="524d1-150">-Skip</span></span>

<span data-ttu-id="524d1-151">Игнорирует указанное количество объектов, а затем получает оставшиеся объекты.</span><span class="sxs-lookup"><span data-stu-id="524d1-151">Ignores the specified number of objects and then gets the remaining objects.</span></span> <span data-ttu-id="524d1-152">Введите количество объектов, которые необходимо пропустить.</span><span class="sxs-lookup"><span data-stu-id="524d1-152">Enter the number of objects to skip.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="524d1-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="524d1-153">CommonParameters</span></span>

<span data-ttu-id="524d1-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="524d1-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="524d1-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="524d1-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="524d1-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="524d1-156">INPUTS</span></span>

### <span data-ttu-id="524d1-157">System.String</span><span class="sxs-lookup"><span data-stu-id="524d1-157">System.String</span></span>

<span data-ttu-id="524d1-158">Можно выполнить конвейерную строку, содержащую путь к `Import-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="524d1-158">You can pipeline a string that contains a path to `Import-Clixml`.</span></span>

## <span data-ttu-id="524d1-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="524d1-159">OUTPUTS</span></span>

### <span data-ttu-id="524d1-160">PSObject</span><span class="sxs-lookup"><span data-stu-id="524d1-160">PSObject</span></span>

<span data-ttu-id="524d1-161">`Import-Clixml` Возвращает объекты, которые были десериализованы из хранимых XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="524d1-161">`Import-Clixml` returns objects that were deserialized from the stored XML files.</span></span>

## <span data-ttu-id="524d1-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="524d1-162">NOTES</span></span>

<span data-ttu-id="524d1-163">При указании нескольких значений параметра разделяйте их запятыми.</span><span class="sxs-lookup"><span data-stu-id="524d1-163">When specifying multiple values for a parameter, use commas to separate the values.</span></span> <span data-ttu-id="524d1-164">Например, `<parameter-name> <value1>, <value2>`.</span><span class="sxs-lookup"><span data-stu-id="524d1-164">For example, `<parameter-name> <value1>, <value2>`.</span></span>

## <span data-ttu-id="524d1-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="524d1-165">RELATED LINKS</span></span>

[<span data-ttu-id="524d1-166">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="524d1-166">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="524d1-167">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="524d1-167">Introducing XML Serialization</span></span>](/dotnet/standard/serialization/introducing-xml-serialization)

[<span data-ttu-id="524d1-168">Join-Path</span><span class="sxs-lookup"><span data-stu-id="524d1-168">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

<span data-ttu-id="524d1-169">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk) (Безопасное хранение учетных данных на диске)</span><span class="sxs-lookup"><span data-stu-id="524d1-169">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)</span></span>

<span data-ttu-id="524d1-170">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/) (Передача учетных данных в устаревшие системы с помощью PowerShell)</span><span class="sxs-lookup"><span data-stu-id="524d1-170">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)</span></span>
