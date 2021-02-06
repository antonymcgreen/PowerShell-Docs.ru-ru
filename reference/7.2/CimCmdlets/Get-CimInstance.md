---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 0e4a148601f3ef2212f9c97128c54258906106d7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601291"
---
# <span data-ttu-id="b77a7-102">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b77a7-102">Get-CimInstance</span></span>

## <span data-ttu-id="b77a7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b77a7-103">SYNOPSIS</span></span>
<span data-ttu-id="b77a7-104">Возвращает экземпляры CIM класса из CIM-сервера.</span><span class="sxs-lookup"><span data-stu-id="b77a7-104">Gets the CIM instances of a class from a CIM server.</span></span>

## <span data-ttu-id="b77a7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b77a7-105">SYNTAX</span></span>

### <span data-ttu-id="b77a7-106">Класснамекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b77a7-106">ClassNameComputerSet (Default)</span></span>

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b77a7-107">ресаурцеурисессионсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-107">ResourceUriSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="b77a7-108">куерисессионсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-108">QuerySessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### <span data-ttu-id="b77a7-109">класснамесессионсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-109">ClassNameSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b77a7-110">Циминстанцесессионсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-110">CimInstanceSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="b77a7-111">Циминстанцекомпутерсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-111">CimInstanceComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="b77a7-112">ресаурцеурикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-112">ResourceUriComputerSet</span></span>

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="b77a7-113">куерикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="b77a7-113">QueryComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## <span data-ttu-id="b77a7-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b77a7-114">DESCRIPTION</span></span>

<span data-ttu-id="b77a7-115">`Get-CimInstance`Командлет возвращает экземпляры CIM класса из CIM-сервера.</span><span class="sxs-lookup"><span data-stu-id="b77a7-115">The `Get-CimInstance` cmdlet gets the CIM instances of a class from a CIM server.</span></span> <span data-ttu-id="b77a7-116">Для этого командлета можно указать либо имя класса, либо запрос.</span><span class="sxs-lookup"><span data-stu-id="b77a7-116">You can specify either the class name or a query for this cmdlet.</span></span> <span data-ttu-id="b77a7-117">Этот командлет возвращает один или несколько объектов экземпляра CIM, представляющих моментальный снимок экземпляров CIM, имеющихся на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="b77a7-117">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances present on the CIM server.</span></span>

<span data-ttu-id="b77a7-118">Если параметр **InputObject** не указан, командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b77a7-118">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="b77a7-119">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.</span><span class="sxs-lookup"><span data-stu-id="b77a7-119">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="b77a7-120">Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-120">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="b77a7-121">Если указан параметр **InputObject** , командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b77a7-121">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="b77a7-122">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.</span><span class="sxs-lookup"><span data-stu-id="b77a7-122">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="b77a7-123">Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра CimSession, либо значение параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-123">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the CimSession parameter value or **ComputerName** parameter value.</span></span>

## <span data-ttu-id="b77a7-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="b77a7-124">EXAMPLES</span></span>

### <span data-ttu-id="b77a7-125">Пример 1. получение экземпляров CIM указанного класса</span><span class="sxs-lookup"><span data-stu-id="b77a7-125">Example 1: Get the CIM instances of a specified class</span></span>

<span data-ttu-id="b77a7-126">В этом примере извлекаются экземпляры CIM класса с именем **Win32_Process**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-126">This example retrieves the CIM instances of a class named **Win32_Process**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process
```

### <span data-ttu-id="b77a7-127">Пример 2. Получение списка пространств имен с сервера WMI</span><span class="sxs-lookup"><span data-stu-id="b77a7-127">Example 2: Get a list of namespaces from a WMI server</span></span>

<span data-ttu-id="b77a7-128">В этом примере извлекается список пространств имен в **корневом** пространстве имен на сервере WMI.</span><span class="sxs-lookup"><span data-stu-id="b77a7-128">This example retrieves a list of namespaces under the **Root** namespace on a WMI server.</span></span>

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### <span data-ttu-id="b77a7-129">Пример 3. получение экземпляров класса, отфильтрованных с помощью запроса</span><span class="sxs-lookup"><span data-stu-id="b77a7-129">Example 3: Get instances of a class filtered by using a query</span></span>

<span data-ttu-id="b77a7-130">В этом примере извлекаются все экземпляры CIM, начинающиеся с буквы **P** класса с именем **Win32_Process** , с помощью запроса, указанного параметром **запроса** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-130">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the query specified by a **Query** parameter.</span></span>

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### <span data-ttu-id="b77a7-131">Пример 4. получение экземпляров класса, отфильтрованных с помощью имени класса и критерия фильтра</span><span class="sxs-lookup"><span data-stu-id="b77a7-131">Example 4: Get instances of a class filtered by using a class name and a filter expression</span></span>

<span data-ttu-id="b77a7-132">В этом примере извлекаются все экземпляры CIM, начинающиеся с буквы **P** класса с именем **Win32_Process** с помощью параметра Filter.</span><span class="sxs-lookup"><span data-stu-id="b77a7-132">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the Filter parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### <span data-ttu-id="b77a7-133">Пример 5. получение экземпляров CIM только с заполненными ключевыми свойствами</span><span class="sxs-lookup"><span data-stu-id="b77a7-133">Example 5: Get the CIM instances with only key properties filled in</span></span>

<span data-ttu-id="b77a7-134">В этом примере создается новый экземпляр CIM в памяти для класса с именем **Win32_Process** со свойством ключа `@{ "Handle"=0 }` и сохраняется в переменной с именем `$x` .</span><span class="sxs-lookup"><span data-stu-id="b77a7-134">This example creates a new CIM instance in memory for a class named **Win32_Process** with the key property `@{ "Handle"=0 }` and stores it in a variable named `$x`.</span></span> <span data-ttu-id="b77a7-135">Переменная передается в командлет в качестве экземпляра CIM `Get-CimInstance` для получения конкретного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b77a7-135">The variable is passed as a CIM instance to the `Get-CimInstance` cmdlet to get a particular instance.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### <span data-ttu-id="b77a7-136">Пример 6. получение экземпляров CIM и их повторное использование</span><span class="sxs-lookup"><span data-stu-id="b77a7-136">Example 6: Retrieve CIM instances and reuse them</span></span>

<span data-ttu-id="b77a7-137">Этот пример получает экземпляры CIM класса с именем **Win32_Process** и сохраняет их в переменных `$x` и `$y` .</span><span class="sxs-lookup"><span data-stu-id="b77a7-137">This example gets the CIM instances of a class named **Win32_Process** and stores them in the variables `$x` and `$y`.</span></span> <span data-ttu-id="b77a7-138">Переменная `$x` затем форматируется в таблице, содержащей только свойства **Name** и **кернелмодетиме** , для которых задано **Автомасштабирование**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-138">The variable `$x` is then formatted in a table containing only the **Name** and **KernelModeTime** properties, the table set to **AutoSize**.</span></span>

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### <span data-ttu-id="b77a7-139">Пример 7. получение экземпляров CIM с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="b77a7-139">Example 7: Get CIM instances from remote computer</span></span>

<span data-ttu-id="b77a7-140">В этом примере извлекаются экземпляры CIM класса с именем **Win32_ComputerSystem** с удаленных компьютеров с именами **Server01** и **Server02**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-140">This example retrieves the CIM instances of a class named **Win32_ComputerSystem** from the remote computers named **Server01** and **Server02**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### <span data-ttu-id="b77a7-141">Пример 8. получение только ключевых свойств, а не всех свойств</span><span class="sxs-lookup"><span data-stu-id="b77a7-141">Example 8: Getting only the key properties, instead of all properties</span></span>

<span data-ttu-id="b77a7-142">В этом примере извлекаются только ключевые свойства, которые уменьшают размер объекта и сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="b77a7-142">This example retrieves only the key properties, which reduces the size of the object and network traffic.</span></span>

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### <span data-ttu-id="b77a7-143">Пример 9. получение только подмножества свойств, а не всех свойств</span><span class="sxs-lookup"><span data-stu-id="b77a7-143">Example 9: Getting only a subset of properties, instead of all properties</span></span>

<span data-ttu-id="b77a7-144">В этом примере извлекается только подмножество свойств, которое уменьшает размер объекта и сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="b77a7-144">This example retrieves only a subset of properties, which reduces the size of the object and network traffic.</span></span>

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

<span data-ttu-id="b77a7-145">Экземпляр, полученный с помощью параметра **Property** , может использоваться для выполнения других операций CIM, например `Set-CimInstance` или `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="b77a7-145">The instance retrieved with the **Property** parameter can be used to perform other CIM operations, for example `Set-CimInstance` or `Invoke-CimMethod`.</span></span>

### <span data-ttu-id="b77a7-146">Пример 10. получение экземпляра CIM с помощью сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="b77a7-146">Example 10: Get the CIM instance using CIM session</span></span>

<span data-ttu-id="b77a7-147">В этом примере создается сеанс CIM на компьютерах с именем **Server01** и **Server02** с помощью `New-CimSession` командлета, а сведения о сеансе сохраняются в переменной с именем `$s` .</span><span class="sxs-lookup"><span data-stu-id="b77a7-147">This example creates a CIM session on the computers named **Server01** and **Server02** using the `New-CimSession` cmdlet and stores the session information in a variable named `$s`.</span></span> <span data-ttu-id="b77a7-148">Затем содержимое переменной передается с `Get-CimInstance` помощью параметра **CimSession** , чтобы получить экземпляры CIM класса с именем **Win32_ComputerSystem**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-148">The contents of the variable are then passed to `Get-CimInstance` by using the **CimSession** parameter, to get the CIM instances of the class named **Win32_ComputerSystem**.</span></span>

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## <span data-ttu-id="b77a7-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b77a7-149">PARAMETERS</span></span>

### <span data-ttu-id="b77a7-150">-CimSession</span><span class="sxs-lookup"><span data-stu-id="b77a7-150">-CimSession</span></span>

<span data-ttu-id="b77a7-151">Указывает сеанс CIM, который будет использоваться для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="b77a7-151">Specifies the CIM session to use for this cmdlet.</span></span> <span data-ttu-id="b77a7-152">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="b77a7-152">Enter a variable that contains the CIM session or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="b77a7-153">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="b77a7-153">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-154">-ClassName</span><span class="sxs-lookup"><span data-stu-id="b77a7-154">-ClassName</span></span>

<span data-ttu-id="b77a7-155">Указывает имя класса CIM, для которого необходимо получить экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="b77a7-155">Specifies the name of the CIM class for which to retrieve the CIM instances.</span></span> <span data-ttu-id="b77a7-156">Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="b77a7-156">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-157">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b77a7-157">-ComputerName</span></span>

<span data-ttu-id="b77a7-158">Указывает компьютер, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="b77a7-158">Specifies computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="b77a7-159">Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="b77a7-159">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="b77a7-160">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="b77a7-160">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="b77a7-161">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="b77a7-161">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="b77a7-162">Если на одном компьютере выполняется несколько операций, подключайтесь с помощью сеанса CIM для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="b77a7-162">If multiple operations are being performed on the same computer, connect using a CIM session for better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-163">-Filter</span><span class="sxs-lookup"><span data-stu-id="b77a7-163">-Filter</span></span>

<span data-ttu-id="b77a7-164">Указывает предложение WHERE для использования в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="b77a7-164">Specifies a where clause to use as a filter.</span></span> <span data-ttu-id="b77a7-165">Укажите предложение на языке запросов **WQL** или **CQL** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-165">Specify the clause in either the **WQL** or the **CQL** query language.</span></span> <span data-ttu-id="b77a7-166">Не включайте `WHERE` ключевое слово в значение параметра.</span><span class="sxs-lookup"><span data-stu-id="b77a7-166">Do not include the `WHERE` keyword in the value of the parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b77a7-167">-InputObject</span></span>

<span data-ttu-id="b77a7-168">Указывает объект экземпляра CIM для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="b77a7-168">Specifies a CIM instance object to use as input.</span></span>

<span data-ttu-id="b77a7-169">Если вы уже работаете с объектом экземпляра CIM, этот параметр можно использовать для передачи объекта экземпляра CIM для получения последнего моментального снимка с сервера CIM.</span><span class="sxs-lookup"><span data-stu-id="b77a7-169">If you are already working with a CIM instance object, you can use this parameter to pass the CIM instance object in order to get the latest snapshot from the CIM server.</span></span> <span data-ttu-id="b77a7-170">При передаче объекта экземпляра CIM в качестве входных данных `Get-CimInstance` возвращает объект с сервера с помощью операции получения CIM вместо перечисления или операции запроса.</span><span class="sxs-lookup"><span data-stu-id="b77a7-170">When you pass a CIM instance object as an input, `Get-CimInstance` returns the object from server using a get CIM operation, instead of an enumerate or query operation.</span></span> <span data-ttu-id="b77a7-171">Использование операции получения CIM более эффективно, чем получение всех экземпляров и последующее их фильтрация.</span><span class="sxs-lookup"><span data-stu-id="b77a7-171">Using a get CIM operation is more efficient than retrieving all instances and then filtering them.</span></span>

<span data-ttu-id="b77a7-172">Если класс CIM не реализует операцию Get, то при указании параметра **InputObject** возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="b77a7-172">If the CIM class does not implement the get operation, then specifying the **InputObject** parameter returns an error.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-173">-Кэйонли</span><span class="sxs-lookup"><span data-stu-id="b77a7-173">-KeyOnly</span></span>

<span data-ttu-id="b77a7-174">Указывает, что возвращаются только объекты с заполненными ключевыми свойствами.</span><span class="sxs-lookup"><span data-stu-id="b77a7-174">Indicates that only objects with key properties populated are returned.</span></span> <span data-ttu-id="b77a7-175">Указание параметра **кэйонли** сокращает объем данных, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="b77a7-175">Specifying the **KeyOnly** parameter reduces the amount of data transferred over the network.</span></span>

<span data-ttu-id="b77a7-176">Используйте параметр **кэйонли** , чтобы вернуть только небольшую часть объекта, которая может использоваться для других операций, таких как `Set-CimInstance` `Get-CimAssociatedInstance` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="b77a7-176">Use the **KeyOnly** parameter to return only a small portion of the object, which can be used for other operations, such as the `Set-CimInstance` or `Get-CimAssociatedInstance` cmdlets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-177">-Namespace</span><span class="sxs-lookup"><span data-stu-id="b77a7-177">-Namespace</span></span>

<span data-ttu-id="b77a7-178">Указывает пространство имен класса CIM.</span><span class="sxs-lookup"><span data-stu-id="b77a7-178">Specifies the namespace of CIM class.</span></span>

<span data-ttu-id="b77a7-179">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-179">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="b77a7-180">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b77a7-180">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-181">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="b77a7-181">-OperationTimeoutSec</span></span>

<span data-ttu-id="b77a7-182">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="b77a7-182">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="b77a7-183">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="b77a7-183">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="b77a7-184">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="b77a7-184">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="b77a7-185">-Property</span><span class="sxs-lookup"><span data-stu-id="b77a7-185">-Property</span></span>

<span data-ttu-id="b77a7-186">Задает набор свойств экземпляра для извлечения.</span><span class="sxs-lookup"><span data-stu-id="b77a7-186">Specifies a set of instance properties to retrieve.</span></span> <span data-ttu-id="b77a7-187">Используйте этот параметр, если необходимо уменьшить размер возвращаемого объекта либо в памяти, либо по сети.</span><span class="sxs-lookup"><span data-stu-id="b77a7-187">Use this parameter when you need to reduce the size of the object returned, either in memory or over the network.</span></span> <span data-ttu-id="b77a7-188">Возвращаемый объект также содержит ключевые свойства, даже если они не перечислены с помощью параметра **Property** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-188">The object returned also contains the key properties even if you have not listed them using the **Property** parameter.</span></span> <span data-ttu-id="b77a7-189">Другие свойства класса существуют, но не заполнены.</span><span class="sxs-lookup"><span data-stu-id="b77a7-189">Other properties of the class are present but they are not populated.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-190">-Query</span><span class="sxs-lookup"><span data-stu-id="b77a7-190">-Query</span></span>

<span data-ttu-id="b77a7-191">Указывает запрос для выполнения на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="b77a7-191">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="b77a7-192">Если указанное значение содержит двойные кавычки `"` , одинарные кавычки `'` или обратную косую черту `\` , эти символы необходимо заключить в escape-символ обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="b77a7-192">If the value specified contains double quotes `"`, single quotes `'`, or a backslash `\`, you must escape those characters by prefixing them with the backslash character.</span></span> <span data-ttu-id="b77a7-193">Если указанное значение использует оператор WQL **Like** , то необходимо экранировать следующие символы, заключив их в квадратные скобки `[]` : процент `%` , символ подчеркивания `_` или открывающую квадратную скобку `[` .</span><span class="sxs-lookup"><span data-stu-id="b77a7-193">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets `[]`: percent `%`, underscore `_`, or opening square bracket `[`.</span></span>

<span data-ttu-id="b77a7-194">Нельзя использовать запрос метаданных для получения списка классов или запроса события.</span><span class="sxs-lookup"><span data-stu-id="b77a7-194">You cannot use a metadata query to retrieve a list of classes or an event query.</span></span> <span data-ttu-id="b77a7-195">Чтобы получить список классов, используйте `Get-CimClass` командлет.</span><span class="sxs-lookup"><span data-stu-id="b77a7-195">To retrieve a list of classes, use the `Get-CimClass` cmdlet.</span></span> <span data-ttu-id="b77a7-196">Чтобы получить запрос события, используйте `Register-CimIndicationEvent` командлет.</span><span class="sxs-lookup"><span data-stu-id="b77a7-196">To retrieve an event query, use the `Register-CimIndicationEvent` cmdlet.</span></span>

<span data-ttu-id="b77a7-197">Диалект запроса можно указать с помощью параметра **куеридиалект** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-197">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-198">-Куеридиалект</span><span class="sxs-lookup"><span data-stu-id="b77a7-198">-QueryDialect</span></span>

<span data-ttu-id="b77a7-199">Указывает язык запросов, используемый для параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="b77a7-199">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="b77a7-200">Допустимые значения для этого параметра: **WQL** или **CQL**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-200">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="b77a7-201">Значение по умолчанию — **WQL**.</span><span class="sxs-lookup"><span data-stu-id="b77a7-201">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-202">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="b77a7-202">-ResourceUri</span></span>

<span data-ttu-id="b77a7-203">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="b77a7-203">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="b77a7-204">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b77a7-204">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b77a7-205">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b77a7-205">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="b77a7-206">Пример:</span><span class="sxs-lookup"><span data-stu-id="b77a7-206">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="b77a7-207">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="b77a7-207">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="b77a7-208">**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="b77a7-208">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="b77a7-209">Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .</span><span class="sxs-lookup"><span data-stu-id="b77a7-209">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="b77a7-210">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="b77a7-210">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-211">-Shallow</span><span class="sxs-lookup"><span data-stu-id="b77a7-211">-Shallow</span></span>

<span data-ttu-id="b77a7-212">Указывает, что экземпляры класса возвращаются без включения экземпляров каких-либо дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="b77a7-212">Indicates that the instances of a class are returned without including the instances of any child classes.</span></span> <span data-ttu-id="b77a7-213">По умолчанию командлет возвращает экземпляры класса и его дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="b77a7-213">By default, the cmdlet returns the instances of a class and its child classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b77a7-214">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b77a7-214">CommonParameters</span></span>

<span data-ttu-id="b77a7-215">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b77a7-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b77a7-216">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b77a7-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b77a7-217">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b77a7-217">INPUTS</span></span>

### <span data-ttu-id="b77a7-218">Экземпляр CIM</span><span class="sxs-lookup"><span data-stu-id="b77a7-218">CIM Instance</span></span>

<span data-ttu-id="b77a7-219">Этот командлет принимает входные объекты, указанные с помощью параметра InputObject.</span><span class="sxs-lookup"><span data-stu-id="b77a7-219">This cmdlet accepts an input objects specified with the InputObject parameter.</span></span>

## <span data-ttu-id="b77a7-220">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b77a7-220">OUTPUTS</span></span>

### <span data-ttu-id="b77a7-221">Экземпляр CIM</span><span class="sxs-lookup"><span data-stu-id="b77a7-221">CIM Instance</span></span>

<span data-ttu-id="b77a7-222">Этот командлет возвращает один или несколько объектов экземпляра CIM, представляющих моментальный снимок экземпляров CIM на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="b77a7-222">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances on the CIM server.</span></span>

## <span data-ttu-id="b77a7-223">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b77a7-223">NOTES</span></span>

## <span data-ttu-id="b77a7-224">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b77a7-224">RELATED LINKS</span></span>

[<span data-ttu-id="b77a7-225">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b77a7-225">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="b77a7-226">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="b77a7-226">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)

[<span data-ttu-id="b77a7-227">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="b77a7-227">Get-CimClass</span></span>](Get-CimClass.md)

[<span data-ttu-id="b77a7-228">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="b77a7-228">Invoke-CimMethod</span></span>](invoke-cimmethod.md)

[<span data-ttu-id="b77a7-229">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b77a7-229">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="b77a7-230">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="b77a7-230">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)

[<span data-ttu-id="b77a7-231">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b77a7-231">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="b77a7-232">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b77a7-232">Set-CimInstance</span></span>](Set-CimInstance.md)

