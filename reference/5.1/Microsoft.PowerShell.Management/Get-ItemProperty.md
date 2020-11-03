---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228374"
---
# <span data-ttu-id="4008a-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-103">Get-ItemProperty</span></span>

## <span data-ttu-id="4008a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4008a-104">SYNOPSIS</span></span>
<span data-ttu-id="4008a-105">Получает свойства указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="4008a-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="4008a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4008a-106">SYNTAX</span></span>

### <span data-ttu-id="4008a-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4008a-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="4008a-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4008a-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="4008a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4008a-109">DESCRIPTION</span></span>

<span data-ttu-id="4008a-110">`Get-ItemProperty`Командлет возвращает свойства указанных элементов.</span><span class="sxs-lookup"><span data-stu-id="4008a-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="4008a-111">Например, с помощью этого командлета можно получить значение свойства LastAccessTime объекта File.</span><span class="sxs-lookup"><span data-stu-id="4008a-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span>
<span data-ttu-id="4008a-112">Этот командлет также можно использовать для просмотра записей реестра и их значений.</span><span class="sxs-lookup"><span data-stu-id="4008a-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="4008a-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="4008a-113">EXAMPLES</span></span>

### <span data-ttu-id="4008a-114">Пример 1. Получение сведений о конкретном каталоге</span><span class="sxs-lookup"><span data-stu-id="4008a-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="4008a-115">Эта команда возвращает сведения о каталоге C:\Windows.</span><span class="sxs-lookup"><span data-stu-id="4008a-115">This command gets information about the "C:\Windows" directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="4008a-116">Пример 2. получение свойств указанного файла</span><span class="sxs-lookup"><span data-stu-id="4008a-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="4008a-117">Эта команда возвращает свойства файла "C:\Test\Weather.xls".</span><span class="sxs-lookup"><span data-stu-id="4008a-117">This command gets the properties of the "C:\Test\Weather.xls" file.</span></span>
<span data-ttu-id="4008a-118">Результат передается `Format-List` командлету для вывода выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="4008a-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="4008a-119">Пример 3. Отображение имени значения и данных записей реестра в подразделе реестра</span><span class="sxs-lookup"><span data-stu-id="4008a-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="4008a-120">Эта команда отображает имя значения и данные каждой из записей реестра, содержащихся в подразделе реестра CurrentVersion.</span><span class="sxs-lookup"><span data-stu-id="4008a-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="4008a-121">Обратите внимание, что команда требует наличия диска PowerShell с именем `HKLM:` , сопоставленного с кустом реестра "HKEY_LOCAL_MACHINE".</span><span class="sxs-lookup"><span data-stu-id="4008a-121">Note that the command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
<span data-ttu-id="4008a-122">Диск с таким именем и сопоставлением доступен в PowerShell по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4008a-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
<span data-ttu-id="4008a-123">Путь к указанному подразделу реестра может быть задан и другим способом. Необходимо ввести путь, начиная с имени поставщика и двоеточия, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="4008a-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>

<span data-ttu-id="4008a-124">"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="4008a-124">"Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### <span data-ttu-id="4008a-125">Пример 4. Получение имени значения и данных записи реестра в подразделе реестра</span><span class="sxs-lookup"><span data-stu-id="4008a-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="4008a-126">Эта команда возвращает имя значения и данные записи реестра "ProgramFilesDir" в подразделе реестра "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="4008a-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="4008a-127">Команда использует параметр **path** для указания подраздела, а параметр Name — для указания имени значения записи.</span><span class="sxs-lookup"><span data-stu-id="4008a-127">The command uses the **Path** parameter to specify the subkey and the Name parameter to specify the value name of the entry.</span></span>

<span data-ttu-id="4008a-128">В команде используется символ обратного или грависом ( \` ), знак продолжения PowerShell, чтобы продолжить выполнение команды во второй строке.</span><span class="sxs-lookup"><span data-stu-id="4008a-128">The command uses a back tick or grave accent (\`), the PowerShell continuation character, to continue the command on the second line.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="4008a-129">Пример 5. Получение имен значений и данных записей реестра в разделе реестра</span><span class="sxs-lookup"><span data-stu-id="4008a-129">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="4008a-130">Эта команда возвращает имена значений и данные записей реестра в разделе реестра "PowerShellEngine".</span><span class="sxs-lookup"><span data-stu-id="4008a-130">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span>
<span data-ttu-id="4008a-131">Результаты отображаются в следующем примере вывода.</span><span class="sxs-lookup"><span data-stu-id="4008a-131">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### <span data-ttu-id="4008a-132">Пример 6. получение, форматирование и отображение результатов значений и данных реестра</span><span class="sxs-lookup"><span data-stu-id="4008a-132">Example 6: Get, format, and display the results of registry values and data</span></span>

<span data-ttu-id="4008a-133">В этом примере показано, как отформатировать выходные данные `Get-ItemProperty` команды в списке, чтобы упростить просмотр значений и данных реестра, а также упростить их интерпретацию.</span><span class="sxs-lookup"><span data-stu-id="4008a-133">This example shows how to format the output of a `Get-ItemProperty` command in a list to make it easy to see the registry values and data and to make it easy to interpret the results.</span></span>

<span data-ttu-id="4008a-134">Первая команда использует `Get-ItemProperty` командлет для получения записей реестра в подразделе **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="4008a-134">The first command uses the `Get-ItemProperty` cmdlet to get the registry entries in the **Microsoft.PowerShell** subkey.</span></span>
<span data-ttu-id="4008a-135">В этом подразделе хранятся параметры оболочки по умолчанию для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4008a-135">This subkey stores options for the default shell for PowerShell.</span></span>
<span data-ttu-id="4008a-136">Результаты отображаются в следующем примере вывода.</span><span class="sxs-lookup"><span data-stu-id="4008a-136">The results are shown in the following sample output.</span></span>

<span data-ttu-id="4008a-137">Выходные данные показывают наличие двух записей реестра: Path и ExecutionPolicy.</span><span class="sxs-lookup"><span data-stu-id="4008a-137">The output shows that there are two registry entries, "Path" and "ExecutionPolicy".</span></span>
<span data-ttu-id="4008a-138">Если раздел реестра содержит меньше пяти записей, его содержимое по умолчанию отображается в виде таблицы, однако, нередко просматривать записи удобнее в виде списка.</span><span class="sxs-lookup"><span data-stu-id="4008a-138">When a registry key contains fewer than five entries, by default it is displayed in a table, but it is often easier to view in a list.</span></span>

<span data-ttu-id="4008a-139">Вторая команда использует ту же `Get-ItemProperty` команду.</span><span class="sxs-lookup"><span data-stu-id="4008a-139">The second command uses the same `Get-ItemProperty` command.</span></span>
<span data-ttu-id="4008a-140">Однако на этот раз команда использует оператор конвейера ( `|` ) для отправки результатов команды в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="4008a-140">However, this time, the command uses a pipeline operator (`|`) to send the results of the command to the `Format-List` cmdlet.</span></span>
<span data-ttu-id="4008a-141">`Format-List`Команда использует параметр Property со значением "\*" (все) для вывода всех свойств объектов в списке.</span><span class="sxs-lookup"><span data-stu-id="4008a-141">The `Format-List` command uses the Property parameter with a value of '\*' (all) to display all of the properties of the objects in a list.</span></span>
<span data-ttu-id="4008a-142">Результаты отображаются в следующем примере вывода.</span><span class="sxs-lookup"><span data-stu-id="4008a-142">The results are shown in the following sample output.</span></span>

<span data-ttu-id="4008a-143">В результате отображаются записи реестра Path и ExecutionPolicy, а также несколько менее знакомых свойств объекта раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="4008a-143">The resulting display shows the "Path" and "ExecutionPolicy" registry entries, along with several less familiar properties of the registry key object.</span></span>
<span data-ttu-id="4008a-144">Другие свойства с префиксом PS являются свойствами пользовательских объектов PowerShell, таких как объекты, представляющие разделы реестра.</span><span class="sxs-lookup"><span data-stu-id="4008a-144">The other properties, prefixed with PS, are properties of PowerShell custom objects, such as the objects that represent the registry keys.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## <span data-ttu-id="4008a-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4008a-145">PARAMETERS</span></span>

### <span data-ttu-id="4008a-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="4008a-146">-Credential</span></span>

<span data-ttu-id="4008a-147">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="4008a-147">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="4008a-148">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="4008a-148">The default is the current user.</span></span>

<span data-ttu-id="4008a-149">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="4008a-149">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="4008a-150">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="4008a-150">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="4008a-151">Этот параметр не поддерживается поставщиками, которые устанавливаются вместе с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4008a-151">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4008a-152">-Exclude</span><span class="sxs-lookup"><span data-stu-id="4008a-152">-Exclude</span></span>

<span data-ttu-id="4008a-153">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="4008a-153">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="4008a-154">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="4008a-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="4008a-155">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="4008a-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="4008a-156">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4008a-156">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4008a-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="4008a-157">-Filter</span></span>

<span data-ttu-id="4008a-158">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="4008a-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="4008a-159">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="4008a-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="4008a-160">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="4008a-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="4008a-161">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="4008a-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="4008a-162">-Include</span><span class="sxs-lookup"><span data-stu-id="4008a-162">-Include</span></span>

<span data-ttu-id="4008a-163">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="4008a-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="4008a-164">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="4008a-164">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="4008a-165">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="4008a-165">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="4008a-166">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4008a-166">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4008a-167">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4008a-167">-LiteralPath</span></span>

<span data-ttu-id="4008a-168">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="4008a-168">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="4008a-169">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="4008a-169">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="4008a-170">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="4008a-170">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="4008a-171">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4008a-171">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="4008a-172">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="4008a-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="4008a-173">-Name</span><span class="sxs-lookup"><span data-stu-id="4008a-173">-Name</span></span>

<span data-ttu-id="4008a-174">Указывает имена свойств, которые нужно извлечь.</span><span class="sxs-lookup"><span data-stu-id="4008a-174">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4008a-175">-Path</span><span class="sxs-lookup"><span data-stu-id="4008a-175">-Path</span></span>

<span data-ttu-id="4008a-176">Указывает путь к элементам.</span><span class="sxs-lookup"><span data-stu-id="4008a-176">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4008a-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="4008a-177">-UseTransaction</span></span>

<span data-ttu-id="4008a-178">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="4008a-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="4008a-179">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="4008a-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="4008a-180">Для получения дополнительных сведений см. фрагмент кода ниже.</span><span class="sxs-lookup"><span data-stu-id="4008a-180">For more information, see Includes the command in the active transaction.</span></span>
<span data-ttu-id="4008a-181">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="4008a-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="4008a-182">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="4008a-182">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="4008a-183">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4008a-183">CommonParameters</span></span>

<span data-ttu-id="4008a-184">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="4008a-184">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4008a-185">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4008a-185">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4008a-186">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4008a-186">INPUTS</span></span>

### <span data-ttu-id="4008a-187">System.String</span><span class="sxs-lookup"><span data-stu-id="4008a-187">System.String</span></span>

<span data-ttu-id="4008a-188">Можно передать строку, содержащую путь, в `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="4008a-188">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="4008a-189">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4008a-189">OUTPUTS</span></span>

### <span data-ttu-id="4008a-190">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="4008a-190">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="4008a-191">`Get-ItemProperty` Возвращает объект для каждого свойства элемента, которое он получает.</span><span class="sxs-lookup"><span data-stu-id="4008a-191">`Get-ItemProperty` returns an object for each item property that it gets.</span></span>
<span data-ttu-id="4008a-192">Тип объекта зависит от извлекаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4008a-192">The object type depends on the object that is retrieved.</span></span>
<span data-ttu-id="4008a-193">Например в случае диска файловой системы командлет возвращает файл или папку.</span><span class="sxs-lookup"><span data-stu-id="4008a-193">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="4008a-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4008a-194">NOTES</span></span>

<span data-ttu-id="4008a-195">`Get-ItemProperty`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="4008a-195">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="4008a-196">Чтобы получить список поставщиков, доступных в вашем сеансе, введите " `Get-PSProvider` ".</span><span class="sxs-lookup"><span data-stu-id="4008a-196">To list the providers available in your session, type "`Get-PSProvider`".</span></span> <span data-ttu-id="4008a-197">Дополнительные сведения см. в разделе about_Providers.</span><span class="sxs-lookup"><span data-stu-id="4008a-197">For more information, see about_Providers.</span></span>

## <span data-ttu-id="4008a-198">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4008a-198">RELATED LINKS</span></span>

[<span data-ttu-id="4008a-199">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-199">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="4008a-200">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-200">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="4008a-201">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-201">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="4008a-202">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-202">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="4008a-203">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-203">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="4008a-204">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-204">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="4008a-205">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4008a-205">Set-ItemProperty</span></span>](Set-ItemProperty.md)
