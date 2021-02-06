---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 59b7ea7f675d72dd90d970306c60107bd3f1de87
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605525"
---
# <span data-ttu-id="2515e-102">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-102">New-ItemProperty</span></span>

## <span data-ttu-id="2515e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2515e-103">SYNOPSIS</span></span>
<span data-ttu-id="2515e-104">Создает новое свойство для элемента и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="2515e-104">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="2515e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2515e-105">SYNTAX</span></span>

### <span data-ttu-id="2515e-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2515e-106">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2515e-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2515e-107">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2515e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2515e-108">DESCRIPTION</span></span>

<span data-ttu-id="2515e-109">`New-ItemProperty`Командлет создает новое свойство для указанного элемента и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="2515e-109">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="2515e-110">Как правило, этот командлет используется для создания новых значений реестра, так как значения реестра являются свойствами элемента раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="2515e-110">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="2515e-111">Этот командлет не добавляет свойства в объект.</span><span class="sxs-lookup"><span data-stu-id="2515e-111">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="2515e-112">Чтобы добавить свойство в экземпляр объекта, используйте `Add-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="2515e-112">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="2515e-113">Чтобы добавить свойство ко всем объектам определенного типа, измените Types.ps1XML-файл.</span><span class="sxs-lookup"><span data-stu-id="2515e-113">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="2515e-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="2515e-114">EXAMPLES</span></span>

### <span data-ttu-id="2515e-115">Пример 1. Добавление записи реестра</span><span class="sxs-lookup"><span data-stu-id="2515e-115">Example 1: Add a registry entry</span></span>

<span data-ttu-id="2515e-116">Эта команда добавляет новую запись реестра «NoOfEmployees» в раздел «MyCompany» раздела «HKLM: \ Software Hive».</span><span class="sxs-lookup"><span data-stu-id="2515e-116">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="2515e-117">Первая команда использует параметр **path** для указания пути к разделу реестра MyCompany.</span><span class="sxs-lookup"><span data-stu-id="2515e-117">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="2515e-118">Он использует параметр **Name** для указания имени записи, а параметр **value** — для указания его значения.</span><span class="sxs-lookup"><span data-stu-id="2515e-118">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="2515e-119">Вторая команда использует `Get-ItemProperty` командлет для просмотра новой записи реестра.</span><span class="sxs-lookup"><span data-stu-id="2515e-119">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### <span data-ttu-id="2515e-120">Пример 2. Добавление записи реестра в раздел</span><span class="sxs-lookup"><span data-stu-id="2515e-120">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="2515e-121">Эта команда добавляет новую запись реестра в раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="2515e-121">This command adds a new registry entry to a registry key.</span></span>
<span data-ttu-id="2515e-122">Чтобы указать ключ, он использует оператор конвейера ( `|` ) для отправки объекта, представляющего ключ `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="2515e-122">To specify the key, it uses a pipeline operator (`|`) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="2515e-123">Первая часть команды использует `Get-Item` командлет для получения раздела реестра MyCompany.</span><span class="sxs-lookup"><span data-stu-id="2515e-123">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span>
<span data-ttu-id="2515e-124">Оператор конвейера отправляет результаты команды в `New-ItemProperty` , который добавляет новую запись реестра ("нуфлокатионс") и ее значение (3) к ключу "MyCompany".</span><span class="sxs-lookup"><span data-stu-id="2515e-124">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="2515e-125">Эта команда работает, так как функция привязки параметров в PowerShell связывает путь `RegistryKey` объекта, `Get-Item` возвращаемого с параметром **LiteralPath** `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="2515e-125">This command works because the parameter-binding feature of PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="2515e-126">Дополнительные сведения см. в разделе [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-126">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="2515e-127">Пример 3. Создание многострочного значения в реестре с помощью Here-String</span><span class="sxs-lookup"><span data-stu-id="2515e-127">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="2515e-128">В этом примере создается многострочное значение с помощью строки here.</span><span class="sxs-lookup"><span data-stu-id="2515e-128">This example creates a MultiString value using a Here-String.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### <span data-ttu-id="2515e-129">Пример 4. Создание многострочного значения в реестре с помощью массива</span><span class="sxs-lookup"><span data-stu-id="2515e-129">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="2515e-130">В примере показано, как использовать массив значений для создания `MultiString` значения.</span><span class="sxs-lookup"><span data-stu-id="2515e-130">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="2515e-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2515e-131">PARAMETERS</span></span>

### <span data-ttu-id="2515e-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="2515e-132">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="2515e-133">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2515e-133">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="2515e-134">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-134">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="2515e-135">-Exclude</span><span class="sxs-lookup"><span data-stu-id="2515e-135">-Exclude</span></span>

<span data-ttu-id="2515e-136">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="2515e-136">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="2515e-137">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="2515e-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2515e-138">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="2515e-138">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="2515e-139">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2515e-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="2515e-140">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="2515e-140">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="2515e-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="2515e-141">-Filter</span></span>

<span data-ttu-id="2515e-142">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="2515e-142">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="2515e-143">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="2515e-143">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="2515e-144">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-144">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="2515e-145">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="2515e-145">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="2515e-146">-Force</span><span class="sxs-lookup"><span data-stu-id="2515e-146">-Force</span></span>

<span data-ttu-id="2515e-147">Заставляет командлет создать свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2515e-147">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="2515e-148">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="2515e-148">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="2515e-149">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-149">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="2515e-150">-Include</span><span class="sxs-lookup"><span data-stu-id="2515e-150">-Include</span></span>

<span data-ttu-id="2515e-151">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="2515e-151">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="2515e-152">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="2515e-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2515e-153">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="2515e-153">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="2515e-154">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2515e-154">Wildcard characters are permitted.</span></span> <span data-ttu-id="2515e-155">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="2515e-155">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="2515e-156">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2515e-156">-LiteralPath</span></span>

<span data-ttu-id="2515e-157">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="2515e-157">Specifies a path to one or more locations.</span></span> <span data-ttu-id="2515e-158">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="2515e-158">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="2515e-159">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="2515e-159">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2515e-160">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="2515e-160">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2515e-161">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="2515e-161">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="2515e-162">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-162">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="2515e-163">-Name</span><span class="sxs-lookup"><span data-stu-id="2515e-163">-Name</span></span>

<span data-ttu-id="2515e-164">Задает имя для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="2515e-164">Specifies a name for the new property.</span></span>
<span data-ttu-id="2515e-165">Если свойство является записью реестра, этот параметр задает имя записи.</span><span class="sxs-lookup"><span data-stu-id="2515e-165">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2515e-166">-Path</span><span class="sxs-lookup"><span data-stu-id="2515e-166">-Path</span></span>

<span data-ttu-id="2515e-167">Указывает путь к элементу.</span><span class="sxs-lookup"><span data-stu-id="2515e-167">Specifies the path of the item.</span></span>
<span data-ttu-id="2515e-168">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2515e-168">Wildcard characters are permitted.</span></span>
<span data-ttu-id="2515e-169">Этот параметр определяет элемент, к которому этот командлет добавляет новое свойство.</span><span class="sxs-lookup"><span data-stu-id="2515e-169">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2515e-170">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="2515e-170">-PropertyType</span></span>

<span data-ttu-id="2515e-171">Указывает тип свойства, добавляемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="2515e-171">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="2515e-172">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2515e-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2515e-173">**Строка**: указывает строку, завершающуюся нулем.</span><span class="sxs-lookup"><span data-stu-id="2515e-173">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="2515e-174">Эквивалентно **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="2515e-174">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="2515e-175">**Експандстринг**: указывает строку, завершающуюся нулем, которая содержит нерасширенные ссылки на переменные среды, развернутые при извлечении значения.</span><span class="sxs-lookup"><span data-stu-id="2515e-175">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="2515e-176">Эквивалентно **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="2515e-176">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="2515e-177">**Двоичный**: Определяет двоичные данные в любой форме.</span><span class="sxs-lookup"><span data-stu-id="2515e-177">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="2515e-178">Эквивалентно **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="2515e-178">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="2515e-179">**DWORD**: задает 32-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="2515e-179">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="2515e-180">Эквивалентно **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="2515e-180">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="2515e-181">**Многострочная**: указывает массив строк, заканчивающихся нулем, заканчивающихся двумя символами NULL.</span><span class="sxs-lookup"><span data-stu-id="2515e-181">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="2515e-182">Эквивалентно **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="2515e-182">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="2515e-183">**QWORD**: задает 64-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="2515e-183">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="2515e-184">Эквивалентно **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="2515e-184">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="2515e-185">**Неизвестно**: указывает неподдерживаемый тип данных реестра, например **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="2515e-185">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2515e-186">-Value</span><span class="sxs-lookup"><span data-stu-id="2515e-186">-Value</span></span>

<span data-ttu-id="2515e-187">Задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="2515e-187">Specifies the property value.</span></span>
<span data-ttu-id="2515e-188">Если свойство является записью реестра, этот параметр указывает значение записи.</span><span class="sxs-lookup"><span data-stu-id="2515e-188">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2515e-189">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2515e-189">-Confirm</span></span>

<span data-ttu-id="2515e-190">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2515e-190">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2515e-191">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2515e-191">-WhatIf</span></span>

<span data-ttu-id="2515e-192">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2515e-192">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2515e-193">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2515e-193">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2515e-194">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2515e-194">CommonParameters</span></span>

<span data-ttu-id="2515e-195">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="2515e-195">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="2515e-196">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-196">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2515e-197">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2515e-197">INPUTS</span></span>

### <span data-ttu-id="2515e-198">None</span><span class="sxs-lookup"><span data-stu-id="2515e-198">None</span></span>

<span data-ttu-id="2515e-199">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="2515e-199">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2515e-200">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2515e-200">OUTPUTS</span></span>

### <span data-ttu-id="2515e-201">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="2515e-201">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="2515e-202">`New-ItemProperty` Возвращает пользовательский объект, содержащий новое свойство.</span><span class="sxs-lookup"><span data-stu-id="2515e-202">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="2515e-203">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2515e-203">NOTES</span></span>

<span data-ttu-id="2515e-204">`New-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="2515e-204">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="2515e-205">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="2515e-205">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="2515e-206">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2515e-206">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="2515e-207">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2515e-207">RELATED LINKS</span></span>

[<span data-ttu-id="2515e-208">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-208">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="2515e-209">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-209">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="2515e-210">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-210">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="2515e-211">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-211">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="2515e-212">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-212">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="2515e-213">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-213">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="2515e-214">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2515e-214">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="2515e-215">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2515e-215">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

