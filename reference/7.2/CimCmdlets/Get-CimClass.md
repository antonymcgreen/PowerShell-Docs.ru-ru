---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: 483b4b5b940a9effca99e942b86a967de5d26d68
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602282"
---
# <span data-ttu-id="0d5a2-102">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="0d5a2-102">Get-CimClass</span></span>

## <span data-ttu-id="0d5a2-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0d5a2-103">SYNOPSIS</span></span>
<span data-ttu-id="0d5a2-104">Возвращает список классов CIM в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-104">Gets a list of CIM classes in a specific namespace.</span></span>

## <span data-ttu-id="0d5a2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d5a2-105">SYNTAX</span></span>

### <span data-ttu-id="0d5a2-106">Computering (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0d5a2-106">ComputerSet (Default)</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### <span data-ttu-id="0d5a2-107">Session, сеанс</span><span class="sxs-lookup"><span data-stu-id="0d5a2-107">SessionSet</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## <span data-ttu-id="0d5a2-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d5a2-108">DESCRIPTION</span></span>

<span data-ttu-id="0d5a2-109">`Get-CimClass`Командлет извлекает список классов CIM в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-109">The `Get-CimClass` cmdlet retrieves a list of CIM classes in a specific namespace.</span></span> <span data-ttu-id="0d5a2-110">Если имя класса не указано, командлет возвращает все классы в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-110">If there is no class name supplied, then the cmdlet returns all the classes in the namespace.</span></span> <span data-ttu-id="0d5a2-111">В отличие от экземпляра CIM, классы CIM не содержат сеанса CIM или имени компьютера, откуда они извлекаются.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-111">Unlike a CIM instance, CIM classes do not contain the CIM session or computer name from which they are retrieved.</span></span>

## <span data-ttu-id="0d5a2-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="0d5a2-112">EXAMPLES</span></span>

### <span data-ttu-id="0d5a2-113">Пример 1. получение всех определений классов</span><span class="sxs-lookup"><span data-stu-id="0d5a2-113">Example 1: Get all the class definitions</span></span>

<span data-ttu-id="0d5a2-114">В этом примере возвращаются все определения классов в пространстве имен **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-114">This example gets all the class definitions under the namespace **root/cimv2**.</span></span>

```powershell
Get-CimClass
```

### <span data-ttu-id="0d5a2-115">Пример 2. получение классов с указанным именем</span><span class="sxs-lookup"><span data-stu-id="0d5a2-115">Example 2: Get the classes with a specific name</span></span>

<span data-ttu-id="0d5a2-116">Этот пример возвращает классы, содержащие слово **Disk** в своих именах.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-116">This example gets the classes that contain the word **disk** in their names.</span></span>

```powershell
Get-CimClass -ClassName *disk*
```

### <span data-ttu-id="0d5a2-117">Пример 3. получение классов с использованием определенного имени метода</span><span class="sxs-lookup"><span data-stu-id="0d5a2-117">Example 3: Get the classes with a specific method name</span></span>

<span data-ttu-id="0d5a2-118">Этот пример получает классы, которые начинаются с имени **Win32** и имеют имя метода, которое начинается с **Term**.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-118">This example gets the classes that start with the name **Win32** and have a method name that starts with **Term**.</span></span>

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### <span data-ttu-id="0d5a2-119">Пример 4. получение классов с заданным именем свойства</span><span class="sxs-lookup"><span data-stu-id="0d5a2-119">Example 4: Get the classes with a specific property name</span></span>

<span data-ttu-id="0d5a2-120">Этот пример получает классы, которые начинаются с имени **Win32** и имеют свойство с именем **Handle**.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-120">This example gets the classes that start with the name **Win32** and have a property named **Handle**.</span></span>

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### <span data-ttu-id="0d5a2-121">Пример 5. получение классов с заданным именем квалификатора</span><span class="sxs-lookup"><span data-stu-id="0d5a2-121">Example 5: Get the classes with a specific qualifier name</span></span>

<span data-ttu-id="0d5a2-122">Этот пример получает классы, которые начинаются с имени **Win32**, содержат слово **Disk** в своих именах и имеют указанную **связь** квалификатора.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-122">This example gets the classes that start with the name **Win32**, contain the word **Disk** in their names and have the specified qualifier **Association**.</span></span>

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### <span data-ttu-id="0d5a2-123">Пример 6. получение определений классов из определенного пространства имен</span><span class="sxs-lookup"><span data-stu-id="0d5a2-123">Example 6: Get the class definitions from a specific namespace</span></span>

<span data-ttu-id="0d5a2-124">В этом примере возвращаются определения классов, содержащие слово **net** в своих именах из указанного **корня или standardCimv2** пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-124">This example gets the class definitions that contain the word **Net** in their names from the specified namespace **root/standardCimv2**.</span></span>

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### <span data-ttu-id="0d5a2-125">Пример 7. получение определений классов с удаленного сервера</span><span class="sxs-lookup"><span data-stu-id="0d5a2-125">Example 7: Get the class definitions from a remote server</span></span>

<span data-ttu-id="0d5a2-126">В этом примере возвращаются определения классов, содержащие слово **Disk** в своих именах из указанных удаленных серверов **Server01** и **Server02**.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-126">This example gets the class definitions that contain the word **disk** in their names from the specified remote servers **Server01** and **Server02**.</span></span>

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### <span data-ttu-id="0d5a2-127">Пример 8. получение классов с помощью сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="0d5a2-127">Example 8: Get the classes by using a CIM session</span></span>

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

<span data-ttu-id="0d5a2-128">Этот набор команд создает сеанс с несколькими компьютерами и сохраняет его в переменную `$s` с помощью `New-CimSession` командлета, а затем получает классы с помощью `Get-CimClass` командлета.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-128">This set of commands creates a session with multiple computers and stores it into a variable `$s` using the `New-CimSession` cmdlet, and then gets the classes using the `Get-CimClass` cmdlet.</span></span>

## <span data-ttu-id="0d5a2-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d5a2-129">PARAMETERS</span></span>

### <span data-ttu-id="0d5a2-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d5a2-130">-CimSession</span></span>

<span data-ttu-id="0d5a2-131">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="0d5a2-132">Введите имя компьютера или объект сеанса, например выходные данные `New-CimSession` `Get-CimSession` командлета или.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-132">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span> <span data-ttu-id="0d5a2-133">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-133">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="0d5a2-134">-ClassName</span><span class="sxs-lookup"><span data-stu-id="0d5a2-134">-ClassName</span></span>

<span data-ttu-id="0d5a2-135">Указывает имя класса CIM, для которого выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-135">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="0d5a2-136">Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-136">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0d5a2-137">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0d5a2-137">-ComputerName</span></span>

<span data-ttu-id="0d5a2-138">Указывает компьютер, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-138">Specifies the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="0d5a2-139">Можно указать полное доменное имя (FQDN) или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-139">You can specify a fully qualified domain name (FQDN) a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="0d5a2-140">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-140">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="0d5a2-141">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-141">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="0d5a2-142">Если на одном компьютере выполняется несколько операций, использование сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-142">If multiple operations are being performed on the same computer, using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0d5a2-143">-Имя_метода</span><span class="sxs-lookup"><span data-stu-id="0d5a2-143">-MethodName</span></span>

<span data-ttu-id="0d5a2-144">Находит классы, имеющие метод, совпадающий с этим именем.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-144">Finds the classes that have a method matching this name.</span></span> <span data-ttu-id="0d5a2-145">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-145">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0d5a2-146">-Namespace</span><span class="sxs-lookup"><span data-stu-id="0d5a2-146">-Namespace</span></span>

<span data-ttu-id="0d5a2-147">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-147">Specifies the namespace for CIM operation.</span></span> <span data-ttu-id="0d5a2-148">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-148">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="0d5a2-149">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-149">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0d5a2-150">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="0d5a2-150">-OperationTimeoutSec</span></span>

<span data-ttu-id="0d5a2-151">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-151">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="0d5a2-152">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-152">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="0d5a2-153">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-153">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="0d5a2-154">-PropertyName</span><span class="sxs-lookup"><span data-stu-id="0d5a2-154">-PropertyName</span></span>

<span data-ttu-id="0d5a2-155">Находит классы, имеющие свойство, соответствующее этому имени.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-155">Finds the classes which have a property matching this name.</span></span> <span data-ttu-id="0d5a2-156">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-156">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="0d5a2-157">-Куалифиернаме</span><span class="sxs-lookup"><span data-stu-id="0d5a2-157">-QualifierName</span></span>

<span data-ttu-id="0d5a2-158">Фильтрует классы по имени квалификатора уровня класса.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-158">Filters the classes by class level qualifier name.</span></span> <span data-ttu-id="0d5a2-159">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-159">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0d5a2-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0d5a2-160">CommonParameters</span></span>

<span data-ttu-id="0d5a2-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d5a2-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0d5a2-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d5a2-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0d5a2-163">INPUTS</span></span>

### <span data-ttu-id="0d5a2-164">None</span><span class="sxs-lookup"><span data-stu-id="0d5a2-164">None</span></span>

<span data-ttu-id="0d5a2-165">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-165">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="0d5a2-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0d5a2-166">OUTPUTS</span></span>

### <span data-ttu-id="0d5a2-167">Microsoft. Management. Infrastructure. Цимкласс</span><span class="sxs-lookup"><span data-stu-id="0d5a2-167">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="0d5a2-168">Этот командлет возвращает объект класса CIM.</span><span class="sxs-lookup"><span data-stu-id="0d5a2-168">This cmdlet returns a CIM class object.</span></span>

## <span data-ttu-id="0d5a2-169">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0d5a2-169">NOTES</span></span>

## <span data-ttu-id="0d5a2-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0d5a2-170">RELATED LINKS</span></span>

[<span data-ttu-id="0d5a2-171">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d5a2-171">New-CimSession</span></span>](New-CimSession.md)

