---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 328abb5776366f6e2d9b5106c93337f5d45533ed
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229721"
---
# <span data-ttu-id="0e333-103">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="0e333-103">Invoke-CimMethod</span></span>

## <span data-ttu-id="0e333-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0e333-104">SYNOPSIS</span></span>
<span data-ttu-id="0e333-105">Вызывает метод класса CIM.</span><span class="sxs-lookup"><span data-stu-id="0e333-105">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="0e333-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e333-106">SYNTAX</span></span>

### <span data-ttu-id="0e333-107">Класснамекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0e333-107">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0e333-108">класснамесессионсет</span><span class="sxs-lookup"><span data-stu-id="0e333-108">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0e333-109">ресаурцеурикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0e333-109">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0e333-110">Циминстанцесессионсет</span><span class="sxs-lookup"><span data-stu-id="0e333-110">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e333-111">Циминстанцекомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0e333-111">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e333-112">ресаурцеурисессионсет</span><span class="sxs-lookup"><span data-stu-id="0e333-112">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0e333-113">Цимкласскомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0e333-113">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e333-114">Цимкласссессионсет</span><span class="sxs-lookup"><span data-stu-id="0e333-114">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e333-115">куерикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0e333-115">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e333-116">куерисессионсет</span><span class="sxs-lookup"><span data-stu-id="0e333-116">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e333-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e333-117">DESCRIPTION</span></span>

<span data-ttu-id="0e333-118">`Invoke-CimMethod`Командлет вызывает метод класса CIM или экземпляра CIM, используя пары "имя-значение", заданные параметром **arguments** .</span><span class="sxs-lookup"><span data-stu-id="0e333-118">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="0e333-119">Если параметр **InputObject** не указан, командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="0e333-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="0e333-120">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.</span><span class="sxs-lookup"><span data-stu-id="0e333-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="0e333-121">Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="0e333-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="0e333-122">Если указан параметр **InputObject** , командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="0e333-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="0e333-123">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.</span><span class="sxs-lookup"><span data-stu-id="0e333-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="0e333-124">Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра **CimSession** , либо значение параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="0e333-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="0e333-125">Это не распространенный сценарий.</span><span class="sxs-lookup"><span data-stu-id="0e333-125">This is not a common scenario.</span></span>

## <span data-ttu-id="0e333-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="0e333-126">EXAMPLES</span></span>

### <span data-ttu-id="0e333-127">Пример 1. вызов метода</span><span class="sxs-lookup"><span data-stu-id="0e333-127">Example 1: Invoke a method</span></span>

<span data-ttu-id="0e333-128">В этом примере вызывается метод **Terminate** класса **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="0e333-128">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="0e333-129">Пример 2. вызов метода с помощью объекта экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="0e333-129">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="0e333-130">Этот пример извлекает объект экземпляра CIM и сохраняет его в переменной с именем `$x` с помощью `Get-CimInstance` командлета.</span><span class="sxs-lookup"><span data-stu-id="0e333-130">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="0e333-131">Содержимое переменной затем используется в качестве **InputObject** для `Invoke-CimMethod` командлета.</span><span class="sxs-lookup"><span data-stu-id="0e333-131">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="0e333-132">Для **CimInstance** вызывается метод- **owner** .</span><span class="sxs-lookup"><span data-stu-id="0e333-132">The **GetOwner** method is invoked for the **CimInstance** .</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="0e333-133">Пример 3. вызов статического метода с помощью аргументов</span><span class="sxs-lookup"><span data-stu-id="0e333-133">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="0e333-134">В этом примере вызывается метод **CREATE** с именем, используя параметр **arguments** .</span><span class="sxs-lookup"><span data-stu-id="0e333-134">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="0e333-135">Пример 4. Проверка на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="0e333-135">Example 4: Client-side validation</span></span>

<span data-ttu-id="0e333-136">В этом примере выполняется проверка на стороне клиента для метода **XYZ** путем передачи объекта **Цимкласс** в `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="0e333-136">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="0e333-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e333-137">PARAMETERS</span></span>

### <span data-ttu-id="0e333-138">-Arguments</span><span class="sxs-lookup"><span data-stu-id="0e333-138">-Arguments</span></span>

<span data-ttu-id="0e333-139">Задает параметры для передачи в вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="0e333-139">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="0e333-140">Укажите значения для этого параметра в виде пар "имя-значение", хранящихся в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="0e333-140">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="0e333-141">Порядок введенных значений не важен.</span><span class="sxs-lookup"><span data-stu-id="0e333-141">The order of the values entered isn't important.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-142">-Цимкласс</span><span class="sxs-lookup"><span data-stu-id="0e333-142">-CimClass</span></span>

<span data-ttu-id="0e333-143">Указывает объект класса CIM, представляющий определение класса CIM на сервере.</span><span class="sxs-lookup"><span data-stu-id="0e333-143">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="0e333-144">Используйте этот параметр при вызове статического метода класса.</span><span class="sxs-lookup"><span data-stu-id="0e333-144">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="0e333-145">С помощью `Get-CimClass` командлета можно получить определение класса с сервера.</span><span class="sxs-lookup"><span data-stu-id="0e333-145">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="0e333-146">Использование этого параметра приводит к повышению допустимости проверки схемы на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="0e333-146">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-147">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0e333-147">-CimSession</span></span>

<span data-ttu-id="0e333-148">Выполняет команду с помощью указанного сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="0e333-148">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="0e333-149">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="0e333-149">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="0e333-150">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="0e333-150">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-151">-ClassName</span><span class="sxs-lookup"><span data-stu-id="0e333-151">-ClassName</span></span>

<span data-ttu-id="0e333-152">Указывает имя класса CIM, для которого выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="0e333-152">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="0e333-153">Этот параметр используется только для статических методов.</span><span class="sxs-lookup"><span data-stu-id="0e333-153">This parameter is only used for static methods.</span></span> <span data-ttu-id="0e333-154">Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="0e333-154">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0e333-155">-ComputerName</span></span>

<span data-ttu-id="0e333-156">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="0e333-156">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="0e333-157">Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="0e333-157">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="0e333-158">При использовании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="0e333-158">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="0e333-159">В противном случае командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="0e333-159">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="0e333-160">Подключение с помощью сеанса CIM для повышения производительности при выполнении нескольких операций на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0e333-160">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0e333-161">-InputObject</span></span>

<span data-ttu-id="0e333-162">Указывает объект экземпляра CIM, используемый в качестве входных данных для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="0e333-162">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="0e333-163">Этот параметр может использоваться только для вызова методов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0e333-163">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="0e333-164">Чтобы вызвать статические методы класса, используйте параметр **класса** или параметр **Цимкласс** .</span><span class="sxs-lookup"><span data-stu-id="0e333-164">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="0e333-165">-Имя_метода</span><span class="sxs-lookup"><span data-stu-id="0e333-165">-MethodName</span></span>

<span data-ttu-id="0e333-166">Указывает имя вызываемого метода CIM.</span><span class="sxs-lookup"><span data-stu-id="0e333-166">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="0e333-167">Этот параметр является обязательным и не может быть NULL или пустым.</span><span class="sxs-lookup"><span data-stu-id="0e333-167">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="0e333-168">Чтобы вызвать статический метод класса CIM, используйте параметр **className** или **Цимкласс** .</span><span class="sxs-lookup"><span data-stu-id="0e333-168">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-169">-Namespace</span><span class="sxs-lookup"><span data-stu-id="0e333-169">-Namespace</span></span>

<span data-ttu-id="0e333-170">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="0e333-170">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="0e333-171">Пространством имен по умолчанию является **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="0e333-171">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="0e333-172">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="0e333-172">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-173">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="0e333-173">-OperationTimeoutSec</span></span>

<span data-ttu-id="0e333-174">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="0e333-174">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="0e333-175">По умолчанию значение равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="0e333-175">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="0e333-176">Если параметр **оператионтимеаутсек** имеет значение, меньшее, чем время ожидания попытки подключения по умолчанию (3 минуты), сетевые сбои, которые больше, чем значение параметра **оператионтимеаутсек** , не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="0e333-176">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="0e333-177">-Query</span><span class="sxs-lookup"><span data-stu-id="0e333-177">-Query</span></span>

<span data-ttu-id="0e333-178">Указывает запрос для выполнения на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="0e333-178">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="0e333-179">Метод вызывается для экземпляров, полученных в результате запроса.</span><span class="sxs-lookup"><span data-stu-id="0e333-179">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="0e333-180">Диалект запроса можно указать с помощью параметра **куеридиалект** .</span><span class="sxs-lookup"><span data-stu-id="0e333-180">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="0e333-181">Если указанное значение содержит двойные кавычки ( `"` ), одинарные кавычки ( `'` ) или обратную косую черту ( `\` ), эти символы необходимо заключить в escape-символ обратной косой черты ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="0e333-181">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="0e333-182">Если указанное значение использует оператор WQL LIKE, необходимо экранировать следующие символы, заключив их в квадратные скобки ( `[]` ): percent ( `%` ), символ подчеркивания ( `_` ) или открывающую квадратную скобку ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="0e333-182">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-183">-Куеридиалект</span><span class="sxs-lookup"><span data-stu-id="0e333-183">-QueryDialect</span></span>

<span data-ttu-id="0e333-184">Указывает язык запросов, используемый для параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="0e333-184">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="0e333-185">Допустимые значения для этого параметра: **WQL** или **CQL** .</span><span class="sxs-lookup"><span data-stu-id="0e333-185">The acceptable values for this parameter are: **WQL** or **CQL** .</span></span>

<span data-ttu-id="0e333-186">Значение по умолчанию — **WQL** .</span><span class="sxs-lookup"><span data-stu-id="0e333-186">The default value is **WQL** .</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-187">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="0e333-187">-ResourceUri</span></span>

<span data-ttu-id="0e333-188">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="0e333-188">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="0e333-189">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0e333-189">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="0e333-190">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="0e333-190">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="0e333-191">Пример:</span><span class="sxs-lookup"><span data-stu-id="0e333-191">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="0e333-192">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="0e333-192">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="0e333-193">**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="0e333-193">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="0e333-194">При указании этого параметра без указания параметра **ComputerName** или при указании сеанса CIM, созданного с помощью протокола DCOM, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="0e333-194">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="0e333-195">Протокол DCOM не поддерживает параметр **resourceUri** .</span><span class="sxs-lookup"><span data-stu-id="0e333-195">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="0e333-196">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="0e333-196">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0e333-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e333-197">-Confirm</span></span>

<span data-ttu-id="0e333-198">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0e333-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e333-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e333-199">-WhatIf</span></span>

<span data-ttu-id="0e333-200">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0e333-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0e333-201">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0e333-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e333-202">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0e333-202">CommonParameters</span></span>

<span data-ttu-id="0e333-203">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e333-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e333-204">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0e333-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0e333-205">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0e333-205">INPUTS</span></span>

### <span data-ttu-id="0e333-206">Microsoft. Management. Infrastructure. Цимкласс</span><span class="sxs-lookup"><span data-stu-id="0e333-206">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="0e333-207">Этот командлет принимает класс CIM в качестве входного объекта.</span><span class="sxs-lookup"><span data-stu-id="0e333-207">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="0e333-208">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="0e333-208">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="0e333-209">Этот командлет принимает экземпляр CIM в качестве входного объекта.</span><span class="sxs-lookup"><span data-stu-id="0e333-209">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="0e333-210">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0e333-210">OUTPUTS</span></span>

### <span data-ttu-id="0e333-211">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="0e333-211">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="0e333-212">Этот командлет возвращает объект.</span><span class="sxs-lookup"><span data-stu-id="0e333-212">This cmdlet returns an object.</span></span>

## <span data-ttu-id="0e333-213">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0e333-213">NOTES</span></span>

## <span data-ttu-id="0e333-214">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0e333-214">RELATED LINKS</span></span>

[<span data-ttu-id="0e333-215">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="0e333-215">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="0e333-216">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="0e333-216">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="0e333-217">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="0e333-217">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="0e333-218">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="0e333-218">New-CimSession</span></span>](New-CimSession.md)
