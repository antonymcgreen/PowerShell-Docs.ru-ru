---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: 5d1394a6689471e3ea65bcbdc87ec0ef5e1fc6a6
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229754"
---
# <span data-ttu-id="c519e-103">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="c519e-103">New-CimInstance</span></span>

## <span data-ttu-id="c519e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c519e-104">SYNOPSIS</span></span>
<span data-ttu-id="c519e-105">Создает экземпляр CIM.</span><span class="sxs-lookup"><span data-stu-id="c519e-105">Creates a CIM instance.</span></span>

## <span data-ttu-id="c519e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c519e-106">SYNTAX</span></span>

### <span data-ttu-id="c519e-107">Класснамекомпутерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c519e-107">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c519e-108">класснамесессионсет</span><span class="sxs-lookup"><span data-stu-id="c519e-108">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c519e-109">ресаурцеурисессионсет</span><span class="sxs-lookup"><span data-stu-id="c519e-109">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c519e-110">ресаурцеурикомпутерсет</span><span class="sxs-lookup"><span data-stu-id="c519e-110">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c519e-111">Цимкласссессионсет</span><span class="sxs-lookup"><span data-stu-id="c519e-111">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c519e-112">Цимкласскомпутерсет</span><span class="sxs-lookup"><span data-stu-id="c519e-112">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c519e-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c519e-113">DESCRIPTION</span></span>

<span data-ttu-id="c519e-114">`New-CimInstance`Командлет создает экземпляр класса CIM на основе определения класса либо на локальном компьютере, либо на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c519e-114">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="c519e-115">По умолчанию `New-CimInstance` командлет создает экземпляр на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c519e-115">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="c519e-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="c519e-116">EXAMPLES</span></span>

### <span data-ttu-id="c519e-117">Пример 1. Создание экземпляра класса CIM</span><span class="sxs-lookup"><span data-stu-id="c519e-117">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="c519e-118">В этом примере создается экземпляр класса CIM с именем win32_environment в пространстве имен root/cimv2 на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c519e-118">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="c519e-119">Проверка на стороне клиента не выполняется, если класс не существует, свойства неверны или сервер отклоняет вызов.</span><span class="sxs-lookup"><span data-stu-id="c519e-119">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="c519e-120">Если экземпляр создан успешно, командлет выводит только что созданный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c519e-120">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="c519e-121">Пример 2. Создание экземпляра класса CIM с помощью схемы класса</span><span class="sxs-lookup"><span data-stu-id="c519e-121">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="c519e-122">В этом примере извлекается объект класса CIM и сохраняется в переменной с именем `$class` .</span><span class="sxs-lookup"><span data-stu-id="c519e-122">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="c519e-123">После этого содержимое переменной передается в `New-CimInstance` командлет.</span><span class="sxs-lookup"><span data-stu-id="c519e-123">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="c519e-124">Пример 3. Создание динамического экземпляра на клиенте</span><span class="sxs-lookup"><span data-stu-id="c519e-124">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="c519e-125">В этом примере создается динамический экземпляр класса CIM с именем **Win32_Process** на клиентском компьютере без получения экземпляра с сервера.</span><span class="sxs-lookup"><span data-stu-id="c519e-125">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="c519e-126">Новый экземпляр хранится в переменной `$a` .</span><span class="sxs-lookup"><span data-stu-id="c519e-126">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="c519e-127">Этот динамический экземпляр можно использовать для выполнения операций, если экземпляр с этим ключом существует на сервере.</span><span class="sxs-lookup"><span data-stu-id="c519e-127">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

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

<span data-ttu-id="c519e-128">`Get-CimInstance`Затем командлет извлекает определенный единственный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c519e-128">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="c519e-129">`Invoke-CimMethod`Командлет вызывает метод метода **GetOwner** with для полученного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c519e-129">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="c519e-130">Пример 4. Создание экземпляра для класса CIM определенного пространства имен</span><span class="sxs-lookup"><span data-stu-id="c519e-130">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="c519e-131">В этом примере получается экземпляр класса CIM с именем **MSFT_Something** в пространстве имен **root/где** и сохраняется в переменной с именем `$class` .</span><span class="sxs-lookup"><span data-stu-id="c519e-131">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="c519e-132">Переменная передается в `New-CimInstance` командлет для создания нового экземпляра CIM и выполнения проверки на стороне клиента в новом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="c519e-132">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="c519e-133">В этом примере использование параметра **Цимкласс** вместо параметра **className** подтверждает, что **Prop1** и **Prop2** фактически существуют и что ключи помечены правильно.</span><span class="sxs-lookup"><span data-stu-id="c519e-133">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="c519e-134">Параметр **ComputerName** или **CimSession** нельзя использовать с параметром **клиентонли** .</span><span class="sxs-lookup"><span data-stu-id="c519e-134">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="c519e-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c519e-135">PARAMETERS</span></span>

### <span data-ttu-id="c519e-136">-Цимкласс</span><span class="sxs-lookup"><span data-stu-id="c519e-136">-CimClass</span></span>

<span data-ttu-id="c519e-137">Указывает объект класса CIM, представляющий тип экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c519e-137">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="c519e-138">Используйте `Get-CimClass` командлет, чтобы получить объявление класса с компьютера.</span><span class="sxs-lookup"><span data-stu-id="c519e-138">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="c519e-139">Использование этого параметра приводит к повышению допустимости проверки схемы на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="c519e-139">Using this parameter results in better client side schema validations.</span></span>

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

### <span data-ttu-id="c519e-140">-CimSession</span><span class="sxs-lookup"><span data-stu-id="c519e-140">-CimSession</span></span>

<span data-ttu-id="c519e-141">Выполняет команду с помощью указанного сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="c519e-141">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="c519e-142">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` `Get-CimSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="c519e-142">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="c519e-143">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="c519e-143">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="c519e-144">-ClassName</span><span class="sxs-lookup"><span data-stu-id="c519e-144">-ClassName</span></span>

<span data-ttu-id="c519e-145">Указывает имя класса CIM, в котором операция создает экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c519e-145">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="c519e-146">Примечание. для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="c519e-146">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="c519e-147">-Клиентонли</span><span class="sxs-lookup"><span data-stu-id="c519e-147">-ClientOnly</span></span>

<span data-ttu-id="c519e-148">Указывает, что экземпляр создается только в PowerShell без перехода на CIM-сервер.</span><span class="sxs-lookup"><span data-stu-id="c519e-148">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="c519e-149">Этот параметр можно использовать для создания экземпляра CIM в памяти, который будет использоваться в последующих операциях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c519e-149">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

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

### <span data-ttu-id="c519e-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c519e-150">-ComputerName</span></span>

<span data-ttu-id="c519e-151">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="c519e-151">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="c519e-152">Вы можете указать полное доменное имя, имя NetBIOS или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="c519e-152">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="c519e-153">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WSMan.</span><span class="sxs-lookup"><span data-stu-id="c519e-153">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="c519e-154">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="c519e-154">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="c519e-155">Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="c519e-155">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="c519e-156">-Key</span><span class="sxs-lookup"><span data-stu-id="c519e-156">-Key</span></span>

<span data-ttu-id="c519e-157">Задает свойства, используемые в качестве ключей.</span><span class="sxs-lookup"><span data-stu-id="c519e-157">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="c519e-158">**CimSession** и **ComputerName** нельзя использовать, если указан **ключ** .</span><span class="sxs-lookup"><span data-stu-id="c519e-158">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

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

### <span data-ttu-id="c519e-159">-Namespace</span><span class="sxs-lookup"><span data-stu-id="c519e-159">-Namespace</span></span>

<span data-ttu-id="c519e-160">Задает пространство имен класса для нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c519e-160">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="c519e-161">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="c519e-161">The default namespace is **root/cimv2**.</span></span>
<span data-ttu-id="c519e-162">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="c519e-162">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="c519e-163">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="c519e-163">-OperationTimeoutSec</span></span>

<span data-ttu-id="c519e-164">Указывает период времени, в течение которого командлет ожидает ответа от сервера CIM.</span><span class="sxs-lookup"><span data-stu-id="c519e-164">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="c519e-165">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="c519e-165">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="c519e-166">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="c519e-166">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="c519e-167">-Property</span><span class="sxs-lookup"><span data-stu-id="c519e-167">-Property</span></span>

<span data-ttu-id="c519e-168">Задает свойства экземпляра CIM, используя хэш-таблицу (пары "имя-значение").</span><span class="sxs-lookup"><span data-stu-id="c519e-168">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="c519e-169">Если указан параметр **Цимкласс** , `New-CimInstance` командлет выполняет проверку свойства на клиенте, чтобы убедиться, что указанные свойства соответствуют объявлению класса на сервере.</span><span class="sxs-lookup"><span data-stu-id="c519e-169">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="c519e-170">Если параметр **Цимкласс** не указан, проверка свойства выполняется на сервере.</span><span class="sxs-lookup"><span data-stu-id="c519e-170">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

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

### <span data-ttu-id="c519e-171">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="c519e-171">-ResourceUri</span></span>

<span data-ttu-id="c519e-172">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="c519e-172">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="c519e-173">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c519e-173">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="c519e-174">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c519e-174">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="c519e-175">Пример:</span><span class="sxs-lookup"><span data-stu-id="c519e-175">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="c519e-176">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="c519e-176">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="c519e-177">**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="c519e-177">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="c519e-178">Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникнет ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .</span><span class="sxs-lookup"><span data-stu-id="c519e-178">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="c519e-179">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c519e-179">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="c519e-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c519e-180">-Confirm</span></span>

<span data-ttu-id="c519e-181">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c519e-181">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c519e-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c519e-182">-WhatIf</span></span>

<span data-ttu-id="c519e-183">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c519e-183">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c519e-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c519e-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c519e-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c519e-185">CommonParameters</span></span>

<span data-ttu-id="c519e-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c519e-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c519e-187">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c519e-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c519e-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c519e-188">INPUTS</span></span>

### <span data-ttu-id="c519e-189">Нет</span><span class="sxs-lookup"><span data-stu-id="c519e-189">None</span></span>

<span data-ttu-id="c519e-190">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="c519e-190">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="c519e-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c519e-191">OUTPUTS</span></span>

### <span data-ttu-id="c519e-192">System.Object</span><span class="sxs-lookup"><span data-stu-id="c519e-192">System.Object</span></span>

<span data-ttu-id="c519e-193">Этот командлет возвращает объект, содержащий сведения об экземпляре CIM.</span><span class="sxs-lookup"><span data-stu-id="c519e-193">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="c519e-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c519e-194">NOTES</span></span>

## <span data-ttu-id="c519e-195">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c519e-195">RELATED LINKS</span></span>

[<span data-ttu-id="c519e-196">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="c519e-196">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="c519e-197">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="c519e-197">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="c519e-198">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="c519e-198">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="c519e-199">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="c519e-199">Set-CimInstance</span></span>](Set-CimInstance.md)
