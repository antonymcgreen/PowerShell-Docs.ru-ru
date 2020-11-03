---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: 10790507b24bc4212db062589cf76d5260554b30
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229714"
---
# <span data-ttu-id="e1f5d-103">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="e1f5d-103">Get-CimAssociatedInstance</span></span>

## <span data-ttu-id="e1f5d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e1f5d-104">SYNOPSIS</span></span>
<span data-ttu-id="e1f5d-105">Извлекает экземпляры CIM, которые подключены к определенному экземпляру CIM с помощью ассоциации.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-105">Retrieves the CIM instances that are connected to a specific CIM instance by an association.</span></span>

## <span data-ttu-id="e1f5d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e1f5d-106">SYNTAX</span></span>

### <span data-ttu-id="e1f5d-107">Computering (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e1f5d-107">ComputerSet (Default)</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### <span data-ttu-id="e1f5d-108">Session, сеанс</span><span class="sxs-lookup"><span data-stu-id="e1f5d-108">SessionSet</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## <span data-ttu-id="e1f5d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e1f5d-109">DESCRIPTION</span></span>

<span data-ttu-id="e1f5d-110">`Get-CimAssociatedInstance`Командлет извлекает экземпляры CIM, подключенные к определенному экземпляру CIM, который называется экземпляром источника, по ассоциации.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-110">The `Get-CimAssociatedInstance` cmdlet retrieves the CIM instances connected to a specific CIM instance, called the source instance, by an association.</span></span>

<span data-ttu-id="e1f5d-111">В ассоциации каждый экземпляр CIM имеет именованную роль и один и тот же экземпляр CIM может участвовать в ассоциации в разных ролях.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-111">In an association, each CIM instance has a named role and the same CIM instance can participate in an association in different roles.</span></span>

<span data-ttu-id="e1f5d-112">Если параметр InputObject не указан, командлет работает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="e1f5d-112">If the InputObject parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="e1f5d-113">Если не указан ни параметр **ComputerName** , ни параметр **CimSession** , этот командлет работает с локальными инструментарий управления Windows (WMI) (WMI), используя сеанс модели COM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-113">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="e1f5d-114">Если указан параметр **ComputerName** или **CimSession** , то этот КОМАНДЛЕТ работает с сервером CIM, указанным либо в параметре **ComputerName** , либо в параметре **CimSession** .</span><span class="sxs-lookup"><span data-stu-id="e1f5d-114">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="e1f5d-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="e1f5d-115">EXAMPLES</span></span>

### <span data-ttu-id="e1f5d-116">Пример 1. получение всех связанных экземпляров конкретного экземпляра</span><span class="sxs-lookup"><span data-stu-id="e1f5d-116">Example 1: Get all the associated instances of a specific instance</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

<span data-ttu-id="e1f5d-117">Этот набор команд извлекает экземпляры класса с именем Win32_LogicalDisk и сохраняет данные в переменной `$disk` с именем с помощью `Get-CimInstance` командлета.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-117">This set of commands retrieves the instances of the class named Win32_LogicalDisk and stores the information in a variable named `$disk` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="e1f5d-118">Первый экземпляр логического диска в переменной затем используется в качестве входного объекта для `Get-CimAssociatedInstance` командлета, чтобы получить все связанные экземпляры CIM указанного экземпляра CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-118">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated CIM instances of the specified CIM instance.</span></span>

### <span data-ttu-id="e1f5d-119">Пример 2. получение всех связанных экземпляров определенного типа</span><span class="sxs-lookup"><span data-stu-id="e1f5d-119">Example 2: Get all the associated instances of a specific type</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

<span data-ttu-id="e1f5d-120">Этот набор команд извлекает все экземпляры класса **Win32_LogicalDisk** и сохраняет их в переменной с именем `$disk` .</span><span class="sxs-lookup"><span data-stu-id="e1f5d-120">This set of commands retrieves all the instances of the **Win32_LogicalDisk** class and stores them in a variable named `$disk`.</span></span> <span data-ttu-id="e1f5d-121">Первый экземпляр логического диска в переменной затем используется в качестве входного объекта для `Get-CimAssociatedInstance` командлета, чтобы получить все связанные экземпляры, связанные с помощью указанного класса ассоциации **Win32_DiskPartition** .</span><span class="sxs-lookup"><span data-stu-id="e1f5d-121">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated instances that are associated through the specified association class **Win32_DiskPartition** .</span></span>

### <span data-ttu-id="e1f5d-122">Пример 3. получение всех связанных экземпляров с помощью квалификатора определенного класса</span><span class="sxs-lookup"><span data-stu-id="e1f5d-122">Example 3: Get all the associated instances through qualifier of a specific class</span></span>

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

<span data-ttu-id="e1f5d-123">Этот набор команд извлекает службы, которые зависят от службы WMI, и сохраняет их в переменной с именем `$s` .</span><span class="sxs-lookup"><span data-stu-id="e1f5d-123">This set of commands retrieves the services that depend on WMI service and stores them in a variable named `$s`.</span></span> <span data-ttu-id="e1f5d-124">Имя класса ассоциации для **Win32_DependentService** извлекается с помощью `Get-CimClass` командлета путем указания **ассоциации** в качестве квалификатора, а затем передается с помощью $s `Get-CimAssociatedInstance` командлету для получения всех связанных экземпляров полученного класса Association.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-124">The association class name for the **Win32_DependentService** is retrieved using the `Get-CimClass` cmdlet by specifying **Association** as the qualifier and is then passed with $s to the `Get-CimAssociatedInstance` cmdlet to get all the associated instances of the retrieved association class.</span></span>

## <span data-ttu-id="e1f5d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e1f5d-125">PARAMETERS</span></span>

### <span data-ttu-id="e1f5d-126">-Ассоциация</span><span class="sxs-lookup"><span data-stu-id="e1f5d-126">-Association</span></span>

<span data-ttu-id="e1f5d-127">Указывает имя класса ассоциации.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-127">Specifies the name of the association class.</span></span> <span data-ttu-id="e1f5d-128">Если этот параметр не указан, командлет возвращает все существующие объекты связи любого типа.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-128">If you do not specify this parameter, the cmdlet returns all existing association objects of any type.</span></span>

<span data-ttu-id="e1f5d-129">Например, если класс A связан с классом B через две ассоциации, AB1 и AB2, то этот параметр можно использовать для указания типа ассоциации: AB1 или AB2.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-129">For example, if class A is associated with class B through two associations, AB1 and AB2, then this parameter can be used to specify the type of association, either AB1 or AB2.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="e1f5d-130">-CimSession</span></span>

<span data-ttu-id="e1f5d-131">Выполняет команду с помощью указанного сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-131">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="e1f5d-132">Введите переменную, которая содержит сеанс CIM, или команду, которая создает или получает сеанс CIM, например `New-CimSession` или `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="e1f5d-132">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as `New-CimSession` or `Get-CimSession`.</span></span> <span data-ttu-id="e1f5d-133">Дополнительные сведения см. в разделе [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="e1f5d-133">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e1f5d-134">-ComputerName</span></span>

<span data-ttu-id="e1f5d-135">Указывает имя компьютера, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-135">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="e1f5d-136">Можно указать полное доменное имя или NetBIOS-имя.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-136">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="e1f5d-137">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-137">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="e1f5d-138">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-138">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="e1f5d-139">Если на одном компьютере выполняется несколько операций, подключение с помощью сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-139">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e1f5d-140">-InputObject</span></span>

<span data-ttu-id="e1f5d-141">Задает входные данные для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-141">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="e1f5d-142">Можно использовать данный параметр или передавать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-142">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-143">-Кэйонли</span><span class="sxs-lookup"><span data-stu-id="e1f5d-143">-KeyOnly</span></span>

<span data-ttu-id="e1f5d-144">Возвращает объекты только с заполненными ключевыми свойствами.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-144">Returns objects with only key properties populated.</span></span> <span data-ttu-id="e1f5d-145">Это сокращает объем данных, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-145">This reduces the amount of data that is transferred over the network.</span></span>

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

### <span data-ttu-id="e1f5d-146">-Namespace</span><span class="sxs-lookup"><span data-stu-id="e1f5d-146">-Namespace</span></span>

<span data-ttu-id="e1f5d-147">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-147">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="e1f5d-148">Пространством имен по умолчанию является root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-148">The default namespace is root/cimv2.</span></span>

> [!NOTE]
> <span data-ttu-id="e1f5d-149">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-149">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-150">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="e1f5d-150">-OperationTimeoutSec</span></span>

<span data-ttu-id="e1f5d-151">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-151">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="e1f5d-152">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-152">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="e1f5d-153">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-153">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-154">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="e1f5d-154">-ResourceUri</span></span>

<span data-ttu-id="e1f5d-155">Указывает универсальный код ресурса (URI) ресурса для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-155">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="e1f5d-156">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-156">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="e1f5d-157">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-157">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="e1f5d-158">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1f5d-158">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="e1f5d-159">По умолчанию, если этот параметр не указан, используется URI стандартного ресурса DMTF `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` и к нему добавляется имя класса.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-159">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="e1f5d-160">**ResourceUri** можно использовать только с сеансами CIM, созданными с помощью протокола WSMAN, или при указании параметра **ComputerName** , который создает сеанс CIM с помощью WSMan.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-160">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="e1f5d-161">Если указать этот параметр без указания параметра **ComputerName** или указать сеанс CIM, созданный с помощью протокола DCOM, возникает ошибка, так как протокол DCOM не поддерживает параметр **resourceUri** .</span><span class="sxs-lookup"><span data-stu-id="e1f5d-161">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="e1f5d-162">Если указаны оба параметра: **ResourceUri** и **Filter** , параметр **Filter** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-162">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e1f5d-163">-Ресулткласснаме</span><span class="sxs-lookup"><span data-stu-id="e1f5d-163">-ResultClassName</span></span>

<span data-ttu-id="e1f5d-164">Указывает имя класса для связанных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-164">Specifies the class name of the associated instances.</span></span> <span data-ttu-id="e1f5d-165">Экземпляр CIM может быть связан с одним или несколькими экземплярами CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-165">A CIM instance can be associated with one or more CIM instances.</span></span> <span data-ttu-id="e1f5d-166">Если не указать имя результирующего класса, возвращаются все связанные экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-166">All associated CIM instances are returned if you do not specify the result class name.</span></span>

<span data-ttu-id="e1f5d-167">По умолчанию значение этого параметра равно null, и возвращаются все связанные экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-167">By default, the value of this parameter is null, and all associated CIM instances are returned.</span></span>

<span data-ttu-id="e1f5d-168">Результаты ассоциации можно отфильтровать в соответствии с именем определенного класса.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-168">You can filter the association results to match a specific class name.</span></span> <span data-ttu-id="e1f5d-169">Фильтрация происходит на сервере.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-169">Filtering happens on the server.</span></span> <span data-ttu-id="e1f5d-170">Если этот параметр не указан, `Get-CIMAssociatedInstance` возвращает все существующие связи.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-170">If this parameter is not specified, `Get-CIMAssociatedInstance` returns all existing associations.</span></span> <span data-ttu-id="e1f5d-171">Например, если класс A связан с классами B, C и D, то этот параметр можно использовать для ограничения выходных данных определенным типом (B, C или D).</span><span class="sxs-lookup"><span data-stu-id="e1f5d-171">For example, if class A is associated with classes B, C and D, then this parameter can be used to restrict the output to a specific type (B, C or D).</span></span>

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

### <span data-ttu-id="e1f5d-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e1f5d-172">CommonParameters</span></span>

<span data-ttu-id="e1f5d-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e1f5d-174">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e1f5d-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e1f5d-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e1f5d-175">INPUTS</span></span>

### <span data-ttu-id="e1f5d-176">Нет</span><span class="sxs-lookup"><span data-stu-id="e1f5d-176">None</span></span>

<span data-ttu-id="e1f5d-177">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-177">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="e1f5d-178">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e1f5d-178">OUTPUTS</span></span>

### <span data-ttu-id="e1f5d-179">System.Object</span><span class="sxs-lookup"><span data-stu-id="e1f5d-179">System.Object</span></span>

<span data-ttu-id="e1f5d-180">Этот командлет возвращает объект.</span><span class="sxs-lookup"><span data-stu-id="e1f5d-180">This cmdlet returns an object.</span></span>

## <span data-ttu-id="e1f5d-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e1f5d-181">NOTES</span></span>

## <span data-ttu-id="e1f5d-182">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e1f5d-182">RELATED LINKS</span></span>

[<span data-ttu-id="e1f5d-183">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="e1f5d-183">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="e1f5d-184">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e1f5d-184">Get-CimInstance</span></span>](get-ciminstance.md)
