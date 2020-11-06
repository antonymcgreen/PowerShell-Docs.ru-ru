---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: 6b862ad6bada3035551d35d592183db5805b232f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227805"
---
# <span data-ttu-id="c05ce-103">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="c05ce-103">Get-Acl</span></span>

## <span data-ttu-id="c05ce-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c05ce-104">SYNOPSIS</span></span>
<span data-ttu-id="c05ce-105">Возвращает дескриптор безопасности для ресурса, например файла или раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="c05ce-105">Gets the security descriptor for a resource, such as a file or registry key.</span></span>

## <span data-ttu-id="c05ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c05ce-106">SYNTAX</span></span>

### <span data-ttu-id="c05ce-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c05ce-107">ByPath (Default)</span></span>

```
Get-Acl [[-Path] <String[]>] [-Audit] [-AllCentralAccessPolicies] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="c05ce-108">бинпутобжект</span><span class="sxs-lookup"><span data-stu-id="c05ce-108">ByInputObject</span></span>

```
Get-Acl -InputObject <PSObject> [-Audit] [-AllCentralAccessPolicies] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="c05ce-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="c05ce-109">ByLiteralPath</span></span>

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-AllCentralAccessPolicies] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="c05ce-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c05ce-110">DESCRIPTION</span></span>

<span data-ttu-id="c05ce-111">`Get-Acl`Командлет получает объекты, представляющие дескриптор безопасности файла или ресурса.</span><span class="sxs-lookup"><span data-stu-id="c05ce-111">The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="c05ce-112">Дескриптор безопасности содержит списки управления доступом (ACL) ресурса.</span><span class="sxs-lookup"><span data-stu-id="c05ce-112">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="c05ce-113">В списке ACL указаны разрешения пользователей и групп пользователей на доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c05ce-113">The ACL specifies the permissions that users and user groups have to access the resource.</span></span>

<span data-ttu-id="c05ce-114">Начиная с Windows PowerShell 3,0, параметр **InputObject** можно использовать `Get-Acl` для получения дескриптора безопасности объектов, которые не имеют пути.</span><span class="sxs-lookup"><span data-stu-id="c05ce-114">Beginning in Windows PowerShell 3.0, you can use the **InputObject** parameter of `Get-Acl` to get the security descriptor of objects that do not have a path.</span></span>

## <span data-ttu-id="c05ce-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="c05ce-115">EXAMPLES</span></span>

### <span data-ttu-id="c05ce-116">Пример 1. Получение списка ACL для папки</span><span class="sxs-lookup"><span data-stu-id="c05ce-116">Example 1- Get an ACL for a folder</span></span>

<span data-ttu-id="c05ce-117">В этом примере возвращается дескриптор безопасности `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c05ce-117">This example gets the security descriptor of the `C:\Windows` directory.</span></span>

```powershell
Get-Acl C:\Windows
```

### <span data-ttu-id="c05ce-118">Пример 2. Получение списка ACL для папки с помощью подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="c05ce-118">Example 2 - Get an ACL for a folder using wildcards</span></span>

<span data-ttu-id="c05ce-119">В этом примере выполняется получение пути PowerShell и SDDL для всех `.log` файлов в `C:\Windows` каталоге, имена которых начинаются с `s` .</span><span class="sxs-lookup"><span data-stu-id="c05ce-119">This example gets the PowerShell path and SDDL for all of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

<span data-ttu-id="c05ce-120">Команда использует `Get-Acl` командлет для получения объектов, представляющих дескрипторы безопасности каждого файла журнала.</span><span class="sxs-lookup"><span data-stu-id="c05ce-120">The command uses the `Get-Acl` cmdlet to get objects representing the security descriptors of each log file.</span></span> <span data-ttu-id="c05ce-121">Он использует оператор конвейера ( `|` ) для отправки результатов в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="c05ce-121">It uses a pipeline operator (`|`) to send the results to the `Format-List` cmdlet.</span></span> <span data-ttu-id="c05ce-122">Команда использует параметр **Property** параметра, `Format-List` чтобы отобразить только свойства **PSPath** и **SDDL** для каждого объекта дескриптора безопасности.</span><span class="sxs-lookup"><span data-stu-id="c05ce-122">The command uses the **Property** parameter of `Format-List` to display only the **PsPath** and **SDDL** properties of each security descriptor object.</span></span>

<span data-ttu-id="c05ce-123">Списки часто используются в PowerShell, так как длинные значения в таблицах усекаются.</span><span class="sxs-lookup"><span data-stu-id="c05ce-123">Lists are often used in PowerShell, because long values appear truncated in tables.</span></span>

<span data-ttu-id="c05ce-124">Значения **SDDL** важны для системных администраторов, так как они представляют собой простые текстовые строки, содержащие все данные дескриптора безопасности.</span><span class="sxs-lookup"><span data-stu-id="c05ce-124">The **SDDL** values are valuable to system administrators, because they are simple text strings that contain all of the information in the security descriptor.</span></span> <span data-ttu-id="c05ce-125">Их легко передавать и хранить, а также при необходимости анализировать.</span><span class="sxs-lookup"><span data-stu-id="c05ce-125">As such, they are easy to pass and store, and they can be parsed when needed.</span></span>

### <span data-ttu-id="c05ce-126">Пример 3. Получение списка записей аудита для ACL</span><span class="sxs-lookup"><span data-stu-id="c05ce-126">Example 3 - Get count of Audit entries for an ACL</span></span>

<span data-ttu-id="c05ce-127">Этот пример получает дескрипторы безопасности `.log` файлов в `C:\Windows` каталоге, имена которых начинаются с `s` .</span><span class="sxs-lookup"><span data-stu-id="c05ce-127">This example gets the security descriptors of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

<span data-ttu-id="c05ce-128">С помощью параметра **Audit** возвращаются записи аудита из списка SACL в дескрипторе безопасности.</span><span class="sxs-lookup"><span data-stu-id="c05ce-128">It uses the **Audit** parameter to get the audit records from the SACL in the security descriptor.</span></span>
<span data-ttu-id="c05ce-129">Затем он использует `ForEach-Object` командлет для подсчета количества записей аудита, связанных с каждым файлом.</span><span class="sxs-lookup"><span data-stu-id="c05ce-129">Then it uses the `ForEach-Object` cmdlet to count the number of audit records associated with each file.</span></span> <span data-ttu-id="c05ce-130">Результат представляет собой список соответствующих чисел.</span><span class="sxs-lookup"><span data-stu-id="c05ce-130">The result is a list of numbers representing the number of audit records for each log file.</span></span>

### <span data-ttu-id="c05ce-131">Пример 4. Получение списка ACL для раздела реестра</span><span class="sxs-lookup"><span data-stu-id="c05ce-131">Example 4 - Get an ACL for a registry key</span></span>

<span data-ttu-id="c05ce-132">В этом примере `Get-Acl` командлет используется для получения дескриптора безопасности подраздела элемента управления ( `HKLM:\SYSTEM\CurrentControlSet\Control` ) реестра.</span><span class="sxs-lookup"><span data-stu-id="c05ce-132">This example uses the `Get-Acl` cmdlet to get the security descriptor of the Control subkey (`HKLM:\SYSTEM\CurrentControlSet\Control`) of the registry.</span></span>

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

<span data-ttu-id="c05ce-133">Параметр **path** задает подраздел Control.</span><span class="sxs-lookup"><span data-stu-id="c05ce-133">The **Path** parameter specifies the Control subkey.</span></span> <span data-ttu-id="c05ce-134">Оператор конвейера ( `|` ) передает дескриптор безопасности, который `Get-Acl` получает `Format-List` команду, который форматирует свойства дескриптора безопасности в виде списка, чтобы их было легко читать.</span><span class="sxs-lookup"><span data-stu-id="c05ce-134">The pipeline operator (`|`) passes the security descriptor that `Get-Acl` gets to the `Format-List` command, which formats the properties of the security descriptor as a list so that they are easy to read.</span></span>

### <span data-ttu-id="c05ce-135">Пример 5. Получение списка ACL с помощью **InputObject**</span><span class="sxs-lookup"><span data-stu-id="c05ce-135">Example 5 - Get an ACL using **InputObject**</span></span>

<span data-ttu-id="c05ce-136">В этом примере параметр **InputObject** используется `Get-Acl` для получения дескриптора безопасности объекта подсистемы хранения.</span><span class="sxs-lookup"><span data-stu-id="c05ce-136">This example uses the **InputObject** parameter of `Get-Acl` to get the security descriptor of a storage subsystem object.</span></span>

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## <span data-ttu-id="c05ce-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c05ce-137">PARAMETERS</span></span>

### <span data-ttu-id="c05ce-138">-Audit</span><span class="sxs-lookup"><span data-stu-id="c05ce-138">-Audit</span></span>

<span data-ttu-id="c05ce-139">Возвращает данные аудита для дескриптора безопасности из системного списка управления доступом (SACL).</span><span class="sxs-lookup"><span data-stu-id="c05ce-139">Gets the audit data for the security descriptor from the system access control list (SACL).</span></span>

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

### <span data-ttu-id="c05ce-140">-Exclude</span><span class="sxs-lookup"><span data-stu-id="c05ce-140">-Exclude</span></span>

<span data-ttu-id="c05ce-141">Исключает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="c05ce-141">Omits the specified items.</span></span> <span data-ttu-id="c05ce-142">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="c05ce-142">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c05ce-143">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c05ce-143">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c05ce-144">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c05ce-144">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c05ce-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="c05ce-145">-Filter</span></span>

<span data-ttu-id="c05ce-146">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="c05ce-146">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="c05ce-147">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="c05ce-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c05ce-148">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="c05ce-148">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="c05ce-149">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их при получении объектов, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="c05ce-149">Filters are more efficient than other parameters, because the provider applies them when getting the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c05ce-150">-Include</span><span class="sxs-lookup"><span data-stu-id="c05ce-150">-Include</span></span>

<span data-ttu-id="c05ce-151">Получает только указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="c05ce-151">Gets only the specified items.</span></span> <span data-ttu-id="c05ce-152">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="c05ce-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c05ce-153">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c05ce-153">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c05ce-154">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c05ce-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c05ce-155">-Path</span><span class="sxs-lookup"><span data-stu-id="c05ce-155">-Path</span></span>

<span data-ttu-id="c05ce-156">Задает путь к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c05ce-156">Specifies the path to a resource.</span></span> <span data-ttu-id="c05ce-157">`Get-Acl` Возвращает дескриптор безопасности ресурса, указанного в пути.</span><span class="sxs-lookup"><span data-stu-id="c05ce-157">`Get-Acl` gets the security descriptor of the resource indicated by the path.</span></span> <span data-ttu-id="c05ce-158">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c05ce-158">Wildcards are permitted.</span></span> <span data-ttu-id="c05ce-159">Если опустить параметр **path** , `Get-Acl` получает дескриптор безопасности текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="c05ce-159">If you omit the **Path** parameter, `Get-Acl` gets the security descriptor of the current directory.</span></span>

<span data-ttu-id="c05ce-160">Имя параметра (Path) указывать необязательно.</span><span class="sxs-lookup"><span data-stu-id="c05ce-160">The parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c05ce-161">-АллцентралакцессполиЦиес</span><span class="sxs-lookup"><span data-stu-id="c05ce-161">-AllCentralAccessPolicies</span></span>

<span data-ttu-id="c05ce-162">Возвращает сведения о всех централизованных политиках доступа, включенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c05ce-162">Gets information about all central access policies that are enabled on the computer.</span></span>

<span data-ttu-id="c05ce-163">Начиная с Windows Server 2012, администраторы могут использовать Active Directory и групповая политика, чтобы задать централизованные политики доступа для пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="c05ce-163">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="c05ce-164">Дополнительные сведения см. в разделе [динамический контроль доступа: обзор сценария](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="c05ce-164">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="c05ce-165">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c05ce-165">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c05ce-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c05ce-166">-InputObject</span></span>

<span data-ttu-id="c05ce-167">Возвращает дескриптор безопасности для указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="c05ce-167">Gets the security descriptor for the specified object.</span></span> <span data-ttu-id="c05ce-168">Введите переменную, содержащую объект, либо команду, которая его возвращают.</span><span class="sxs-lookup"><span data-stu-id="c05ce-168">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="c05ce-169">Нельзя передать по конвейеру объект, отличный от пути, к `Get-Acl` .</span><span class="sxs-lookup"><span data-stu-id="c05ce-169">You cannot pipe an object, other than a path, to `Get-Acl`.</span></span> <span data-ttu-id="c05ce-170">Вместо этого настроить параметр **InputObject** прямо в команде.</span><span class="sxs-lookup"><span data-stu-id="c05ce-170">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="c05ce-171">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c05ce-171">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c05ce-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c05ce-172">-LiteralPath</span></span>

<span data-ttu-id="c05ce-173">Задает путь к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c05ce-173">Specifies the path to a resource.</span></span> <span data-ttu-id="c05ce-174">В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="c05ce-174">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="c05ce-175">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="c05ce-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c05ce-176">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c05ce-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c05ce-177">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="c05ce-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c05ce-178">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c05ce-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c05ce-179">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="c05ce-179">-UseTransaction</span></span>

<span data-ttu-id="c05ce-180">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="c05ce-180">Includes the command in the active transaction.</span></span>
<span data-ttu-id="c05ce-181">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="c05ce-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="c05ce-182">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="c05ce-182">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="c05ce-183">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c05ce-183">CommonParameters</span></span>

<span data-ttu-id="c05ce-184">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c05ce-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c05ce-185">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c05ce-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c05ce-186">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c05ce-186">INPUTS</span></span>

### <span data-ttu-id="c05ce-187">System.String</span><span class="sxs-lookup"><span data-stu-id="c05ce-187">System.String</span></span>

<span data-ttu-id="c05ce-188">Можно передать строку, содержащую путь, в `Get-Acl` .</span><span class="sxs-lookup"><span data-stu-id="c05ce-188">You can pipe a string that contains a path to `Get-Acl`.</span></span>

## <span data-ttu-id="c05ce-189">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c05ce-189">OUTPUTS</span></span>

### <span data-ttu-id="c05ce-190">System. Security. AccessControl. FileSecurity, System. Security. AccessControl. Директорисекурити, System. Security. AccessControl. Регистрисекурити</span><span class="sxs-lookup"><span data-stu-id="c05ce-190">System.Security.AccessControl.FileSecurity, System.Security.AccessControl.DirectorySecurity, System.Security.AccessControl.RegistrySecurity</span></span>

<span data-ttu-id="c05ce-191">`Get-Acl` Возвращает объект, представляющий списки ACL, которые он получает.</span><span class="sxs-lookup"><span data-stu-id="c05ce-191">`Get-Acl` returns an object that represents the ACLs that it gets.</span></span> <span data-ttu-id="c05ce-192">Тип объекта зависит от типа списка ACL.</span><span class="sxs-lookup"><span data-stu-id="c05ce-192">The object type depends upon the ACL type.</span></span>

## <span data-ttu-id="c05ce-193">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c05ce-193">NOTES</span></span>

<span data-ttu-id="c05ce-194">По умолчанию `Get-Acl` отображает путь PowerShell к ресурсу ( `<provider>::<resource-path>` ), владельцу ресурса и «доступ», список (массив) записей управления доступом в списке управления доступом на уровне пользователей (DACL) для ресурса.</span><span class="sxs-lookup"><span data-stu-id="c05ce-194">By default, `Get-Acl` displays the PowerShell path to the resource (`<provider>::<resource-path>`), the owner of the resource, and "Access", a list (array) of the access control entries in the discretionary access control list (DACL) for the resource.</span></span> <span data-ttu-id="c05ce-195">Список DACL контролируется владельцем ресурса.</span><span class="sxs-lookup"><span data-stu-id="c05ce-195">The DACL list is controlled by the resource owner.</span></span>

<span data-ttu-id="c05ce-196">При форматировании результата в виде списка ( `Get-Acl | Format-List` ), помимо пути, владельца и списка доступа, PowerShell отображает следующие свойства и значения свойств:</span><span class="sxs-lookup"><span data-stu-id="c05ce-196">When you format the result as a list, (`Get-Acl | Format-List`), in addition to the path, owner, and access list, PowerShell displays the following properties and property values:</span></span>

- <span data-ttu-id="c05ce-197">**Группа** — группа безопасности владельца.</span><span class="sxs-lookup"><span data-stu-id="c05ce-197">**Group** : The security group of the owner.</span></span>
- <span data-ttu-id="c05ce-198">**Аудит** : список (массив) записей в системном списке управления доступом (SACL).</span><span class="sxs-lookup"><span data-stu-id="c05ce-198">**Audit** :  A list (array) of entries in the system access control list (SACL).</span></span> <span data-ttu-id="c05ce-199">В списке SACL указываются типы попыток доступа, для которых ОС Windows создает записи аудита.</span><span class="sxs-lookup"><span data-stu-id="c05ce-199">The SACL specifies the types of access attempts for which Windows generates audit records.</span></span>
- <span data-ttu-id="c05ce-200">**SDDL** : дескриптор безопасности ресурса, отображаемый в одной текстовой строке в формате языка определения дескриптора безопасности.</span><span class="sxs-lookup"><span data-stu-id="c05ce-200">**Sddl** : The security descriptor of the resource displayed in a single text string in Security Descriptor Definition Language format.</span></span> <span data-ttu-id="c05ce-201">Для получения этих данных PowerShell использует метод **жетсддлформ** дескрипторов безопасности.</span><span class="sxs-lookup"><span data-stu-id="c05ce-201">PowerShell uses the **GetSddlForm** method of security descriptors to get this data.</span></span>

<span data-ttu-id="c05ce-202">Так как `Get-Acl` поддерживается в файловой системе и поставщиках реестра, можно использовать `Get-Acl` для просмотра списка управления доступом к объектам файловой системы, таким как файлы и каталоги, и объекты реестра, такие как разделы и записи реестра.</span><span class="sxs-lookup"><span data-stu-id="c05ce-202">Because `Get-Acl` is supported by the file system and registry providers, you can use `Get-Acl` to view the ACL of file system objects, such as files and directories, and registry objects, such as registry keys and entries.</span></span>

## <span data-ttu-id="c05ce-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c05ce-203">RELATED LINKS</span></span>

[<span data-ttu-id="c05ce-204">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="c05ce-204">Set-Acl</span></span>](Set-Acl.md)