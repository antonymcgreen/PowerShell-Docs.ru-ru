---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: b12ca6bda03c1eb3834916bf9bfce43ecc3a70fb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226809"
---
# <span data-ttu-id="05f1d-103">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-103">Set-ItemProperty</span></span>

## <span data-ttu-id="05f1d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="05f1d-104">SYNOPSIS</span></span>
<span data-ttu-id="05f1d-105">Создает или изменяет значение свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="05f1d-105">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="05f1d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="05f1d-106">SYNTAX</span></span>

### <span data-ttu-id="05f1d-107">Пропертивалуепассет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="05f1d-107">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="05f1d-108">пропертипсобжектпассет</span><span class="sxs-lookup"><span data-stu-id="05f1d-108">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="05f1d-109">пропертивалуелитералпассет</span><span class="sxs-lookup"><span data-stu-id="05f1d-109">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="05f1d-110">пропертипсобжектлитералпассет</span><span class="sxs-lookup"><span data-stu-id="05f1d-110">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="05f1d-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="05f1d-111">DESCRIPTION</span></span>

<span data-ttu-id="05f1d-112">`Set-ItemProperty`Командлет изменяет значение свойства указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="05f1d-112">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span>
<span data-ttu-id="05f1d-113">Его можно использовать для установки и изменения свойств элементов.</span><span class="sxs-lookup"><span data-stu-id="05f1d-113">You can use the cmdlet to establish or change the properties of items.</span></span>
<span data-ttu-id="05f1d-114">Например, можно использовать `Set-ItemProperty` для установки значения свойства **IsReadOnly** объекта файла в значение `$True` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-114">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="05f1d-115">Также используется `Set-ItemProperty` для создания и изменения значений и данных реестра.</span><span class="sxs-lookup"><span data-stu-id="05f1d-115">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="05f1d-116">Например, с его помощью можно добавить в раздел реестра новую запись и установить или изменить ее значение.</span><span class="sxs-lookup"><span data-stu-id="05f1d-116">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="05f1d-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="05f1d-117">EXAMPLES</span></span>

### <span data-ttu-id="05f1d-118">Пример 1. Задание свойства файла</span><span class="sxs-lookup"><span data-stu-id="05f1d-118">Example 1: Set a property of a file</span></span>

<span data-ttu-id="05f1d-119">Эта команда задает для свойства **IsReadOnly** файла "final.doc" значение "true".</span><span class="sxs-lookup"><span data-stu-id="05f1d-119">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span>
<span data-ttu-id="05f1d-120">Он использует **путь** для указания файла, **имя** для указания имени свойства, а параметр **value** — для указания нового значения.</span><span class="sxs-lookup"><span data-stu-id="05f1d-120">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="05f1d-121">Файл является объектом **System. IO. FileInfo** , а свойство **IsReadOnly** — только одним из его свойств.</span><span class="sxs-lookup"><span data-stu-id="05f1d-121">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="05f1d-122">Чтобы просмотреть все свойства, введите `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-122">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property`.</span></span>

<span data-ttu-id="05f1d-123">`$true`Автоматическая переменная представляет значение "true".</span><span class="sxs-lookup"><span data-stu-id="05f1d-123">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="05f1d-124">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-124">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="05f1d-125">Пример 2. Создание записи и значения реестра</span><span class="sxs-lookup"><span data-stu-id="05f1d-125">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="05f1d-126">В этом примере показано, как использовать `Set-ItemProperty` для создания новой записи реестра и для назначения значения записи.</span><span class="sxs-lookup"><span data-stu-id="05f1d-126">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="05f1d-127">Он создает запись "NoOfEmployees" в ключе "Контосокомпани" в `HKLM\Software` разделе Key и присваивает ей значение 823.</span><span class="sxs-lookup"><span data-stu-id="05f1d-127">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in `HKLM\Software` key and sets its value to 823.</span></span>

<span data-ttu-id="05f1d-128">Поскольку записи реестра считаются свойствами разделов реестра, которые являются элементами, используются `Set-ItemProperty` для создания записей реестра, а также для установки и изменения их значений.</span><span class="sxs-lookup"><span data-stu-id="05f1d-128">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

<span data-ttu-id="05f1d-129">Первая команда создает запись реестра.</span><span class="sxs-lookup"><span data-stu-id="05f1d-129">The first command creates the registry entry.</span></span>
<span data-ttu-id="05f1d-130">В нем используется **путь** для указания пути к `HKLM:` диску и ключа "софтваре\микомпани".</span><span class="sxs-lookup"><span data-stu-id="05f1d-130">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="05f1d-131">Команда использует **имя** , чтобы указать имя и **значение** записи для указания значения.</span><span class="sxs-lookup"><span data-stu-id="05f1d-131">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="05f1d-132">Вторая команда использует `Get-ItemProperty` командлет для просмотра новой записи реестра.</span><span class="sxs-lookup"><span data-stu-id="05f1d-132">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>
<span data-ttu-id="05f1d-133">Если используются `Get-Item` `Get-ChildItem` командлеты или, записи не отображаются, так как они являются свойствами ключа, а не элементами или дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="05f1d-133">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="05f1d-134">Третья команда изменяет значение записи **NoOfEmployees** на 824.</span><span class="sxs-lookup"><span data-stu-id="05f1d-134">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="05f1d-135">Можно также использовать `New-ItemProperty` командлет для создания записи реестра и ее значения, а затем использовать `Set-ItemProperty` для изменения значения.</span><span class="sxs-lookup"><span data-stu-id="05f1d-135">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="05f1d-136">Для получения дополнительных сведений о `HKLM:` диске введите `Get-Help Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-136">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="05f1d-137">Для получения дополнительных сведений об управлении реестром с помощью PowerShell введите `Get-Help Registry` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-137">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

### <span data-ttu-id="05f1d-138">Пример 3. изменение элемента с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="05f1d-138">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="05f1d-139">Эти команды показывают, как использовать оператор конвейера ( `|` ) для отправки элемента в `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-139">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="05f1d-140">Первая часть команды использует `Get-ChildItem` для получения объекта, представляющего файл "Weekly.txt".</span><span class="sxs-lookup"><span data-stu-id="05f1d-140">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span> <span data-ttu-id="05f1d-141">Команда использует оператор конвейера для отправки объекта File в `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-141">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="05f1d-142">`Set-ItemProperty`Команда использует параметры **Name** и **value** для указания свойства и его нового значения.</span><span class="sxs-lookup"><span data-stu-id="05f1d-142">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="05f1d-143">Эта команда эквивалентна использованию параметра **InputObject** для указания объекта, который `Get-ChildItem` получает.</span><span class="sxs-lookup"><span data-stu-id="05f1d-143">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="05f1d-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="05f1d-144">PARAMETERS</span></span>

### <span data-ttu-id="05f1d-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="05f1d-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="05f1d-146">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05f1d-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="05f1d-147">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="05f1d-148">-Exclude</span><span class="sxs-lookup"><span data-stu-id="05f1d-148">-Exclude</span></span>

<span data-ttu-id="05f1d-149">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="05f1d-149">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="05f1d-150">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-150">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="05f1d-151">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-151">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="05f1d-152">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05f1d-152">Wildcard characters are permitted.</span></span> <span data-ttu-id="05f1d-153">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="05f1d-153">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="05f1d-154">-Filter</span><span class="sxs-lookup"><span data-stu-id="05f1d-154">-Filter</span></span>

<span data-ttu-id="05f1d-155">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="05f1d-155">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="05f1d-156">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="05f1d-156">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="05f1d-157">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-157">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="05f1d-158">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="05f1d-158">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="05f1d-159">-Force</span><span class="sxs-lookup"><span data-stu-id="05f1d-159">-Force</span></span>

<span data-ttu-id="05f1d-160">Заставляет командлет задать свойство для элементов, к которым пользователь не может получить доступ иным образом.</span><span class="sxs-lookup"><span data-stu-id="05f1d-160">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="05f1d-161">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="05f1d-161">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="05f1d-162">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-162">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="05f1d-163">-Include</span><span class="sxs-lookup"><span data-stu-id="05f1d-163">-Include</span></span>

<span data-ttu-id="05f1d-164">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="05f1d-164">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="05f1d-165">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-165">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="05f1d-166">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-166">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="05f1d-167">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05f1d-167">Wildcard characters are permitted.</span></span> <span data-ttu-id="05f1d-168">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="05f1d-168">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="05f1d-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="05f1d-169">-InputObject</span></span>

<span data-ttu-id="05f1d-170">Указывает объект, содержащий свойства, которые изменяется этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="05f1d-170">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="05f1d-171">Введите переменную, содержащую объект, либо команду, которая его возвращают.</span><span class="sxs-lookup"><span data-stu-id="05f1d-171">Enter a variable that contains the object or a command that gets the object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="05f1d-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="05f1d-172">-LiteralPath</span></span>

<span data-ttu-id="05f1d-173">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="05f1d-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="05f1d-174">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="05f1d-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="05f1d-175">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="05f1d-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="05f1d-176">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="05f1d-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="05f1d-177">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="05f1d-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="05f1d-178">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyPSObjectLiteralPathSet, propertyValueLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="05f1d-179">-Name</span><span class="sxs-lookup"><span data-stu-id="05f1d-179">-Name</span></span>

<span data-ttu-id="05f1d-180">Задает имя свойства.</span><span class="sxs-lookup"><span data-stu-id="05f1d-180">Specifies the name of the property.</span></span>

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="05f1d-181">-PassThru</span><span class="sxs-lookup"><span data-stu-id="05f1d-181">-PassThru</span></span>

<span data-ttu-id="05f1d-182">Возвращает объект, представляющий свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="05f1d-182">Returns an object that represents the item property.</span></span>
<span data-ttu-id="05f1d-183">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="05f1d-183">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="05f1d-184">-Path</span><span class="sxs-lookup"><span data-stu-id="05f1d-184">-Path</span></span>

<span data-ttu-id="05f1d-185">Указывает путь к элементам с изменяемым свойством.</span><span class="sxs-lookup"><span data-stu-id="05f1d-185">Specifies the path of the items with the property to modify.</span></span>
<span data-ttu-id="05f1d-186">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="05f1d-186">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="05f1d-187">-Type</span><span class="sxs-lookup"><span data-stu-id="05f1d-187">-Type</span></span>

<span data-ttu-id="05f1d-188">**Тип** — это динамический параметр, который поставщик реестра добавляет к `Set-ItemProperty` командлету.</span><span class="sxs-lookup"><span data-stu-id="05f1d-188">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="05f1d-189">Этот параметр работает только в дисках реестра.</span><span class="sxs-lookup"><span data-stu-id="05f1d-189">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="05f1d-190">Указывает тип свойства, добавляемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="05f1d-190">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="05f1d-191">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="05f1d-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="05f1d-192">**Строка** : указывает строку, завершающуюся нулем.</span><span class="sxs-lookup"><span data-stu-id="05f1d-192">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="05f1d-193">Эквивалентно **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-193">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="05f1d-194">**Експандстринг** : указывает строку, завершающуюся нулем, которая содержит нерасширенные ссылки на переменные среды, развернутые при извлечении значения.</span><span class="sxs-lookup"><span data-stu-id="05f1d-194">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="05f1d-195">Эквивалентно **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-195">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="05f1d-196">**Двоичный** : Определяет двоичные данные в любой форме.</span><span class="sxs-lookup"><span data-stu-id="05f1d-196">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="05f1d-197">Эквивалентно **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-197">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="05f1d-198">**DWORD** : задает 32-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="05f1d-198">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="05f1d-199">Эквивалентно **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-199">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="05f1d-200">**Многострочная** : указывает массив строк, заканчивающихся нулем, заканчивающихся двумя символами NULL.</span><span class="sxs-lookup"><span data-stu-id="05f1d-200">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="05f1d-201">Эквивалентно **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-201">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="05f1d-202">**QWORD** : задает 64-разрядное двоичное число.</span><span class="sxs-lookup"><span data-stu-id="05f1d-202">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="05f1d-203">Эквивалентно **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-203">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="05f1d-204">**Неизвестно** : указывает неподдерживаемый тип данных реестра, например **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="05f1d-204">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="05f1d-205">-Value</span><span class="sxs-lookup"><span data-stu-id="05f1d-205">-Value</span></span>

<span data-ttu-id="05f1d-206">Задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="05f1d-206">Specifies the value of the property.</span></span>

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="05f1d-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="05f1d-207">-Confirm</span></span>

<span data-ttu-id="05f1d-208">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="05f1d-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="05f1d-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="05f1d-209">-WhatIf</span></span>

<span data-ttu-id="05f1d-210">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="05f1d-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="05f1d-211">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="05f1d-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="05f1d-212">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="05f1d-212">CommonParameters</span></span>

<span data-ttu-id="05f1d-213">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="05f1d-213">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="05f1d-214">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-214">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="05f1d-215">Входные данные</span><span class="sxs-lookup"><span data-stu-id="05f1d-215">INPUTS</span></span>

### <span data-ttu-id="05f1d-216">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="05f1d-216">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="05f1d-217">Вы можете передать объекты в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="05f1d-217">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="05f1d-218">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="05f1d-218">OUTPUTS</span></span>

### <span data-ttu-id="05f1d-219">Нет, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="05f1d-219">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="05f1d-220">Этот командлет создает объект **PSCustomObject** , представляющий измененный элемент, и его новое значение, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="05f1d-220">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="05f1d-221">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="05f1d-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="05f1d-222">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="05f1d-222">NOTES</span></span>

<span data-ttu-id="05f1d-223">`Set-ItemProperty` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="05f1d-223">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="05f1d-224">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="05f1d-224">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="05f1d-225">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="05f1d-225">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="05f1d-226">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="05f1d-226">RELATED LINKS</span></span>

[<span data-ttu-id="05f1d-227">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-227">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="05f1d-228">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-228">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="05f1d-229">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-229">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="05f1d-230">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-230">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="05f1d-231">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-231">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="05f1d-232">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-232">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="05f1d-233">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="05f1d-233">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="05f1d-234">about_Providers</span><span class="sxs-lookup"><span data-stu-id="05f1d-234">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
