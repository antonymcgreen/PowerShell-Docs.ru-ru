---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimInstance
ms.openlocfilehash: 5a23aaa59eb10ff35ecefb7365d3294cdb06f781
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599620"
---
# <span data-ttu-id="6b005-102">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="6b005-102">Remove-CimInstance</span></span>

## <span data-ttu-id="6b005-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6b005-103">SYNOPSIS</span></span>
<span data-ttu-id="6b005-104">Удаляет экземпляр CIM с компьютера.</span><span class="sxs-lookup"><span data-stu-id="6b005-104">Removes a CIM instance from a computer.</span></span>

## <span data-ttu-id="6b005-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6b005-105">SYNTAX</span></span>

### <span data-ttu-id="6b005-106">Циминстанцекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6b005-106">CimInstanceComputerSet (Default)</span></span>

```
Remove-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6b005-107">Циминстанцесессионсет</span><span class="sxs-lookup"><span data-stu-id="6b005-107">CimInstanceSessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6b005-108">куерисессионсет</span><span class="sxs-lookup"><span data-stu-id="6b005-108">QuerySessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="6b005-109">куерикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="6b005-109">QueryComputerSet</span></span>

```
Remove-CimInstance [-ComputerName <String[]>] [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="6b005-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6b005-110">DESCRIPTION</span></span>

<span data-ttu-id="6b005-111">Этот командлет удаляет экземпляр CIM с сервера CIM.</span><span class="sxs-lookup"><span data-stu-id="6b005-111">This cmdlet removes a CIM instance from a CIM server.</span></span> <span data-ttu-id="6b005-112">Экземпляр CIM можно указать для удаления с помощью объекта экземпляра CIM, полученного `Get-CimInstance` командлетом, или путем указания запроса.</span><span class="sxs-lookup"><span data-stu-id="6b005-112">You can specify the CIM instance to remove by using either a CIM instance object retrieved by the `Get-CimInstance` cmdlet, or by specifying a query.</span></span>

<span data-ttu-id="6b005-113">Если параметр **InputObject** не указан, командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="6b005-113">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="6b005-114">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.</span><span class="sxs-lookup"><span data-stu-id="6b005-114">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="6b005-115">Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="6b005-115">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="6b005-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="6b005-116">EXAMPLES</span></span>

### <span data-ttu-id="6b005-117">Пример 1. Удаление экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="6b005-117">Example 1: Remove the CIM instance</span></span>

<span data-ttu-id="6b005-118">В этом примере используется параметр **запроса** для удаления экземпляров CIM из класса с именем **Win32_Environment** , который начинается со строки символов **testvar** .</span><span class="sxs-lookup"><span data-stu-id="6b005-118">This example use the **Query** parameter to remove CIM instances from the class named **Win32_Environment** that start with the character string **testvar** .</span></span>

```powershell
Remove-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"'
```

### <span data-ttu-id="6b005-119">Пример 2. Удаление экземпляра CIM с помощью объекта экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="6b005-119">Example 2: Remove the CIM instance using CIM instance object</span></span>

<span data-ttu-id="6b005-120">Этот пример извлекает объекты экземпляра CIM, отфильтрованные по параметру **запроса** , и сохраняет их в переменной с именем `$var` с помощью `Get-CimInstance` командлета.</span><span class="sxs-lookup"><span data-stu-id="6b005-120">This example retrieves the CIM instance objects filtered by the **Query** parameter and stores them in variable named `$var` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="6b005-121">После этого содержимое переменной передается в `Remove-CimInstance` командлет, который удаляет экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="6b005-121">The contents of the variable are then passed to the `Remove-CimInstance` cmdlet, which removes the CIM instances.</span></span>

```powershell
notepad.exe
$var = Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "notepad%"'
Remove-CimInstance -InputObject $var
```

## <span data-ttu-id="6b005-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6b005-122">PARAMETERS</span></span>

### <span data-ttu-id="6b005-123">-CimSession</span><span class="sxs-lookup"><span data-stu-id="6b005-123">-CimSession</span></span>

<span data-ttu-id="6b005-124">Выполняет команду с помощью указанного сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="6b005-124">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="6b005-125">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="6b005-125">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="6b005-126">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="6b005-126">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-127">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6b005-127">-ComputerName</span></span>

<span data-ttu-id="6b005-128">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="6b005-128">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="6b005-129">Можно указать полное доменное имя или NetBIOS-имя.</span><span class="sxs-lookup"><span data-stu-id="6b005-129">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="6b005-130">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="6b005-130">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="6b005-131">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="6b005-131">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="6b005-132">Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="6b005-132">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6b005-133">-InputObject</span></span>

<span data-ttu-id="6b005-134">Указывает объект экземпляра CIM, который будет удален с сервера CIM.</span><span class="sxs-lookup"><span data-stu-id="6b005-134">Specifies a CIM instance object to be removed from the CIM server.</span></span> <span data-ttu-id="6b005-135">Объект, переданный в командлет, не изменяется, удаляется только экземпляр на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="6b005-135">The object passed to the cmdlet is not changed, only the instance in the CIM server is removed.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-136">-Namespace</span><span class="sxs-lookup"><span data-stu-id="6b005-136">-Namespace</span></span>

<span data-ttu-id="6b005-137">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="6b005-137">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="6b005-138">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="6b005-138">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="6b005-139">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="6b005-139">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-140">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="6b005-140">-OperationTimeoutSec</span></span>

<span data-ttu-id="6b005-141">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="6b005-141">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="6b005-142">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="6b005-142">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="6b005-143">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="6b005-143">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-144">-Query</span><span class="sxs-lookup"><span data-stu-id="6b005-144">-Query</span></span>

<span data-ttu-id="6b005-145">Указывает запрос для выполнения на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="6b005-145">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="6b005-146">Диалект запроса можно указать с помощью параметра **куеридиалект** .</span><span class="sxs-lookup"><span data-stu-id="6b005-146">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="6b005-147">Если указанное значение содержит двойные кавычки ( `"` ), одинарные кавычки ( `'` ) или обратную косую черту ( `\` ), эти символы необходимо заключить в escape-символ обратной косой черты ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="6b005-147">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="6b005-148">Если указанное значение использует оператор WQL LIKE, необходимо экранировать следующие символы, заключив их в квадратные скобки ( `[]` ): percent ( `%` ), символ подчеркивания ( `_` ) или открывающую квадратную скобку ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="6b005-148">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-149">-Куеридиалект</span><span class="sxs-lookup"><span data-stu-id="6b005-149">-QueryDialect</span></span>

<span data-ttu-id="6b005-150">Указывает язык запросов, используемый для параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="6b005-150">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="6b005-151">Допустимые значения для этого параметра: **WQL** или **CQL**.</span><span class="sxs-lookup"><span data-stu-id="6b005-151">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="6b005-152">Значение по умолчанию — **WQL**.</span><span class="sxs-lookup"><span data-stu-id="6b005-152">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-153">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="6b005-153">-ResourceUri</span></span>

<span data-ttu-id="6b005-154">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="6b005-154">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="6b005-155">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6b005-155">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="6b005-156">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="6b005-156">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="6b005-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="6b005-157">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="6b005-158">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="6b005-158">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="6b005-159">ResourceURI можно использовать только с сеансами CIM, созданными с помощью протокола WSMan, или при указании параметра ComputerName, который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="6b005-159">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="6b005-160">Если указать этот параметр без указания параметра ComputerName или указать сеанс CIM, созданный с помощью протокола DCOM, возникает ошибка, так как протокол DCOM не поддерживает параметр ResourceURI.</span><span class="sxs-lookup"><span data-stu-id="6b005-160">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="6b005-161">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="6b005-161">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6b005-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6b005-162">-Confirm</span></span>

<span data-ttu-id="6b005-163">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="6b005-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6b005-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6b005-164">-WhatIf</span></span>

<span data-ttu-id="6b005-165">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="6b005-165">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6b005-166">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6b005-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6b005-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6b005-167">CommonParameters</span></span>

<span data-ttu-id="6b005-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6b005-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6b005-169">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6b005-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6b005-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6b005-170">INPUTS</span></span>

### <span data-ttu-id="6b005-171">None</span><span class="sxs-lookup"><span data-stu-id="6b005-171">None</span></span>

<span data-ttu-id="6b005-172">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="6b005-172">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="6b005-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6b005-173">OUTPUTS</span></span>

### <span data-ttu-id="6b005-174">None</span><span class="sxs-lookup"><span data-stu-id="6b005-174">None</span></span>

<span data-ttu-id="6b005-175">Этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="6b005-175">This cmdlet produces no outputs.</span></span>

## <span data-ttu-id="6b005-176">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6b005-176">NOTES</span></span>

## <span data-ttu-id="6b005-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6b005-177">RELATED LINKS</span></span>

[<span data-ttu-id="6b005-178">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="6b005-178">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="6b005-179">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="6b005-179">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="6b005-180">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="6b005-180">Set-CimInstance</span></span>](Set-CimInstance.md)

