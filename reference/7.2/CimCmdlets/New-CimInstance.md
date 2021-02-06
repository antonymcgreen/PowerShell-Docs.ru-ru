---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d81117ad6885d660e31f031bd8134096db91b7da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601478"
---
# <span data-ttu-id="3a32e-102">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="3a32e-102">New-CimInstance</span></span>

## <span data-ttu-id="3a32e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3a32e-103">SYNOPSIS</span></span>
<span data-ttu-id="3a32e-104">Создает экземпляр CIM.</span><span class="sxs-lookup"><span data-stu-id="3a32e-104">Creates a CIM instance.</span></span>

## <span data-ttu-id="3a32e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a32e-105">SYNTAX</span></span>

### <span data-ttu-id="3a32e-106">Класснамекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3a32e-106">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a32e-107">класснамесессионсет</span><span class="sxs-lookup"><span data-stu-id="3a32e-107">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a32e-108">ресаурцеурисессионсет</span><span class="sxs-lookup"><span data-stu-id="3a32e-108">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a32e-109">ресаурцеурикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="3a32e-109">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a32e-110">Цимкласссессионсет</span><span class="sxs-lookup"><span data-stu-id="3a32e-110">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a32e-111">Цимкласскомпутерсет</span><span class="sxs-lookup"><span data-stu-id="3a32e-111">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3a32e-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a32e-112">DESCRIPTION</span></span>

<span data-ttu-id="3a32e-113">`New-CimInstance`Командлет создает экземпляр класса CIM на основе определения класса либо на локальном компьютере, либо на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-113">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="3a32e-114">По умолчанию `New-CimInstance` командлет создает экземпляр на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-114">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="3a32e-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="3a32e-115">EXAMPLES</span></span>

### <span data-ttu-id="3a32e-116">Пример 1. Создание экземпляра класса CIM</span><span class="sxs-lookup"><span data-stu-id="3a32e-116">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="3a32e-117">В этом примере создается экземпляр класса CIM с именем win32_environment в пространстве имен root/cimv2 на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-117">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="3a32e-118">Проверка на стороне клиента не выполняется, если класс не существует, свойства неверны или сервер отклоняет вызов.</span><span class="sxs-lookup"><span data-stu-id="3a32e-118">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="3a32e-119">Если экземпляр создан успешно, командлет выводит только что созданный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3a32e-119">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="3a32e-120">Пример 2. Создание экземпляра класса CIM с помощью схемы класса</span><span class="sxs-lookup"><span data-stu-id="3a32e-120">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="3a32e-121">В этом примере извлекается объект класса CIM и сохраняется в переменной с именем `$class` .</span><span class="sxs-lookup"><span data-stu-id="3a32e-121">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="3a32e-122">После этого содержимое переменной передается в `New-CimInstance` командлет.</span><span class="sxs-lookup"><span data-stu-id="3a32e-122">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="3a32e-123">Пример 3. Создание динамического экземпляра на клиенте</span><span class="sxs-lookup"><span data-stu-id="3a32e-123">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="3a32e-124">В этом примере создается динамический экземпляр класса CIM с именем **Win32_Process** на клиентском компьютере без получения экземпляра с сервера.</span><span class="sxs-lookup"><span data-stu-id="3a32e-124">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="3a32e-125">Новый экземпляр хранится в переменной `$a` .</span><span class="sxs-lookup"><span data-stu-id="3a32e-125">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="3a32e-126">Этот динамический экземпляр можно использовать для выполнения операций, если экземпляр с этим ключом существует на сервере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-126">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

```powershell
$a = New-CimInstance -ClassName Win32_Process -Property @{Handle=0} -Key Handle -ClientOnly
Get-CimInstance -CimInstance $a
Invoke-CimMethod -CimInstance $a -MethodName GetOwner
```

```Output
ProcessId Name                HandleCount WorkingSetSize VirtualSize
--------- ----                ----------- -------------- -----------
0         System Idle Process 0           8192           8192

Domain         :
ReturnValue    : 2
User           :
PSComputerName :
```

<span data-ttu-id="3a32e-127">`Get-CimInstance`Затем командлет извлекает определенный единственный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3a32e-127">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="3a32e-128">`Invoke-CimMethod`Командлет вызывает метод метода  with для полученного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3a32e-128">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="3a32e-129">Пример 4. Создание экземпляра для класса CIM определенного пространства имен</span><span class="sxs-lookup"><span data-stu-id="3a32e-129">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="3a32e-130">В этом примере получается экземпляр класса CIM с именем **MSFT_Something** в пространстве имен **root/где** и сохраняется в переменной с именем `$class` .</span><span class="sxs-lookup"><span data-stu-id="3a32e-130">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="3a32e-131">Переменная передается в `New-CimInstance` командлет для создания нового экземпляра CIM и выполнения проверки на стороне клиента в новом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="3a32e-131">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="3a32e-132">В этом примере использование параметра **Цимкласс** вместо параметра **className** подтверждает, что **Prop1** и **Prop2** фактически существуют и что ключи помечены правильно.</span><span class="sxs-lookup"><span data-stu-id="3a32e-132">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="3a32e-133">Параметр **ComputerName** или **CimSession** нельзя использовать с параметром **клиентонли** .</span><span class="sxs-lookup"><span data-stu-id="3a32e-133">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="3a32e-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a32e-134">PARAMETERS</span></span>

### <span data-ttu-id="3a32e-135">-Цимкласс</span><span class="sxs-lookup"><span data-stu-id="3a32e-135">-CimClass</span></span>

<span data-ttu-id="3a32e-136">Указывает объект класса CIM, представляющий тип экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3a32e-136">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="3a32e-137">Используйте `Get-CimClass` командлет, чтобы получить объявление класса с компьютера.</span><span class="sxs-lookup"><span data-stu-id="3a32e-137">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="3a32e-138">Использование этого параметра приводит к повышению допустимости проверки схемы на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="3a32e-138">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassSessionSet, CimClassComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-139">-CimSession</span><span class="sxs-lookup"><span data-stu-id="3a32e-139">-CimSession</span></span>

<span data-ttu-id="3a32e-140">Выполняет команду с помощью указанного сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="3a32e-140">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="3a32e-141">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="3a32e-141">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="3a32e-142">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="3a32e-142">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, ResourceUriSessionSet, CimClassSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-143">-ClassName</span><span class="sxs-lookup"><span data-stu-id="3a32e-143">-ClassName</span></span>

<span data-ttu-id="3a32e-144">Указывает имя класса CIM, в котором операция создает экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3a32e-144">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="3a32e-145">Примечание. для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="3a32e-145">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="3a32e-146">-Клиентонли</span><span class="sxs-lookup"><span data-stu-id="3a32e-146">-ClientOnly</span></span>

<span data-ttu-id="3a32e-147">Указывает, что экземпляр создается только в PowerShell без перехода на CIM-сервер.</span><span class="sxs-lookup"><span data-stu-id="3a32e-147">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="3a32e-148">Этот параметр можно использовать для создания экземпляра CIM в памяти, который будет использоваться в последующих операциях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a32e-148">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, CimClassSessionSet, CimClassComputerSet
Aliases: Local

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3a32e-149">-ComputerName</span></span>

<span data-ttu-id="3a32e-150">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="3a32e-150">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="3a32e-151">Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="3a32e-151">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="3a32e-152">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WSMan.</span><span class="sxs-lookup"><span data-stu-id="3a32e-152">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="3a32e-153">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="3a32e-153">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="3a32e-154">Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="3a32e-154">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-155">-Key</span><span class="sxs-lookup"><span data-stu-id="3a32e-155">-Key</span></span>

<span data-ttu-id="3a32e-156">Задает свойства, используемые в качестве ключей.</span><span class="sxs-lookup"><span data-stu-id="3a32e-156">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="3a32e-157">**CimSession** и **ComputerName** нельзя использовать, если указан **ключ** .</span><span class="sxs-lookup"><span data-stu-id="3a32e-157">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-158">-Namespace</span><span class="sxs-lookup"><span data-stu-id="3a32e-158">-Namespace</span></span>

<span data-ttu-id="3a32e-159">Задает пространство имен класса для нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3a32e-159">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="3a32e-160">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="3a32e-160">The default namespace is **root/cimv2**.</span></span>
<span data-ttu-id="3a32e-161">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="3a32e-161">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-162">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="3a32e-162">-OperationTimeoutSec</span></span>

<span data-ttu-id="3a32e-163">Указывает период времени, в течение которого командлет ожидает ответа от сервера CIM.</span><span class="sxs-lookup"><span data-stu-id="3a32e-163">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="3a32e-164">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="3a32e-164">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="3a32e-165">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="3a32e-165">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="3a32e-166">-Property</span><span class="sxs-lookup"><span data-stu-id="3a32e-166">-Property</span></span>

<span data-ttu-id="3a32e-167">Задает свойства экземпляра CIM, используя хэш-таблицу (пары "имя-значение").</span><span class="sxs-lookup"><span data-stu-id="3a32e-167">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="3a32e-168">Если указан параметр **Цимкласс** , `New-CimInstance` командлет выполняет проверку свойства на клиенте, чтобы убедиться, что указанные свойства соответствуют объявлению класса на сервере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-168">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="3a32e-169">Если параметр **Цимкласс** не указан, проверка свойства выполняется на сервере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-169">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Arguments

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-170">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="3a32e-170">-ResourceUri</span></span>

<span data-ttu-id="3a32e-171">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="3a32e-171">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="3a32e-172">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a32e-172">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="3a32e-173">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="3a32e-173">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="3a32e-174">Пример:</span><span class="sxs-lookup"><span data-stu-id="3a32e-174">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="3a32e-175">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="3a32e-175">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="3a32e-176">**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="3a32e-176">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="3a32e-177">Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .</span><span class="sxs-lookup"><span data-stu-id="3a32e-177">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="3a32e-178">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3a32e-178">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3a32e-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3a32e-179">-Confirm</span></span>

<span data-ttu-id="3a32e-180">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3a32e-180">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3a32e-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3a32e-181">-WhatIf</span></span>

<span data-ttu-id="3a32e-182">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3a32e-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3a32e-183">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3a32e-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3a32e-184">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3a32e-184">CommonParameters</span></span>

<span data-ttu-id="3a32e-185">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a32e-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a32e-186">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3a32e-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3a32e-187">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3a32e-187">INPUTS</span></span>

### <span data-ttu-id="3a32e-188">None</span><span class="sxs-lookup"><span data-stu-id="3a32e-188">None</span></span>

<span data-ttu-id="3a32e-189">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="3a32e-189">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="3a32e-190">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3a32e-190">OUTPUTS</span></span>

### <span data-ttu-id="3a32e-191">System.Object</span><span class="sxs-lookup"><span data-stu-id="3a32e-191">System.Object</span></span>

<span data-ttu-id="3a32e-192">Этот командлет возвращает объект, содержащий сведения об экземпляре CIM.</span><span class="sxs-lookup"><span data-stu-id="3a32e-192">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="3a32e-193">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3a32e-193">NOTES</span></span>

## <span data-ttu-id="3a32e-194">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3a32e-194">RELATED LINKS</span></span>

[<span data-ttu-id="3a32e-195">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="3a32e-195">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="3a32e-196">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="3a32e-196">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="3a32e-197">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="3a32e-197">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="3a32e-198">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="3a32e-198">Set-CimInstance</span></span>](Set-CimInstance.md)

