---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 63f1df176bb2e3308a5fb66f19a6f94336a5d8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227242"
---
# <span data-ttu-id="80293-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-103">New-ItemProperty</span></span>

## <span data-ttu-id="80293-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="80293-104">SYNOPSIS</span></span>
<span data-ttu-id="80293-105">Создает новое свойство для элемента и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="80293-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="80293-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80293-106">SYNTAX</span></span>

### <span data-ttu-id="80293-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="80293-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80293-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="80293-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="80293-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80293-109">DESCRIPTION</span></span>

<span data-ttu-id="80293-110">`New-ItemProperty`Командлет создает новое свойство для указанного элемента и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="80293-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="80293-111">Как правило, этот командлет используется для создания новых значений реестра, так как значения реестра являются свойствами элемента раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="80293-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="80293-112">Этот командлет не добавляет свойства в объект.</span><span class="sxs-lookup"><span data-stu-id="80293-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="80293-113">Чтобы добавить свойство в экземпляр объекта, используйте `Add-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="80293-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="80293-114">Чтобы добавить свойство ко всем объектам определенного типа, измените Types.ps1XML-файл.</span><span class="sxs-lookup"><span data-stu-id="80293-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="80293-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="80293-115">EXAMPLES</span></span>

### <span data-ttu-id="80293-116">Пример 1. Добавление записи реестра</span><span class="sxs-lookup"><span data-stu-id="80293-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="80293-117">Эта команда добавляет новую запись реестра «NoOfEmployees» в раздел «MyCompany» раздела «HKLM: \ Software Hive».</span><span class="sxs-lookup"><span data-stu-id="80293-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="80293-118">Первая команда использует параметр **path** для указания пути к разделу реестра MyCompany.</span><span class="sxs-lookup"><span data-stu-id="80293-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="80293-119">Он использует параметр **Name** для указания имени записи, а параметр **value** — для указания его значения.</span><span class="sxs-lookup"><span data-stu-id="80293-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="80293-120">Вторая команда использует `Get-ItemProperty` командлет для просмотра новой записи реестра.</span><span class="sxs-lookup"><span data-stu-id="80293-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

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

### <span data-ttu-id="80293-121">Пример 2. Добавление записи реестра в раздел</span><span class="sxs-lookup"><span data-stu-id="80293-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="80293-122">Эта команда добавляет новую запись реестра в раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="80293-122">This command adds a new registry entry to a registry key.</span></span>
<span data-ttu-id="80293-123">Чтобы указать ключ, он использует оператор конвейера ( `|` ) для отправки объекта, представляющего ключ `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="80293-123">To specify the key, it uses a pipeline operator (`|`) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="80293-124">Первая часть команды использует `Get-Item` командлет для получения раздела реестра MyCompany.</span><span class="sxs-lookup"><span data-stu-id="80293-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span>
<span data-ttu-id="80293-125">Оператор конвейера отправляет результаты команды в `New-ItemProperty` , который добавляет новую запись реестра ("нуфлокатионс") и ее значение (3) к ключу "MyCompany".</span><span class="sxs-lookup"><span data-stu-id="80293-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="80293-126">Эта команда работает, так как функция привязки параметров в PowerShell связывает путь `RegistryKey` объекта, `Get-Item` возвращаемого с параметром **LiteralPath** `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="80293-126">This command works because the parameter-binding feature of PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="80293-127">Дополнительные сведения см. в разделе [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="80293-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="80293-128">Пример 3. Создание многострочного значения в реестре с помощью Here-String</span><span class="sxs-lookup"><span data-stu-id="80293-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="80293-129">В этом примере создается многострочное значение с помощью строки here.</span><span class="sxs-lookup"><span data-stu-id="80293-129">This example creates a MultiString value using a Here-String.</span></span>

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

### <span data-ttu-id="80293-130">Пример 4. Создание многострочного значения в реестре с помощью массива</span><span class="sxs-lookup"><span data-stu-id="80293-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="80293-131">В примере показано, как использовать массив значений для создания `MultiString` значения.</span><span class="sxs-lookup"><span data-stu-id="80293-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="80293-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80293-132">PARAMETERS</span></span>

### <span data-ttu-id="80293-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="80293-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="80293-134">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80293-134">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="80293-135">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="80293-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="80293-136">-Exclude</span><span class="sxs-lookup"><span data-stu-id="80293-136">-Exclude</span></span>

<span data-ttu-id="80293-137">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="80293-137">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="80293-138">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="80293-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="80293-139">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="80293-139">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="80293-140">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80293-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="80293-141">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="80293-141">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="80293-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="80293-142">-Filter</span></span>

<span data-ttu-id="80293-143">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="80293-143">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="80293-144">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="80293-144">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="80293-145">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="80293-145">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="80293-146">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="80293-146">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="80293-147">-Force</span><span class="sxs-lookup"><span data-stu-id="80293-147">-Force</span></span>

<span data-ttu-id="80293-148">Заставляет командлет создать свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="80293-148">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="80293-149">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="80293-149">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="80293-150">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80293-150">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="80293-151">-Include</span><span class="sxs-lookup"><span data-stu-id="80293-151">-Include</span></span>

<span data-ttu-id="80293-152">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="80293-152">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="80293-153">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="80293-153">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="80293-154">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="80293-154">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="80293-155">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80293-155">Wildcard characters are permitted.</span></span> <span data-ttu-id="80293-156">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="80293-156">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="80293-157">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="80293-157">-LiteralPath</span></span>

<span data-ttu-id="80293-158">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="80293-158">Specifies a path to one or more locations.</span></span> <span data-ttu-id="80293-159">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="80293-159">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="80293-160">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="80293-160">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="80293-161">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="80293-161">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="80293-162">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="80293-162">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="80293-163">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="80293-163">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="80293-164">-Name</span><span class="sxs-lookup"><span data-stu-id="80293-164">-Name</span></span>

<span data-ttu-id="80293-165">Задает имя для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="80293-165">Specifies a name for the new property.</span></span>
<span data-ttu-id="80293-166">Если свойство является записью реестра, этот параметр задает имя записи.</span><span class="sxs-lookup"><span data-stu-id="80293-166">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

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

### <span data-ttu-id="80293-167">-Path</span><span class="sxs-lookup"><span data-stu-id="80293-167">-Path</span></span>

<span data-ttu-id="80293-168">Указывает путь к элементу.</span><span class="sxs-lookup"><span data-stu-id="80293-168">Specifies the path of the item.</span></span>
<span data-ttu-id="80293-169">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80293-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="80293-170">Этот параметр определяет элемент, к которому этот командлет добавляет новое свойство.</span><span class="sxs-lookup"><span data-stu-id="80293-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

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

### <span data-ttu-id="80293-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="80293-171">-PropertyType</span></span>

<span data-ttu-id="80293-172">Указывает тип свойства, добавляемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="80293-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="80293-173">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="80293-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80293-174">**Строка** : указывает строку, завершающуюся нулем.</span><span class="sxs-lookup"><span data-stu-id="80293-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="80293-175">Эквивалентно **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="80293-175">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="80293-176">**Експандстринг** : указывает строку, завершающуюся нулем, которая содержит нерасширенные ссылки на переменные среды, развернутые при извлечении значения.</span><span class="sxs-lookup"><span data-stu-id="80293-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="80293-177">Эквивалентно **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="80293-177">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="80293-178">**Двоичный** : Определяет двоичные данные в любой форме.</span><span class="sxs-lookup"><span data-stu-id="80293-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="80293-179">Эквивалентно **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="80293-179">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="80293-180">**DWORD** : задает 32-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="80293-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="80293-181">Эквивалентно **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="80293-181">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="80293-182">**Многострочная** : указывает массив строк, заканчивающихся нулем, заканчивающихся двумя символами NULL.</span><span class="sxs-lookup"><span data-stu-id="80293-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="80293-183">Эквивалентно **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="80293-183">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="80293-184">**QWORD** : задает 64-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="80293-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="80293-185">Эквивалентно **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="80293-185">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="80293-186">**Неизвестно** : указывает неподдерживаемый тип данных реестра, например **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="80293-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

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

### <span data-ttu-id="80293-187">-Value</span><span class="sxs-lookup"><span data-stu-id="80293-187">-Value</span></span>

<span data-ttu-id="80293-188">Задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="80293-188">Specifies the property value.</span></span>
<span data-ttu-id="80293-189">Если свойство является записью реестра, этот параметр указывает значение записи.</span><span class="sxs-lookup"><span data-stu-id="80293-189">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

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

### <span data-ttu-id="80293-190">-Confirm</span><span class="sxs-lookup"><span data-stu-id="80293-190">-Confirm</span></span>

<span data-ttu-id="80293-191">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="80293-191">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="80293-192">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="80293-192">-WhatIf</span></span>

<span data-ttu-id="80293-193">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="80293-193">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="80293-194">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="80293-194">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="80293-195">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="80293-195">CommonParameters</span></span>

<span data-ttu-id="80293-196">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="80293-196">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="80293-197">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="80293-197">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="80293-198">Входные данные</span><span class="sxs-lookup"><span data-stu-id="80293-198">INPUTS</span></span>

### <span data-ttu-id="80293-199">Нет</span><span class="sxs-lookup"><span data-stu-id="80293-199">None</span></span>

<span data-ttu-id="80293-200">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="80293-200">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="80293-201">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="80293-201">OUTPUTS</span></span>

### <span data-ttu-id="80293-202">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="80293-202">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="80293-203">`New-ItemProperty` Возвращает пользовательский объект, содержащий новое свойство.</span><span class="sxs-lookup"><span data-stu-id="80293-203">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="80293-204">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="80293-204">NOTES</span></span>

<span data-ttu-id="80293-205">`New-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="80293-205">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="80293-206">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="80293-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="80293-207">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80293-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="80293-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="80293-208">RELATED LINKS</span></span>

[<span data-ttu-id="80293-209">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-209">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="80293-210">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-210">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="80293-211">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-211">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="80293-212">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-212">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="80293-213">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-213">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="80293-214">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-214">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="80293-215">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="80293-215">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="80293-216">about_Providers</span><span class="sxs-lookup"><span data-stu-id="80293-216">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
