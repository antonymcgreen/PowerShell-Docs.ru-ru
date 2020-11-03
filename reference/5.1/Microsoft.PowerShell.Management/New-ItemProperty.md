---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227970"
---
# <span data-ttu-id="0a66e-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-103">New-ItemProperty</span></span>

## <span data-ttu-id="0a66e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0a66e-104">SYNOPSIS</span></span>
<span data-ttu-id="0a66e-105">Создает новое свойство для элемента и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="0a66e-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="0a66e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0a66e-106">SYNTAX</span></span>

### <span data-ttu-id="0a66e-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0a66e-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="0a66e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0a66e-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="0a66e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0a66e-109">DESCRIPTION</span></span>

<span data-ttu-id="0a66e-110">`New-ItemProperty`Командлет создает новое свойство для указанного элемента и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="0a66e-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="0a66e-111">Как правило, этот командлет используется для создания новых значений реестра, так как значения реестра являются свойствами элемента раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="0a66e-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="0a66e-112">Этот командлет не добавляет свойства в объект.</span><span class="sxs-lookup"><span data-stu-id="0a66e-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="0a66e-113">Чтобы добавить свойство в экземпляр объекта, используйте `Add-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="0a66e-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="0a66e-114">Чтобы добавить свойство ко всем объектам определенного типа, измените Types.ps1XML-файл.</span><span class="sxs-lookup"><span data-stu-id="0a66e-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="0a66e-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="0a66e-115">EXAMPLES</span></span>

### <span data-ttu-id="0a66e-116">Пример 1. Добавление записи реестра</span><span class="sxs-lookup"><span data-stu-id="0a66e-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="0a66e-117">Эта команда добавляет новую запись реестра «NoOfEmployees» в раздел «MyCompany» раздела «HKLM: \ Software Hive».</span><span class="sxs-lookup"><span data-stu-id="0a66e-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="0a66e-118">Первая команда использует параметр **path** для указания пути к разделу реестра MyCompany.</span><span class="sxs-lookup"><span data-stu-id="0a66e-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="0a66e-119">Он использует параметр **Name** для указания имени записи, а параметр **value** — для указания его значения.</span><span class="sxs-lookup"><span data-stu-id="0a66e-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="0a66e-120">Вторая команда использует `Get-ItemProperty` командлет для просмотра новой записи реестра.</span><span class="sxs-lookup"><span data-stu-id="0a66e-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

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

### <span data-ttu-id="0a66e-121">Пример 2. Добавление записи реестра в раздел</span><span class="sxs-lookup"><span data-stu-id="0a66e-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="0a66e-122">Эта команда добавляет новую запись реестра в раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="0a66e-122">This command adds a new registry entry to a registry key.</span></span> <span data-ttu-id="0a66e-123">Чтобы указать ключ, он использует оператор конвейера (|) для отправки объекта, представляющего ключ `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="0a66e-123">To specify the key, it uses a pipeline operator (|) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="0a66e-124">Первая часть команды использует `Get-Item` командлет для получения раздела реестра MyCompany.</span><span class="sxs-lookup"><span data-stu-id="0a66e-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span> <span data-ttu-id="0a66e-125">Оператор конвейера отправляет результаты команды в `New-ItemProperty` , который добавляет новую запись реестра ("нуфлокатионс") и ее значение (3) к ключу "MyCompany".</span><span class="sxs-lookup"><span data-stu-id="0a66e-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="0a66e-126">Эта команда работает, так как функция привязки параметров Windows PowerShell связывает путь `RegistryKey` объекта, `Get-Item` возвращаемого с параметром **LiteralPath** `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="0a66e-126">This command works because the parameter-binding feature of Windows PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="0a66e-127">Дополнительные сведения см. в разделе [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="0a66e-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="0a66e-128">Пример 3. Создание многострочного значения в реестре с помощью Here-String</span><span class="sxs-lookup"><span data-stu-id="0a66e-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="0a66e-129">В этом примере создается многострочное значение с помощью строки here.</span><span class="sxs-lookup"><span data-stu-id="0a66e-129">This example creates a MultiString value using a Here-String.</span></span>

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

### <span data-ttu-id="0a66e-130">Пример 4. Создание многострочного значения в реестре с помощью массива</span><span class="sxs-lookup"><span data-stu-id="0a66e-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="0a66e-131">В примере показано, как использовать массив значений для создания `MultiString` значения.</span><span class="sxs-lookup"><span data-stu-id="0a66e-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="0a66e-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0a66e-132">PARAMETERS</span></span>

### <span data-ttu-id="0a66e-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="0a66e-133">-Credential</span></span>

<span data-ttu-id="0a66e-134">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="0a66e-134">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0a66e-135">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="0a66e-135">The default is the current user.</span></span>

<span data-ttu-id="0a66e-136">Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="0a66e-136">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0a66e-137">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="0a66e-137">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="0a66e-138">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a66e-138">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0a66e-139">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="0a66e-139">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="0a66e-140">-Exclude</span><span class="sxs-lookup"><span data-stu-id="0a66e-140">-Exclude</span></span>

<span data-ttu-id="0a66e-141">Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="0a66e-141">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="0a66e-142">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-142">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="0a66e-143">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="0a66e-143">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="0a66e-144">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0a66e-144">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0a66e-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="0a66e-145">-Filter</span></span>

<span data-ttu-id="0a66e-146">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a66e-146">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="0a66e-147">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-147">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="0a66e-148">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a66e-148">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="0a66e-149">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="0a66e-149">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0a66e-150">-Force</span><span class="sxs-lookup"><span data-stu-id="0a66e-150">-Force</span></span>

<span data-ttu-id="0a66e-151">Заставляет командлет создать свойство объекта, доступ к которому в противном случае невозможен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a66e-151">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="0a66e-152">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="0a66e-152">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="0a66e-153">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0a66e-153">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="0a66e-154">-Include</span><span class="sxs-lookup"><span data-stu-id="0a66e-154">-Include</span></span>

<span data-ttu-id="0a66e-155">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="0a66e-155">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="0a66e-156">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-156">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="0a66e-157">Введите путь к элементу или шаблон, например. «\*.txt».</span><span class="sxs-lookup"><span data-stu-id="0a66e-157">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="0a66e-158">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0a66e-158">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0a66e-159">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0a66e-159">-LiteralPath</span></span>

<span data-ttu-id="0a66e-160">Указывает путь к текущему расположению свойства.</span><span class="sxs-lookup"><span data-stu-id="0a66e-160">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="0a66e-161">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="0a66e-161">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="0a66e-162">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="0a66e-162">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="0a66e-163">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="0a66e-163">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="0a66e-164">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="0a66e-164">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="0a66e-165">-Name</span><span class="sxs-lookup"><span data-stu-id="0a66e-165">-Name</span></span>

<span data-ttu-id="0a66e-166">Задает имя для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="0a66e-166">Specifies a name for the new property.</span></span>
<span data-ttu-id="0a66e-167">Если свойство является записью реестра, этот параметр задает имя записи.</span><span class="sxs-lookup"><span data-stu-id="0a66e-167">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

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

### <span data-ttu-id="0a66e-168">-Path</span><span class="sxs-lookup"><span data-stu-id="0a66e-168">-Path</span></span>

<span data-ttu-id="0a66e-169">Указывает путь к элементу.</span><span class="sxs-lookup"><span data-stu-id="0a66e-169">Specifies the path of the item.</span></span>
<span data-ttu-id="0a66e-170">Этот параметр определяет элемент, к которому этот командлет добавляет новое свойство.</span><span class="sxs-lookup"><span data-stu-id="0a66e-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0a66e-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="0a66e-171">-PropertyType</span></span>

<span data-ttu-id="0a66e-172">Указывает тип свойства, добавляемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="0a66e-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="0a66e-173">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0a66e-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0a66e-174">**Строка** : указывает строку, завершающуюся нулем.</span><span class="sxs-lookup"><span data-stu-id="0a66e-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="0a66e-175">Эквивалентно **REG_SZ** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="0a66e-176">**Експандстринг** : указывает строку, завершающуюся нулем, которая содержит нерасширенные ссылки на переменные среды, развернутые при извлечении значения.</span><span class="sxs-lookup"><span data-stu-id="0a66e-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="0a66e-177">Эквивалентно **REG_EXPAND_SZ** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="0a66e-178">**Двоичный** : Определяет двоичные данные в любой форме.</span><span class="sxs-lookup"><span data-stu-id="0a66e-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="0a66e-179">Эквивалентно **REG_BINARY** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="0a66e-180">**DWORD** : задает 32-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="0a66e-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="0a66e-181">Эквивалентно **REG_DWORD** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="0a66e-182">**Многострочная** : указывает массив строк, заканчивающихся нулем, заканчивающихся двумя символами NULL.</span><span class="sxs-lookup"><span data-stu-id="0a66e-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="0a66e-183">Эквивалентно **REG_MULTI_SZ** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="0a66e-184">**QWORD** : задает 64-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="0a66e-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="0a66e-185">Эквивалентно **REG_QWORD** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="0a66e-186">**Неизвестно** : указывает неподдерживаемый тип данных реестра, например **REG_RESOURCE_LIST** .</span><span class="sxs-lookup"><span data-stu-id="0a66e-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

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

### <span data-ttu-id="0a66e-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="0a66e-187">-UseTransaction</span></span>

<span data-ttu-id="0a66e-188">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0a66e-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="0a66e-189">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="0a66e-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="0a66e-190">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="0a66e-190">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="0a66e-191">-Value</span><span class="sxs-lookup"><span data-stu-id="0a66e-191">-Value</span></span>

<span data-ttu-id="0a66e-192">Задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="0a66e-192">Specifies the property value.</span></span>
<span data-ttu-id="0a66e-193">Если свойство является записью реестра, этот параметр указывает значение записи.</span><span class="sxs-lookup"><span data-stu-id="0a66e-193">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

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

### <span data-ttu-id="0a66e-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0a66e-194">-Confirm</span></span>

<span data-ttu-id="0a66e-195">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0a66e-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0a66e-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0a66e-196">-WhatIf</span></span>

<span data-ttu-id="0a66e-197">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0a66e-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0a66e-198">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0a66e-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0a66e-199">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0a66e-199">CommonParameters</span></span>

<span data-ttu-id="0a66e-200">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="0a66e-200">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0a66e-201">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0a66e-201">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0a66e-202">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0a66e-202">INPUTS</span></span>

### <span data-ttu-id="0a66e-203">Нет</span><span class="sxs-lookup"><span data-stu-id="0a66e-203">None</span></span>

<span data-ttu-id="0a66e-204">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="0a66e-204">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0a66e-205">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0a66e-205">OUTPUTS</span></span>

### <span data-ttu-id="0a66e-206">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="0a66e-206">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="0a66e-207">`New-ItemProperty` Возвращает пользовательский объект, содержащий новое свойство.</span><span class="sxs-lookup"><span data-stu-id="0a66e-207">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="0a66e-208">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0a66e-208">NOTES</span></span>

<span data-ttu-id="0a66e-209">`New-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0a66e-209">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0a66e-210">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="0a66e-210">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="0a66e-211">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0a66e-211">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0a66e-212">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0a66e-212">RELATED LINKS</span></span>

[<span data-ttu-id="0a66e-213">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-213">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="0a66e-214">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-214">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="0a66e-215">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-215">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="0a66e-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-216">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="0a66e-217">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-217">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="0a66e-218">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-218">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="0a66e-219">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0a66e-219">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="0a66e-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0a66e-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
