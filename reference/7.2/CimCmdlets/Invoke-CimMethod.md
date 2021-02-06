---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 1217e07d09213d7c0e223129207c085b9ba2d48d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603318"
---
# <span data-ttu-id="0b96b-102">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="0b96b-102">Invoke-CimMethod</span></span>

## <span data-ttu-id="0b96b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0b96b-103">SYNOPSIS</span></span>
<span data-ttu-id="0b96b-104">Вызывает метод класса CIM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-104">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="0b96b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b96b-105">SYNTAX</span></span>

### <span data-ttu-id="0b96b-106">Класснамекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0b96b-106">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0b96b-107">класснамесессионсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-107">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0b96b-108">ресаурцеурикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-108">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0b96b-109">Циминстанцесессионсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-109">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b96b-110">Циминстанцекомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-110">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b96b-111">ресаурцеурисессионсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-111">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0b96b-112">Цимкласскомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-112">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b96b-113">Цимкласссессионсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-113">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b96b-114">куерикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-114">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b96b-115">куерисессионсет</span><span class="sxs-lookup"><span data-stu-id="0b96b-115">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0b96b-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b96b-116">DESCRIPTION</span></span>

<span data-ttu-id="0b96b-117">`Invoke-CimMethod`Командлет вызывает метод класса CIM или экземпляра CIM, используя пары "имя-значение", заданные параметром **arguments** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-117">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="0b96b-118">Если параметр **InputObject** не указан, командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="0b96b-118">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="0b96b-119">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-119">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="0b96b-120">Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-120">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="0b96b-121">Если указан параметр **InputObject** , командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="0b96b-121">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="0b96b-122">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , то этот командлет использует сеанс CIM или имя компьютера из входного объекта.</span><span class="sxs-lookup"><span data-stu-id="0b96b-122">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="0b96b-123">Если указан параметр **ComputerName** или **CimSession** , то этот командлет использует либо значение параметра **CimSession** , либо значение параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-123">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="0b96b-124">Это не распространенный сценарий.</span><span class="sxs-lookup"><span data-stu-id="0b96b-124">This is not a common scenario.</span></span>

## <span data-ttu-id="0b96b-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b96b-125">EXAMPLES</span></span>

### <span data-ttu-id="0b96b-126">Пример 1. вызов метода</span><span class="sxs-lookup"><span data-stu-id="0b96b-126">Example 1: Invoke a method</span></span>

<span data-ttu-id="0b96b-127">В этом примере вызывается метод **Terminate** класса **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-127">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="0b96b-128">Пример 2. вызов метода с помощью объекта экземпляра CIM</span><span class="sxs-lookup"><span data-stu-id="0b96b-128">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="0b96b-129">Этот пример извлекает объект экземпляра CIM и сохраняет его в переменной с именем `$x` с помощью `Get-CimInstance` командлета.</span><span class="sxs-lookup"><span data-stu-id="0b96b-129">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="0b96b-130">Содержимое переменной затем используется в качестве **InputObject** для `Invoke-CimMethod` командлета.</span><span class="sxs-lookup"><span data-stu-id="0b96b-130">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="0b96b-131">Для **CimInstance** вызывается метод- **owner** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-131">The **GetOwner** method is invoked for the **CimInstance**.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="0b96b-132">Пример 3. вызов статического метода с помощью аргументов</span><span class="sxs-lookup"><span data-stu-id="0b96b-132">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="0b96b-133">В этом примере вызывается метод **CREATE** с именем, используя параметр **arguments** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-133">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="0b96b-134">Пример 4. Проверка на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="0b96b-134">Example 4: Client-side validation</span></span>

<span data-ttu-id="0b96b-135">В этом примере выполняется проверка на стороне клиента для метода **XYZ** путем передачи объекта **Цимкласс** в `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="0b96b-135">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="0b96b-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b96b-136">PARAMETERS</span></span>

### <span data-ttu-id="0b96b-137">-Arguments</span><span class="sxs-lookup"><span data-stu-id="0b96b-137">-Arguments</span></span>

<span data-ttu-id="0b96b-138">Задает параметры для передачи в вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="0b96b-138">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="0b96b-139">Укажите значения для этого параметра в виде пар "имя-значение", хранящихся в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="0b96b-139">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="0b96b-140">Порядок введенных значений не важен.</span><span class="sxs-lookup"><span data-stu-id="0b96b-140">The order of the values entered isn't important.</span></span>

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

### <span data-ttu-id="0b96b-141">-Цимкласс</span><span class="sxs-lookup"><span data-stu-id="0b96b-141">-CimClass</span></span>

<span data-ttu-id="0b96b-142">Указывает объект класса CIM, представляющий определение класса CIM на сервере.</span><span class="sxs-lookup"><span data-stu-id="0b96b-142">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="0b96b-143">Используйте этот параметр при вызове статического метода класса.</span><span class="sxs-lookup"><span data-stu-id="0b96b-143">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="0b96b-144">С помощью `Get-CimClass` командлета можно получить определение класса с сервера.</span><span class="sxs-lookup"><span data-stu-id="0b96b-144">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="0b96b-145">Использование этого параметра приводит к повышению допустимости проверки схемы на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="0b96b-145">Using this parameter results in better client side schema validations.</span></span>

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

### <span data-ttu-id="0b96b-146">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0b96b-146">-CimSession</span></span>

<span data-ttu-id="0b96b-147">Выполняет команду с помощью указанного сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-147">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="0b96b-148">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="0b96b-148">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="0b96b-149">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="0b96b-149">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="0b96b-150">-ClassName</span><span class="sxs-lookup"><span data-stu-id="0b96b-150">-ClassName</span></span>

<span data-ttu-id="0b96b-151">Указывает имя класса CIM, для которого выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="0b96b-151">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="0b96b-152">Этот параметр используется только для статических методов.</span><span class="sxs-lookup"><span data-stu-id="0b96b-152">This parameter is only used for static methods.</span></span> <span data-ttu-id="0b96b-153">Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="0b96b-153">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="0b96b-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0b96b-154">-ComputerName</span></span>

<span data-ttu-id="0b96b-155">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-155">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="0b96b-156">Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="0b96b-156">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="0b96b-157">При использовании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="0b96b-157">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="0b96b-158">В противном случае командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-158">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="0b96b-159">Подключение с помощью сеанса CIM для повышения производительности при выполнении нескольких операций на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b96b-159">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

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

### <span data-ttu-id="0b96b-160">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0b96b-160">-InputObject</span></span>

<span data-ttu-id="0b96b-161">Указывает объект экземпляра CIM, используемый в качестве входных данных для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="0b96b-161">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="0b96b-162">Этот параметр может использоваться только для вызова методов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0b96b-162">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="0b96b-163">Чтобы вызвать статические методы класса, используйте параметр **класса** или параметр **Цимкласс** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-163">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="0b96b-164">-Имя_метода</span><span class="sxs-lookup"><span data-stu-id="0b96b-164">-MethodName</span></span>

<span data-ttu-id="0b96b-165">Указывает имя вызываемого метода CIM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-165">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="0b96b-166">Этот параметр является обязательным и не может быть NULL или пустым.</span><span class="sxs-lookup"><span data-stu-id="0b96b-166">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="0b96b-167">Чтобы вызвать статический метод класса CIM, используйте параметр **className** или **Цимкласс** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-167">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="0b96b-168">-Namespace</span><span class="sxs-lookup"><span data-stu-id="0b96b-168">-Namespace</span></span>

<span data-ttu-id="0b96b-169">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="0b96b-169">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="0b96b-170">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="0b96b-170">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="0b96b-171">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="0b96b-171">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0b96b-172">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="0b96b-172">-OperationTimeoutSec</span></span>

<span data-ttu-id="0b96b-173">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="0b96b-173">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="0b96b-174">По умолчанию значение равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="0b96b-174">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="0b96b-175">Если параметр **оператионтимеаутсек** имеет значение, меньшее, чем время ожидания попытки подключения по умолчанию (3 минуты), сетевые сбои, которые больше, чем значение параметра **оператионтимеаутсек** , не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="0b96b-175">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="0b96b-176">-Query</span><span class="sxs-lookup"><span data-stu-id="0b96b-176">-Query</span></span>

<span data-ttu-id="0b96b-177">Указывает запрос для выполнения на CIM-сервере.</span><span class="sxs-lookup"><span data-stu-id="0b96b-177">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="0b96b-178">Метод вызывается для экземпляров, полученных в результате запроса.</span><span class="sxs-lookup"><span data-stu-id="0b96b-178">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="0b96b-179">Диалект запроса можно указать с помощью параметра **куеридиалект** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-179">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="0b96b-180">Если указанное значение содержит двойные кавычки ( `"` ), одинарные кавычки ( `'` ) или обратную косую черту ( `\` ), эти символы необходимо заключить в escape-символ обратной косой черты ( `\` ).</span><span class="sxs-lookup"><span data-stu-id="0b96b-180">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="0b96b-181">Если указанное значение использует оператор WQL LIKE, необходимо экранировать следующие символы, заключив их в квадратные скобки ( `[]` ): percent ( `%` ), символ подчеркивания ( `_` ) или открывающую квадратную скобку ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="0b96b-181">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

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

### <span data-ttu-id="0b96b-182">-Куеридиалект</span><span class="sxs-lookup"><span data-stu-id="0b96b-182">-QueryDialect</span></span>

<span data-ttu-id="0b96b-183">Указывает язык запросов, используемый для параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="0b96b-183">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="0b96b-184">Допустимые значения для этого параметра: **WQL** или **CQL**.</span><span class="sxs-lookup"><span data-stu-id="0b96b-184">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span>

<span data-ttu-id="0b96b-185">Значение по умолчанию — **WQL**.</span><span class="sxs-lookup"><span data-stu-id="0b96b-185">The default value is **WQL**.</span></span>

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

### <span data-ttu-id="0b96b-186">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="0b96b-186">-ResourceUri</span></span>

<span data-ttu-id="0b96b-187">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="0b96b-187">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="0b96b-188">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b96b-188">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="0b96b-189">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="0b96b-189">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="0b96b-190">Пример:</span><span class="sxs-lookup"><span data-stu-id="0b96b-190">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="0b96b-191">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="0b96b-191">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="0b96b-192">**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="0b96b-192">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="0b96b-193">При указании этого параметра без указания параметра **ComputerName** или при указании сеанса CIM, созданного с помощью протокола DCOM, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="0b96b-193">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="0b96b-194">Протокол DCOM не поддерживает параметр **resourceUri** .</span><span class="sxs-lookup"><span data-stu-id="0b96b-194">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="0b96b-195">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="0b96b-195">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0b96b-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0b96b-196">-Confirm</span></span>

<span data-ttu-id="0b96b-197">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0b96b-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0b96b-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0b96b-198">-WhatIf</span></span>

<span data-ttu-id="0b96b-199">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0b96b-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0b96b-200">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0b96b-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0b96b-201">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0b96b-201">CommonParameters</span></span>

<span data-ttu-id="0b96b-202">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b96b-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b96b-203">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0b96b-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0b96b-204">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0b96b-204">INPUTS</span></span>

### <span data-ttu-id="0b96b-205">Класс CIM</span><span class="sxs-lookup"><span data-stu-id="0b96b-205">CIM class</span></span>

<span data-ttu-id="0b96b-206">Этот командлет принимает класс CIM в качестве входного объекта.</span><span class="sxs-lookup"><span data-stu-id="0b96b-206">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="0b96b-207">Экземпляр CIM</span><span class="sxs-lookup"><span data-stu-id="0b96b-207">CIM instance</span></span>

<span data-ttu-id="0b96b-208">Этот командлет принимает экземпляр CIM в качестве входного объекта.</span><span class="sxs-lookup"><span data-stu-id="0b96b-208">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="0b96b-209">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0b96b-209">OUTPUTS</span></span>

### <span data-ttu-id="0b96b-210">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="0b96b-210">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="0b96b-211">Этот командлет возвращает объект.</span><span class="sxs-lookup"><span data-stu-id="0b96b-211">This cmdlet returns an object.</span></span>

## <span data-ttu-id="0b96b-212">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0b96b-212">NOTES</span></span>

## <span data-ttu-id="0b96b-213">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0b96b-213">RELATED LINKS</span></span>

[<span data-ttu-id="0b96b-214">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="0b96b-214">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="0b96b-215">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="0b96b-215">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="0b96b-216">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="0b96b-216">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="0b96b-217">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="0b96b-217">New-CimSession</span></span>](New-CimSession.md)

