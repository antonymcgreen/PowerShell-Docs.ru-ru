---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: e4775a9d9a37fdd448f6910e612b97a45a35351c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229798"
---
# <span data-ttu-id="a3470-103">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a3470-103">Set-CimInstance</span></span>

## <span data-ttu-id="a3470-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a3470-104">SYNOPSIS</span></span>
<span data-ttu-id="a3470-105">Изменяет экземпляр CIM на CIM-сервере, вызывая метод Модифинстанце класса CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-105">Modifies a CIM instance on a CIM server by calling the ModifyInstance method of the CIM class.</span></span>

## <span data-ttu-id="a3470-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3470-106">SYNTAX</span></span>

### <span data-ttu-id="a3470-107">Циминстанцекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a3470-107">CimInstanceComputerSet (Default)</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a3470-108">Циминстанцесессионсет</span><span class="sxs-lookup"><span data-stu-id="a3470-108">CimInstanceSessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a3470-109">куерисессионсет</span><span class="sxs-lookup"><span data-stu-id="a3470-109">QuerySessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a3470-110">куерикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="a3470-110">QueryComputerSet</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a3470-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3470-111">DESCRIPTION</span></span>

<span data-ttu-id="a3470-112">Этот командлет изменяет экземпляр CIM на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="a3470-112">This cmdlet modifies a CIM instance on a CIM server.</span></span>

<span data-ttu-id="a3470-113">Если параметр **InputObject** не указан, командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a3470-113">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="a3470-114">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.</span><span class="sxs-lookup"><span data-stu-id="a3470-114">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="a3470-115">Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="a3470-115">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="a3470-116">Если указан параметр **InputObject** , командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a3470-116">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="a3470-117">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.</span><span class="sxs-lookup"><span data-stu-id="a3470-117">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="a3470-118">Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра **CimSession** , либо значение параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="a3470-118">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="a3470-119">Это не очень распространено.</span><span class="sxs-lookup"><span data-stu-id="a3470-119">This is not very common.</span></span>

## <span data-ttu-id="a3470-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="a3470-120">EXAMPLES</span></span>

### <span data-ttu-id="a3470-121">Пример 1. Задание экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="a3470-121">Example 1: Set the CIM instance</span></span>

<span data-ttu-id="a3470-122">В этом примере для свойства **вариаблевалуе** задается значение **ABCD** с помощью параметра **запроса** .</span><span class="sxs-lookup"><span data-stu-id="a3470-122">This example sets the value of the **VariableValue** property to **abcd** using the **Query** parameter.</span></span> <span data-ttu-id="a3470-123">Можно изменить экземпляры, соответствующие запросу на языке запросов инструментарий управления Windows (WMI) (WQL).</span><span class="sxs-lookup"><span data-stu-id="a3470-123">You can modify instances matching a Windows Management Instrumentation Query Language (WQL) query.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="a3470-124">Пример 2. Задание свойства экземпляра CIM с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="a3470-124">Example 2: Set the CIM instance property using pipeline</span></span>

<span data-ttu-id="a3470-125">В этом примере извлекается объект экземпляра CIM, отфильтрованный по параметру **запроса** с помощью `Get-CimInstance` командлета.</span><span class="sxs-lookup"><span data-stu-id="a3470-125">This example retrieves the CIM instance object filtered by the **Query** parameter using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="a3470-126">`Set-CimInstance`Командлет изменяет значение свойства **вариаблевалуе** на **ABCD**.</span><span class="sxs-lookup"><span data-stu-id="a3470-126">The `Set-CimInstance` cmdlet modifies the value of **VariableValue** property to **abcd**.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="a3470-127">Пример 3. Установка свойства экземпляра CIM с помощью входного объекта</span><span class="sxs-lookup"><span data-stu-id="a3470-127">Example 3: Set the CIM instance property using input object</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

<span data-ttu-id="a3470-128">Этот пример извлекает объекты экземпляра CIM, отфильтрованные с помощью параметра запроса в, в переменную `$x` с помощью `Get-CimInstance` , а затем передает содержимое переменной в `Set-CimInstance` командлет.</span><span class="sxs-lookup"><span data-stu-id="a3470-128">This example retrieves the CIM instance objects filtered by the Query parameter in to a variable `$x` using `Get-CimInstance`, and then passes the contents of the variable to the `Set-CimInstance` cmdlet.</span></span> <span data-ttu-id="a3470-129">`Set-CimInstance` затем изменяет свойство **вариаблевалуе** на **someValue**.</span><span class="sxs-lookup"><span data-stu-id="a3470-129">`Set-CimInstance` then modifies the **VariableValue** property to **somevalue**.</span></span> <span data-ttu-id="a3470-130">Поскольку используется параметр **PassThru** , этот пример возвращает измененный объект экземпляра CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-130">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

### <span data-ttu-id="a3470-131">Пример 4. Установка свойства экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="a3470-131">Example 4: Set the CIM instance property</span></span>

<span data-ttu-id="a3470-132">В этом примере извлекается объект экземпляра CIM, указанный в параметре **запроса** , в переменную `$x` с помощью `Get-CimInstance` командлета и изменяется значение свойства **вариаблевалуе** объекта для изменения.</span><span class="sxs-lookup"><span data-stu-id="a3470-132">This example retrieves the CIM instance object that is specified in the **Query** parameter into a variable `$x` using the `Get-CimInstance` cmdlet, and changes the **VariableValue** property value of the object to change.</span></span> <span data-ttu-id="a3470-133">Затем объект экземпляра CIM сохраняется с помощью `Set-CimInstance` командлета.</span><span class="sxs-lookup"><span data-stu-id="a3470-133">The CIM instance object is then saved using the `Set-CimInstance` cmdlet.</span></span>
<span data-ttu-id="a3470-134">Поскольку используется параметр **PassThru** , этот пример возвращает измененный объект экземпляра CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-134">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### <span data-ttu-id="a3470-135">Пример 5. Отображение списка экземпляров CIM для изменения с помощью WhatIf</span><span class="sxs-lookup"><span data-stu-id="a3470-135">Example 5: Show the list of CIM instances to modify using WhatIf</span></span>

<span data-ttu-id="a3470-136">В этом примере используется общий параметр **WhatIf** для указания на то, что изменение не должно выполняться, но выводить только то, что было бы выполнено, если оно было выполнено.</span><span class="sxs-lookup"><span data-stu-id="a3470-136">This example uses the common parameter **WhatIf** to specify that the modification should not be done, but only output what would happen if it were done.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### <span data-ttu-id="a3470-137">Пример 6. Задание экземпляра CIM после подтверждения от пользователя</span><span class="sxs-lookup"><span data-stu-id="a3470-137">Example 6: Set the CIM instance after confirmation from the user</span></span>

<span data-ttu-id="a3470-138">В этом примере используется общий параметр **Confirm** , чтобы указать, что изменение должно выполняться только после подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3470-138">This example uses the common parameter **Confirm** to specify that the modification should be done only after confirmation from the user.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### <span data-ttu-id="a3470-139">Пример 7. Задание созданного экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="a3470-139">Example 7: Set the created CIM instance</span></span>

<span data-ttu-id="a3470-140">В этом примере создается экземпляр CIM с указанными свойствами с помощью `New-CimInstance` командлета и извлекается его содержимое в переменную `$x` .</span><span class="sxs-lookup"><span data-stu-id="a3470-140">This example creates a CIM instance with the specified properties using the `New-CimInstance` cmdlet, and retrieves its contents in to a variable `$x`.</span></span> <span data-ttu-id="a3470-141">Переменная затем передается в `Set-CimInstance` командлет, который изменяет значение свойства **вариаблевалуе** на **someValue**.</span><span class="sxs-lookup"><span data-stu-id="a3470-141">The variable is then passed to the `Set-CimInstance` cmdlet, which modifies the value of **VariableValue** property to **somevalue**.</span></span>
<span data-ttu-id="a3470-142">Поскольку используется параметр **PassThru** , этот пример возвращает измененный объект экземпляра CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-142">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## <span data-ttu-id="a3470-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3470-143">PARAMETERS</span></span>

### <span data-ttu-id="a3470-144">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a3470-144">-CimSession</span></span>

<span data-ttu-id="a3470-145">Запускает командлеты на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a3470-145">Runs the cmdlets on a remote computer.</span></span> <span data-ttu-id="a3470-146">Введите имя компьютера или объект сеанса, например выходные данные `New-CimSession` `Get-CimSession` командлета или.</span><span class="sxs-lookup"><span data-stu-id="a3470-146">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

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

### <span data-ttu-id="a3470-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a3470-147">-ComputerName</span></span>

<span data-ttu-id="a3470-148">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-148">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="a3470-149">Можно указать полное доменное имя или NetBIOS-имя.</span><span class="sxs-lookup"><span data-stu-id="a3470-149">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="a3470-150">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="a3470-150">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="a3470-151">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="a3470-151">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="a3470-152">Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="a3470-152">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="a3470-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a3470-153">-InputObject</span></span>

<span data-ttu-id="a3470-154">Указывает объект экземпляра CIM для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="a3470-154">Specifies a CIM instance object to use as input.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a3470-155">-Namespace</span><span class="sxs-lookup"><span data-stu-id="a3470-155">-Namespace</span></span>

<span data-ttu-id="a3470-156">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-156">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="a3470-157">Пространством имен по умолчанию является root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="a3470-157">The default namespace is root/cimv2.</span></span> <span data-ttu-id="a3470-158">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="a3470-158">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3470-159">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="a3470-159">-OperationTimeoutSec</span></span>

<span data-ttu-id="a3470-160">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="a3470-160">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="a3470-161">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="a3470-161">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="a3470-162">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="a3470-162">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="a3470-163">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a3470-163">-PassThru</span></span>

<span data-ttu-id="a3470-164">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="a3470-164">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="a3470-165">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a3470-165">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a3470-166">-Property</span><span class="sxs-lookup"><span data-stu-id="a3470-166">-Property</span></span>

<span data-ttu-id="a3470-167">Задает свойства экземпляра CIM в виде хэш-таблицы (с использованием пар "имя-значение").</span><span class="sxs-lookup"><span data-stu-id="a3470-167">Specifies the properties of the CIM instance as a hash table (using name-value pairs).</span></span> <span data-ttu-id="a3470-168">Изменяются только свойства, указанные с помощью этого параметра.</span><span class="sxs-lookup"><span data-stu-id="a3470-168">Only the properties specified using this parameter are changed.</span></span> <span data-ttu-id="a3470-169">Другие свойства экземпляра CIM не изменяются.</span><span class="sxs-lookup"><span data-stu-id="a3470-169">Other properties of the CIM instance are not changed.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3470-170">-Query</span><span class="sxs-lookup"><span data-stu-id="a3470-170">-Query</span></span>

<span data-ttu-id="a3470-171">Указывает запрос, выполняемый на CIM-сервере для получения экземпляров CIM, на которых должен выполняться командлет.</span><span class="sxs-lookup"><span data-stu-id="a3470-171">Specifies a query to run on the CIM server to retrieve CIM instances on which to run the cmdlet.</span></span> <span data-ttu-id="a3470-172">Диалект запроса можно указать с помощью параметра Куеридиалект.</span><span class="sxs-lookup"><span data-stu-id="a3470-172">You can specify the query dialect using the QueryDialect parameter.</span></span>

<span data-ttu-id="a3470-173">Если указанное значение содержит двойные кавычки ( `"` ), одинарные кавычки ( `'` ) или обратную косую черту ( `\` ), эти символы необходимо заключить в escape-символ обратной косой черты ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="a3470-173">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="a3470-174">Если указанное значение использует оператор WQL **Like** , необходимо экранировать следующие символы, заключив их в квадратные скобки ( `[]` ): percent ( `%` ), символ подчеркивания ( `_` ) или открывающую квадратную скобку ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="a3470-174">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3470-175">-Куеридиалект</span><span class="sxs-lookup"><span data-stu-id="a3470-175">-QueryDialect</span></span>

<span data-ttu-id="a3470-176">Указывает язык запросов, используемый для параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="a3470-176">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="a3470-177">Допустимые значения для этого параметра: **WQL** или **CQL**.</span><span class="sxs-lookup"><span data-stu-id="a3470-177">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="a3470-178">Значение по умолчанию — **WQL**.</span><span class="sxs-lookup"><span data-stu-id="a3470-178">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3470-179">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="a3470-179">-ResourceUri</span></span>

<span data-ttu-id="a3470-180">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="a3470-180">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="a3470-181">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a3470-181">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="a3470-182">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="a3470-182">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="a3470-183">Пример:</span><span class="sxs-lookup"><span data-stu-id="a3470-183">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="a3470-184">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="a3470-184">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="a3470-185">ResourceURI можно использовать только с сеансами CIM, созданными с помощью протокола WSMan, или при указании параметра ComputerName, который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="a3470-185">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="a3470-186">Если указать этот параметр без указания параметра ComputerName или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр ResourceURI.</span><span class="sxs-lookup"><span data-stu-id="a3470-186">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="a3470-187">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="a3470-187">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="a3470-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a3470-188">-Confirm</span></span>

<span data-ttu-id="a3470-189">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a3470-189">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a3470-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a3470-190">-WhatIf</span></span>

<span data-ttu-id="a3470-191">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a3470-191">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a3470-192">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a3470-192">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a3470-193">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a3470-193">CommonParameters</span></span>

<span data-ttu-id="a3470-194">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3470-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3470-195">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a3470-195">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a3470-196">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a3470-196">INPUTS</span></span>

### <span data-ttu-id="a3470-197">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="a3470-197">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="a3470-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a3470-198">OUTPUTS</span></span>

### <span data-ttu-id="a3470-199">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="a3470-199">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="a3470-200">Если указан параметр **PassThru** , этот командлет возвращает измененный объект экземпляра CIM.</span><span class="sxs-lookup"><span data-stu-id="a3470-200">When the **Passthru** parameter is specified, this cmdlet returns a modified CIM instance object.</span></span>

## <span data-ttu-id="a3470-201">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a3470-201">NOTES</span></span>

## <span data-ttu-id="a3470-202">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a3470-202">RELATED LINKS</span></span>

[<span data-ttu-id="a3470-203">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a3470-203">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="a3470-204">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a3470-204">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="a3470-205">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a3470-205">Remove-CimInstance</span></span>](remove-ciminstance.md)
