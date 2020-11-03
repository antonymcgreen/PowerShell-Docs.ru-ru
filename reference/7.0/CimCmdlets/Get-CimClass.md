---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: 2fd87935e2594a643327d2ae07fad112b1b9386f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225681"
---
# <span data-ttu-id="72d8c-103">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="72d8c-103">Get-CimClass</span></span>

## <span data-ttu-id="72d8c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="72d8c-104">SYNOPSIS</span></span>
<span data-ttu-id="72d8c-105">Возвращает список классов CIM в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="72d8c-105">Gets a list of CIM classes in a specific namespace.</span></span>

## <span data-ttu-id="72d8c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="72d8c-106">SYNTAX</span></span>

### <span data-ttu-id="72d8c-107">Computering (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="72d8c-107">ComputerSet (Default)</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### <span data-ttu-id="72d8c-108">Session, сеанс</span><span class="sxs-lookup"><span data-stu-id="72d8c-108">SessionSet</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## <span data-ttu-id="72d8c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="72d8c-109">DESCRIPTION</span></span>

<span data-ttu-id="72d8c-110">`Get-CimClass`Командлет извлекает список классов CIM в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="72d8c-110">The `Get-CimClass` cmdlet retrieves a list of CIM classes in a specific namespace.</span></span> <span data-ttu-id="72d8c-111">Если имя класса не указано, командлет возвращает все классы в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="72d8c-111">If there is no class name supplied, then the cmdlet returns all the classes in the namespace.</span></span> <span data-ttu-id="72d8c-112">В отличие от экземпляра CIM, классы CIM не содержат сеанса CIM или имени компьютера, откуда они извлекаются.</span><span class="sxs-lookup"><span data-stu-id="72d8c-112">Unlike a CIM instance, CIM classes do not contain the CIM session or computer name from which they are retrieved.</span></span>

## <span data-ttu-id="72d8c-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="72d8c-113">EXAMPLES</span></span>

### <span data-ttu-id="72d8c-114">Пример 1. получение всех определений классов</span><span class="sxs-lookup"><span data-stu-id="72d8c-114">Example 1: Get all the class definitions</span></span>

<span data-ttu-id="72d8c-115">В этом примере возвращаются все определения классов в пространстве имен **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="72d8c-115">This example gets all the class definitions under the namespace **root/cimv2**.</span></span>

```powershell
Get-CimClass
```

### <span data-ttu-id="72d8c-116">Пример 2. получение классов с указанным именем</span><span class="sxs-lookup"><span data-stu-id="72d8c-116">Example 2: Get the classes with a specific name</span></span>

<span data-ttu-id="72d8c-117">Этот пример возвращает классы, содержащие слово **Disk** в своих именах.</span><span class="sxs-lookup"><span data-stu-id="72d8c-117">This example gets the classes that contain the word **disk** in their names.</span></span>

```powershell
Get-CimClass -ClassName *disk*
```

### <span data-ttu-id="72d8c-118">Пример 3. получение классов с использованием определенного имени метода</span><span class="sxs-lookup"><span data-stu-id="72d8c-118">Example 3: Get the classes with a specific method name</span></span>

<span data-ttu-id="72d8c-119">Этот пример получает классы, которые начинаются с имени **Win32** и имеют имя метода, которое начинается с **Term**.</span><span class="sxs-lookup"><span data-stu-id="72d8c-119">This example gets the classes that start with the name **Win32** and have a method name that starts with **Term**.</span></span>

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### <span data-ttu-id="72d8c-120">Пример 4. получение классов с заданным именем свойства</span><span class="sxs-lookup"><span data-stu-id="72d8c-120">Example 4: Get the classes with a specific property name</span></span>

<span data-ttu-id="72d8c-121">Этот пример получает классы, которые начинаются с имени **Win32** и имеют свойство с именем **Handle**.</span><span class="sxs-lookup"><span data-stu-id="72d8c-121">This example gets the classes that start with the name **Win32** and have a property named **Handle**.</span></span>

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### <span data-ttu-id="72d8c-122">Пример 5. получение классов с заданным именем квалификатора</span><span class="sxs-lookup"><span data-stu-id="72d8c-122">Example 5: Get the classes with a specific qualifier name</span></span>

<span data-ttu-id="72d8c-123">Этот пример получает классы, которые начинаются с имени **Win32** , содержат слово **Disk** в своих именах и имеют указанную **связь** квалификатора.</span><span class="sxs-lookup"><span data-stu-id="72d8c-123">This example gets the classes that start with the name **Win32** , contain the word **Disk** in their names and have the specified qualifier **Association**.</span></span>

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### <span data-ttu-id="72d8c-124">Пример 6. получение определений классов из определенного пространства имен</span><span class="sxs-lookup"><span data-stu-id="72d8c-124">Example 6: Get the class definitions from a specific namespace</span></span>

<span data-ttu-id="72d8c-125">В этом примере возвращаются определения классов, содержащие слово **net** в своих именах из указанного **корня или standardCimv2** пространства имен.</span><span class="sxs-lookup"><span data-stu-id="72d8c-125">This example gets the class definitions that contain the word **Net** in their names from the specified namespace **root/standardCimv2**.</span></span>

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### <span data-ttu-id="72d8c-126">Пример 7. получение определений классов с удаленного сервера</span><span class="sxs-lookup"><span data-stu-id="72d8c-126">Example 7: Get the class definitions from a remote server</span></span>

<span data-ttu-id="72d8c-127">В этом примере возвращаются определения классов, содержащие слово **Disk** в своих именах из указанных удаленных серверов **Server01** и **Server02**.</span><span class="sxs-lookup"><span data-stu-id="72d8c-127">This example gets the class definitions that contain the word **disk** in their names from the specified remote servers **Server01** and **Server02**.</span></span>

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### <span data-ttu-id="72d8c-128">Пример 8. получение классов с помощью сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="72d8c-128">Example 8: Get the classes by using a CIM session</span></span>

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

<span data-ttu-id="72d8c-129">Этот набор команд создает сеанс с несколькими компьютерами и сохраняет его в переменную `$s` с помощью `New-CimSession` командлета, а затем получает классы с помощью `Get-CimClass` командлета.</span><span class="sxs-lookup"><span data-stu-id="72d8c-129">This set of commands creates a session with multiple computers and stores it into a variable `$s` using the `New-CimSession` cmdlet, and then gets the classes using the `Get-CimClass` cmdlet.</span></span>

## <span data-ttu-id="72d8c-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="72d8c-130">PARAMETERS</span></span>

### <span data-ttu-id="72d8c-131">-CimSession</span><span class="sxs-lookup"><span data-stu-id="72d8c-131">-CimSession</span></span>

<span data-ttu-id="72d8c-132">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="72d8c-132">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="72d8c-133">Введите имя компьютера или объект сеанса, например выходные данные `New-CimSession` `Get-CimSession` командлета или.</span><span class="sxs-lookup"><span data-stu-id="72d8c-133">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span> <span data-ttu-id="72d8c-134">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="72d8c-134">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="72d8c-135">-ClassName</span><span class="sxs-lookup"><span data-stu-id="72d8c-135">-ClassName</span></span>

<span data-ttu-id="72d8c-136">Указывает имя класса CIM, для которого выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="72d8c-136">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="72d8c-137">Для просмотра списка классов можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список классов с локального сервера WMI, чтобы предоставить список имен классов.</span><span class="sxs-lookup"><span data-stu-id="72d8c-137">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="72d8c-138">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="72d8c-138">-ComputerName</span></span>

<span data-ttu-id="72d8c-139">Указывает компьютер, на котором требуется выполнить операцию CIM.</span><span class="sxs-lookup"><span data-stu-id="72d8c-139">Specifies the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="72d8c-140">Можно указать полное доменное имя (FQDN) или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="72d8c-140">You can specify a fully qualified domain name (FQDN) a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="72d8c-141">При указании этого параметра командлет создает временный сеанс на указанном компьютере с помощью протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="72d8c-141">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="72d8c-142">Если этот параметр не указан, командлет выполняет операцию на локальном компьютере с помощью модели COM.</span><span class="sxs-lookup"><span data-stu-id="72d8c-142">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="72d8c-143">Если на одном компьютере выполняется несколько операций, использование сеанса CIM обеспечивает лучшую производительность.</span><span class="sxs-lookup"><span data-stu-id="72d8c-143">If multiple operations are being performed on the same computer, using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="72d8c-144">-Имя_метода</span><span class="sxs-lookup"><span data-stu-id="72d8c-144">-MethodName</span></span>

<span data-ttu-id="72d8c-145">Находит классы, имеющие метод, совпадающий с этим именем.</span><span class="sxs-lookup"><span data-stu-id="72d8c-145">Finds the classes that have a method matching this name.</span></span> <span data-ttu-id="72d8c-146">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="72d8c-146">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="72d8c-147">-Namespace</span><span class="sxs-lookup"><span data-stu-id="72d8c-147">-Namespace</span></span>

<span data-ttu-id="72d8c-148">Указывает пространство имен для операции CIM.</span><span class="sxs-lookup"><span data-stu-id="72d8c-148">Specifies the namespace for CIM operation.</span></span> <span data-ttu-id="72d8c-149">Пространством имен по умолчанию является **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="72d8c-149">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="72d8c-150">Для просмотра списка пространств имен можно использовать функцию заполнения нажатием клавиши TAB, так как PowerShell получает список пространств имен с локального сервера WMI для предоставления списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="72d8c-150">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="72d8c-151">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="72d8c-151">-OperationTimeoutSec</span></span>

<span data-ttu-id="72d8c-152">Указывает период времени, в течение которого командлет ожидает ответа от компьютера.</span><span class="sxs-lookup"><span data-stu-id="72d8c-152">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="72d8c-153">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="72d8c-153">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="72d8c-154">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="72d8c-154">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="72d8c-155">-PropertyName</span><span class="sxs-lookup"><span data-stu-id="72d8c-155">-PropertyName</span></span>

<span data-ttu-id="72d8c-156">Находит классы, имеющие свойство, соответствующее этому имени.</span><span class="sxs-lookup"><span data-stu-id="72d8c-156">Finds the classes which have a property matching this name.</span></span> <span data-ttu-id="72d8c-157">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="72d8c-157">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="72d8c-158">-Куалифиернаме</span><span class="sxs-lookup"><span data-stu-id="72d8c-158">-QualifierName</span></span>

<span data-ttu-id="72d8c-159">Фильтрует классы по имени квалификатора уровня класса.</span><span class="sxs-lookup"><span data-stu-id="72d8c-159">Filters the classes by class level qualifier name.</span></span> <span data-ttu-id="72d8c-160">С этим параметром можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="72d8c-160">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="72d8c-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="72d8c-161">CommonParameters</span></span>

<span data-ttu-id="72d8c-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="72d8c-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="72d8c-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="72d8c-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="72d8c-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="72d8c-164">INPUTS</span></span>

### <span data-ttu-id="72d8c-165">Нет</span><span class="sxs-lookup"><span data-stu-id="72d8c-165">None</span></span>

<span data-ttu-id="72d8c-166">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="72d8c-166">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="72d8c-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="72d8c-167">OUTPUTS</span></span>

### <span data-ttu-id="72d8c-168">Microsoft. Management. Infrastructure. Цимкласс</span><span class="sxs-lookup"><span data-stu-id="72d8c-168">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="72d8c-169">Этот командлет возвращает объект класса CIM.</span><span class="sxs-lookup"><span data-stu-id="72d8c-169">This cmdlet returns a CIM class object.</span></span>

## <span data-ttu-id="72d8c-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="72d8c-170">NOTES</span></span>

## <span data-ttu-id="72d8c-171">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="72d8c-171">RELATED LINKS</span></span>

[<span data-ttu-id="72d8c-172">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="72d8c-172">New-CimSession</span></span>](New-CimSession.md)
