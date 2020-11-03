---
description: Содержит описание языка WQL, используемого для получения объектов WMI в Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232258"
---
# <a name="about-wql"></a><span data-ttu-id="d9ca1-104">Сведения о WQL</span><span class="sxs-lookup"><span data-stu-id="d9ca1-104">About WQL</span></span>

## <a name="short-description"></a><span data-ttu-id="d9ca1-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="d9ca1-106">Содержит описание языка WQL, используемого для получения объектов WMI в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-106">Describes WMI Query Language (WQL), which can be used to get WMI objects in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d9ca1-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d9ca1-108">WQL — это язык запросов инструментарий управления Windows (WMI) (WMI), который используется для получения информации от WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-108">WQL is the Windows Management Instrumentation (WMI) query language, which is the language used to get information from WMI.</span></span>

<span data-ttu-id="d9ca1-109">Для выполнения запросов WMI в Windows PowerShell не требуется использовать WQL.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-109">You are not required to use WQL to perform a WMI query in Windows PowerShell.</span></span>
<span data-ttu-id="d9ca1-110">Вместо этого можно использовать параметры командлетов Get-WmiObject или Get-CimInstance.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-110">Instead, you can use the parameters of the Get-WmiObject or Get-CimInstance cmdlets.</span></span> <span data-ttu-id="d9ca1-111">Запросы WQL выполняются несколько быстрее, чем стандартные команды Get-WmiObject и улучшенная производительность очевидна, когда команды выполняются на сотнях систем.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-111">WQL queries are somewhat faster than standard Get-WmiObject commands and the improved performance is evident when the commands run on hundreds of systems.</span></span> <span data-ttu-id="d9ca1-112">Однако следует убедиться, что время, затрачиваемое на написание успешного запроса WQL, не перевешивает повышение производительности.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-112">However, be sure that the time you spend to write a successful WQL query doesn't outweigh the performance improvement.</span></span>

<span data-ttu-id="d9ca1-113">Основные инструкции WQL, для которых необходимо использовать WQL, — SELECT, WHERE и from.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-113">The basic WQL statements you need to use WQL are Select, Where, and From.</span></span>

## <a name="when-to-use-wql"></a><span data-ttu-id="d9ca1-114">КОГДА СЛЕДУЕТ ИСПОЛЬЗОВАТЬ WQL</span><span class="sxs-lookup"><span data-stu-id="d9ca1-114">WHEN TO USE WQL</span></span>

<span data-ttu-id="d9ca1-115">При работе с WMI, особенно с WQL, не забывайте, что вы также используете Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-115">When working with WMI, and especially with WQL, do not forget that you are also using Windows PowerShell.</span></span> <span data-ttu-id="d9ca1-116">Часто, если запрос WQL не работает должным образом, проще использовать стандартную команду Windows PowerShell, чем отладка WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-116">Often, if a WQL query does not work as expected, it's easier to use a standard Windows PowerShell command than to debug the WQL query.</span></span>

<span data-ttu-id="d9ca1-117">Если вы не возвращаете большие объемы данных из нескольких удаленных систем с ограниченной пропускной способностью, редко бывает, что тратить время на совершение сложных запросов WQL и сложные, если существует вполне приемлемый командлет Windows, который делает то же самое, если немного медленнее.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-117">Unless you are returning massive amounts of data from across bandwidth-constrained remote systems, it is rarely productive to spend hours trying to perfect a complicated and convoluted WQL query when there is a perfectly acceptable Windows cmdlet that does the same thing, if a bit more slowly.</span></span>

## <a name="using-the-select-statement"></a><span data-ttu-id="d9ca1-118">ИСПОЛЬЗОВАНИЕ ИНСТРУКЦИИ SELECT</span><span class="sxs-lookup"><span data-stu-id="d9ca1-118">USING THE SELECT STATEMENT</span></span>

<span data-ttu-id="d9ca1-119">Типичный запрос WMI начинается с инструкции SELECT, которая получает все свойства или определенные свойства класса WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-119">A typical WMI query begins with a Select statement that gets all properties or particular properties of a WMI class.</span></span> <span data-ttu-id="d9ca1-120">Чтобы выбрать все свойства класса WMI, используйте звездочку ( \* ).</span><span class="sxs-lookup"><span data-stu-id="d9ca1-120">To select all properties of a WMI class, use an asterisk (\*).</span></span> <span data-ttu-id="d9ca1-121">Ключевое слово FROM указывает класс WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-121">The From keyword specifies the WMI class.</span></span>

<span data-ttu-id="d9ca1-122">Инструкция SELECT имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d9ca1-122">A Select statement has the following format:</span></span>

```
Select <property> from <WMI-class>
```

<span data-ttu-id="d9ca1-123">Например, следующая инструкция SELECT выбирает все свойства (\*) из экземпляров класса Win32_Bios WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-123">For example, the following Select statement selects all properties (\*) from the instances of the Win32_Bios WMI class.</span></span>

```
Select * from Win32_Bios
```

<span data-ttu-id="d9ca1-124">Чтобы выбрать определенное свойство класса WMI, поместите имя свойства между ключевыми словами SELECT и from.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-124">To select a particular property of a WMI class, place the property name between the Select and From keywords.</span></span>

<span data-ttu-id="d9ca1-125">Следующий запрос выбирает только имя BIOS из класса Win32_Bios WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-125">The following query selects only the name of the BIOS from the Win32_Bios WMI class.</span></span> <span data-ttu-id="d9ca1-126">Команда сохраняет запрос в переменной $queryName.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-126">The command saves the query in the $queryName variable.</span></span>

```
Select Name from Win32_Bios
```

<span data-ttu-id="d9ca1-127">Чтобы выбрать несколько свойств, используйте запятые для разделения имен свойств.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-127">To select more than one property, use commas to separate the property names.</span></span>
<span data-ttu-id="d9ca1-128">Следующий запрос WMI выбирает имя и версию класса Win32_Bios WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-128">The following WMI query selects the name and the version of the Win32_Bios WMI class.</span></span> <span data-ttu-id="d9ca1-129">Команда сохраняет запрос в переменной $queryNameVersion.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-129">The command saves the query in the $queryNameVersion variable.</span></span>

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a><span data-ttu-id="d9ca1-130">ИСПОЛЬЗОВАНИЕ WQL-ЗАПРОСА</span><span class="sxs-lookup"><span data-stu-id="d9ca1-130">USING THE WQL QUERY</span></span>

<span data-ttu-id="d9ca1-131">Существует три способа использования WQL-запроса в команде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-131">There are three ways to use WQL query in Windows PowerShell command.</span></span>

- <span data-ttu-id="d9ca1-132">Использование командлета Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="d9ca1-132">Use the Get-WmiObject cmdlet</span></span>
- <span data-ttu-id="d9ca1-133">Использование командлета Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="d9ca1-133">Use the Get-CimInstance cmdlet</span></span>
- <span data-ttu-id="d9ca1-134">Используйте ускоритель типа [вмисеарчер].</span><span class="sxs-lookup"><span data-stu-id="d9ca1-134">Use the [wmisearcher] type accelerator.</span></span>

## <a name="using-the-get-wmiobject-cmdlet"></a><span data-ttu-id="d9ca1-135">ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТА GET-WMIOBJECT</span><span class="sxs-lookup"><span data-stu-id="d9ca1-135">USING THE GET-WMIOBJECT CMDLET</span></span>

<span data-ttu-id="d9ca1-136">Самый простой способ использовать WQL-запрос заключается в заключении его в кавычки (в виде строки), а затем используйте строку запроса в качестве значения параметра запроса командлета Get-WmiObject, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-136">The most basic way to use the WQL query is to enclose it in quotation marks (as a string) and then use the query string as the value of the Query parameter of the Get-WmiObject cmdlet, as shown in the following example.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="d9ca1-137">Можно также сохранить инструкцию WQL в переменной, а затем использовать переменную в качестве значения параметра запроса, как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-137">You can also save the WQL statement in a variable and then use the variable as the value of the Query parameter, as shown in the following command.</span></span>

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

<span data-ttu-id="d9ca1-138">Можно использовать любой из форматов с любой инструкцией WQL.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-138">You can use either format with any WQL statement.</span></span> <span data-ttu-id="d9ca1-139">Следующая команда использует запрос в переменной $queryName, чтобы получить только свойства Name и Version BIOS системы.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-139">The following command uses the query in the $queryName variable to get only the name and version properties of the system BIOS.</span></span>

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

<span data-ttu-id="d9ca1-140">Помните, что для получения того же результата можно использовать параметры командлета Get-WmiObject.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-140">Remember that you can use the parameters of the Get-WmiObject cmdlet to get the same result.</span></span> <span data-ttu-id="d9ca1-141">Например, следующая команда также возвращает значения свойств Name и Version экземпляров класса Win32_Bios WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-141">For example, the following command also gets the values of the Name and Version properties of instances of the Win32_Bios WMI class.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a><span data-ttu-id="d9ca1-142">ИСПОЛЬЗОВАНИЕ КОМАНДЛЕТА GET-CIMINSTANCE</span><span class="sxs-lookup"><span data-stu-id="d9ca1-142">USING THE GET-CIMINSTANCE CMDLET</span></span>

<span data-ttu-id="d9ca1-143">Начиная с Windows PowerShell 3,0, можно использовать командлет Get-CimInstance для выполнения WQL-запросов.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-143">Beginning in Windows PowerShell 3.0, you can use the Get-CimInstance cmdlet to run WQL queries.</span></span>

<span data-ttu-id="d9ca1-144">Get-CimInstance получает экземпляры классов, совместимых с CIM, включая классы WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-144">Get-CimInstance gets instances of CIM-compliant classes, including WMI classes.</span></span> <span data-ttu-id="d9ca1-145">Командлеты CIM, появившиеся в Windows PowerShell 3,0, выполняют те же задачи, что и командлеты WMI.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-145">The CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="d9ca1-146">Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту модель CIM (CIM), который позволяет командлетам использовать те же методы для управления компьютерами и компьютерами Windows, на которых работают другие операционные системы.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-146">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage Windows computers and computers that are running other operating systems.</span></span>

<span data-ttu-id="d9ca1-147">Следующая команда использует командлет Get-CimInstance для выполнения WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-147">The following command uses the Get-CimInstance cmdlet to run a WQL query.</span></span>

<span data-ttu-id="d9ca1-148">Любой запрос WQL, который можно использовать с Get-WmiObject, также можно использовать с Get-CimInstance.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-148">Any WQL query that can be used with Get-WmiObject can also be used with Get-CimInstance.</span></span>

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="d9ca1-149">Get-CimInstance возвращает объект CimInstance, а не ManagementObject, который Get-WmiObject возвращает, но объекты весьма похожи.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-149">Get-CimInstance returns a CimInstance object, instead of the ManagementObject that Get-WmiObject returns, but the objects are quite similar.</span></span>

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a><span data-ttu-id="d9ca1-150">Использование УСКОРИТЕЛя типов [вмисеарчер]</span><span class="sxs-lookup"><span data-stu-id="d9ca1-150">USING THE [wmisearcher] TYPE ACCELERATOR</span></span>

<span data-ttu-id="d9ca1-151">Ускоритель типа [вмисеарчер] создает объект Манажементобжектсеарчер из строки инструкции WQL.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-151">The [wmisearcher] type accelerator creates a ManagementObjectSearcher object from a WQL statement string.</span></span> <span data-ttu-id="d9ca1-152">Объект Манажементобжектсеарчер имеет множество свойств и методов, но самый простой метод — это метод Get, который вызывает заданный WMI-запрос и возвращает результирующие объекты.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-152">The ManagementObjectSearcher object has many properties and methods, but the most basic method is the Get method, which invokes the specified WMI query and returns the resulting objects.</span></span>

<span data-ttu-id="d9ca1-153">Используя [вмисеарчер], вы получаете простой доступ к классу .NET Framework Манажементобжектсеарчер.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-153">By using the [wmisearcher], you gain easy access to the ManagementObjectSearcher .NET Framework class.</span></span> <span data-ttu-id="d9ca1-154">Это позволяет запрашивать Инструментарий WMI и настраивать способ выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-154">This lets you query WMI and to configure the way the query is conducted.</span></span>

<span data-ttu-id="d9ca1-155">Чтобы использовать ускоритель типа [вмисеарчер], выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-155">To use the [wmisearcher] type accelerator:</span></span>

1. <span data-ttu-id="d9ca1-156">Приведите строку WQL в объект Манажементобжектсеарчер.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-156">Cast the  WQL string into a ManagementObjectSearcher object.</span></span>
2. <span data-ttu-id="d9ca1-157">Вызовите метод Get объекта Манажементобжектсеарчер.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-157">Call the Get method of the ManagementObjectSearcher object.</span></span>

<span data-ttu-id="d9ca1-158">Например, следующая команда приводит к появлению запроса SELECT ALL, сохраняет результат в переменной $bios, а затем вызывает метод Get объекта Манажементобжектсеарчер в переменной $bios.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-158">For example, the following command casts the "select all" query, saves the result in the $bios variable, and then calls the Get method of the ManagementObjectSearcher object in the $bios variable.</span></span>

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="d9ca1-159">Примечание. по умолчанию отображаются только выбранные свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-159">NOTE: Only selected object properties are displayed by default.</span></span> <span data-ttu-id="d9ca1-160">Эти свойства определяются в Types.ps1XML-файле.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-160">These properties are defined in the Types.ps1xml file.</span></span>

<span data-ttu-id="d9ca1-161">Для приведения запроса или переменной можно использовать ускоритель типа [вмисеарчер].</span><span class="sxs-lookup"><span data-stu-id="d9ca1-161">You can use the [wmisearcher] type accelerator to cast the query or the variable.</span></span> <span data-ttu-id="d9ca1-162">В следующем примере для приведения переменной используется ускоритель типа [вмисеарчер].</span><span class="sxs-lookup"><span data-stu-id="d9ca1-162">In the following example, the [wmisearcher] type accelerator is used to cast the variable.</span></span> <span data-ttu-id="d9ca1-163">Результат такой же.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-163">The result is the same.</span></span>

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="d9ca1-164">При использовании ускорителя типа [вмисеарчер] строка запроса преобразуется в объект Манажементобжектсеарчер, как показано в следующих командах.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-164">When you use the [wmisearcher] type accelerator, it changes the query string into a ManagementObjectSearcher object, as shown in the following commands.</span></span>

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

<span data-ttu-id="d9ca1-165">Этот формат команды работает с любым запросом.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-165">This command format works on any query.</span></span> <span data-ttu-id="d9ca1-166">Следующая команда возвращает значение свойства Name класса WMI Win32_Bios.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-166">The following command gets the value of the Name property of the Win32_Bios WMI class.</span></span>

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

<span data-ttu-id="d9ca1-167">Эту операцию можно выполнить в одной команде, хотя команда немного сложнее интерпретировать.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-167">You can perform this operation in a single command, although the command is a bit more difficult to interpret.</span></span>

<span data-ttu-id="d9ca1-168">В этом формате вы используете ускоритель типа [вмисеарчер] для приведения строки запроса WQL к Манажементобжектсеарчер, а затем вызываете метод Get для объекта--ALL в одной команде.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-168">In this format, you use the [wmisearcher] type accelerator to cast the WQL query string to a ManagementObjectSearcher, and then call the Get method on the object -- all in a single command.</span></span> <span data-ttu-id="d9ca1-169">Круглые скобки (), которые заключают приведенную строку в оболочку Windows PowerShell для приведения строки перед вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-169">The parentheses () that enclose the casted string direct Windows PowerShell to cast the string before calling the method.</span></span>

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a><span data-ttu-id="d9ca1-170">ИСПОЛЬЗОВАНИЕ БАЗОВОЙ ИНСТРУКЦИИ WQL WHERE</span><span class="sxs-lookup"><span data-stu-id="d9ca1-170">USING THE BASIC WQL WHERE STATEMENT</span></span>

<span data-ttu-id="d9ca1-171">Оператор WHERE устанавливает условия для данных, возвращаемых инструкцией SELECT.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-171">A Where statement establishes conditions for the data that a Select statement returns.</span></span>

<span data-ttu-id="d9ca1-172">Инструкция WHERE имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d9ca1-172">The Where statement has the following format:</span></span>

```
where <property> <operator> <value>
```

<span data-ttu-id="d9ca1-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="d9ca1-173">For example:</span></span>

```
where Name = 'Notepad.exe'
```

<span data-ttu-id="d9ca1-174">Инструкция WHERE используется с инструкцией SELECT, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-174">The Where statement is used with the Select statement, as shown in the following example.</span></span>

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

<span data-ttu-id="d9ca1-175">При использовании инструкции WHERE имя и значение свойства должны быть точными.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-175">When using the Where statement, the property name and value must be accurate.</span></span>

<span data-ttu-id="d9ca1-176">Например, следующая команда получает процессы Notepad на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-176">For example, the following command gets the Notepad processes on the local computer.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

<span data-ttu-id="d9ca1-177">Однако следующая команда завершается ошибкой, так как имя процесса включает расширение имени файла ". exe".</span><span class="sxs-lookup"><span data-stu-id="d9ca1-177">However, the following command fails, because the process name includes the ".exe" file name extension.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a><span data-ttu-id="d9ca1-178">ОПЕРАТОРЫ СРАВНЕНИЯ ОПЕРАТОРОВ WHERE</span><span class="sxs-lookup"><span data-stu-id="d9ca1-178">WHERE STATEMENT COMPARISON OPERATORS</span></span>

<span data-ttu-id="d9ca1-179">Следующие операторы являются допустимыми в инструкции WQL WHERE.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-179">The following operators are valid in a WQL Where statement.</span></span>

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

<span data-ttu-id="d9ca1-180">Существуют и другие операторы, но это те, которые используются для сравнения.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-180">There are other operators, but these are the ones used for making comparisons.</span></span>

<span data-ttu-id="d9ca1-181">Например, следующий запрос выбирает свойства Name и Priority из процессов в классе Win32_Process, где приоритет процесса больше или равен 11.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-181">For example, the following query selects the Name and Priority properties from processes in the Win32_Process class where the process priority is greater than or equal to 11.</span></span> <span data-ttu-id="d9ca1-182">Командлет Get-WmiObject выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-182">The Get-WmiObject cmdlet runs the query.</span></span>

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a><span data-ttu-id="d9ca1-183">ИСПОЛЬЗОВАНИЕ ОПЕРАТОРОВ WQL В ПАРАМЕТРЕ FILTER</span><span class="sxs-lookup"><span data-stu-id="d9ca1-183">USING THE WQL OPERATORS IN THE FILTER PARAMETER</span></span>

<span data-ttu-id="d9ca1-184">Операторы WQL также можно использовать в значении параметра Filter командлетов Get-WmiObject или Get-CimInstance, а также в значениях параметров запроса этих командлетов.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-184">The WQL operators can also be used in the value of the Filter parameter of the Get-WmiObject or Get-CimInstance cmdlets, as well as in the value of the Query parameters of these cmdlets.</span></span>

<span data-ttu-id="d9ca1-185">Например, следующая команда возвращает свойства Name и ProcessID последних пяти процессов, которые имеют значения ProcessID, превышающие 1004.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-185">For example, the following command gets the Name and ProcessID properties of the last five processes that have ProcessID values greater than 1004.</span></span> <span data-ttu-id="d9ca1-186">Команда использует параметр Filter для указания условия ProcessID.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-186">The command uses the Filter parameter to specify the ProcessID condition.</span></span>

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a><span data-ttu-id="d9ca1-187">ИСПОЛЬЗОВАНИЕ ОПЕРАТОРА LIKE</span><span class="sxs-lookup"><span data-stu-id="d9ca1-187">USING THE LIKE OPERATOR</span></span>

<span data-ttu-id="d9ca1-188">Оператор Like позволяет использовать подстановочные знаки для фильтрации результатов WQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-188">The Like operator lets you use wildcard characters to filter the results of a WQL query.</span></span>

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

<span data-ttu-id="d9ca1-189">Если оператор Like используется без подстановочных знаков или операторов диапазона, он ведет себя как оператор равенства (=) и возвращает объекты только в том случае, если они точно соответствуют шаблону.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-189">When the Like operator is used without any wildcard characters or range operators, it behaves like the equality operator (=) and returns objects only when they are an exact match for the pattern.</span></span>

<span data-ttu-id="d9ca1-190">Операцию Range можно объединить с подстановочным знаком процента, чтобы создать простые, но мощные фильтры.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-190">You can combine the range operation with the percent wildcard character to create simple, yet powerful filters.</span></span>

### <a name="like-operator-examples"></a><span data-ttu-id="d9ca1-191">ПРИМЕРЫ ОПЕРАТОРОВ LIKE</span><span class="sxs-lookup"><span data-stu-id="d9ca1-191">LIKE OPERATOR EXAMPLES</span></span>

#### <a name="example-1-range"></a><span data-ttu-id="d9ca1-192">Пример 1: [ \<range> ]</span><span class="sxs-lookup"><span data-stu-id="d9ca1-192">EXAMPLE 1: [\<range>]</span></span>

<span data-ttu-id="d9ca1-193">Следующие команды запускают Блокнот, а затем выполняют поиск экземпляра класса Win32_Process, имя которого начинается с буквы в диапазоне от "H" до "N" (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="d9ca1-193">The following commands start Notepad and then search for an instance of the Win32_Process class that has a name that starts with a letter between "H" and "N" (case-insensitive).</span></span>

<span data-ttu-id="d9ca1-194">Запрос должен возвращать любой процесс из Hotpad.exe с помощью Notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-194">The query should return any process from Hotpad.exe through Notepad.exe.</span></span>

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a><span data-ttu-id="d9ca1-195">Пример 2: [ \<range> ] и%</span><span class="sxs-lookup"><span data-stu-id="d9ca1-195">EXAMPLE 2: [\<range>] and %</span></span>

<span data-ttu-id="d9ca1-196">Следующие команды выбирают все процессы, имена которых начинаются с буквы между A и P (без учета регистра), за которым следует ноль или более букв в любом сочетании.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-196">The following commands select all process that have a name that begins with a letter between A and P (case-insensitive) followed by zero or more letters in any combination.</span></span>

<span data-ttu-id="d9ca1-197">Командлет Get-WmiObject выполняет запрос, командлет Select-Object получает свойства Name и ProcessID, а командлет Sort-Object сортирует результаты в алфавитном порядке по имени.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-197">The Get-WmiObject cmdlet runs the query, the Select-Object cmdlet gets the Name and ProcessID properties, and the Sort-Object cmdlet sorts the results in alphabetical order by name.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a><span data-ttu-id="d9ca1-198">Пример 3. не в диапазоне (^)</span><span class="sxs-lookup"><span data-stu-id="d9ca1-198">EXAMPLE 3: Not in Range (^)</span></span>

<span data-ttu-id="d9ca1-199">Следующая команда получает процессы, имена которых не начинаются с одной из следующих букв: A, S, W, P, R, C, U, N</span><span class="sxs-lookup"><span data-stu-id="d9ca1-199">The following command gets processes whose names do not begin with any of the following letters: A, S, W, P, R, C, U, N</span></span>

<span data-ttu-id="d9ca1-200">и с последующей длиной не более букв.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-200">and followed zero or more letters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a><span data-ttu-id="d9ca1-201">Пример 4. любые символы--или None (%)</span><span class="sxs-lookup"><span data-stu-id="d9ca1-201">EXAMPLE 4: Any characters -- or none (%)</span></span>

<span data-ttu-id="d9ca1-202">Следующие команды получают процессы, имена которых начинаются с "Calc".</span><span class="sxs-lookup"><span data-stu-id="d9ca1-202">The following commands get processes that have names that begin with "calc".</span></span>
<span data-ttu-id="d9ca1-203">Символ% в WQL эквивалентен символу звездочки ( \* ) в регулярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-203">The % symbol in WQL is equivalent to the asterisk (\*) symbol in regular expressions.</span></span>

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a><span data-ttu-id="d9ca1-204">Пример 5. один символ (_)</span><span class="sxs-lookup"><span data-stu-id="d9ca1-204">EXAMPLE 5: One character (_)</span></span>

<span data-ttu-id="d9ca1-205">Следующие команды получают процессы, имена которых имеют следующий шаблон: "c_lc.exe", где символ подчеркивания представляет любой символ.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-205">The following commands get processes that have names that have the following pattern, "c_lc.exe" where the underscore character represents any one character.</span></span> <span data-ttu-id="d9ca1-206">Этот шаблон соответствует любому имени из calc.exe с помощью czlc.exe или c9lc.exe, но не соответствует именам, в которых символы "c" и "l" разделены более чем одним символом.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-206">This pattern matches any name from calc.exe through czlc.exe, or c9lc.exe, but does not match names in which the "c" and "l" are separated by more than one character.</span></span>

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a><span data-ttu-id="d9ca1-207">Пример 6. точное совпадение</span><span class="sxs-lookup"><span data-stu-id="d9ca1-207">EXAMPLE 6: Exact match</span></span>

<span data-ttu-id="d9ca1-208">Следующие команды получают процессы с именем WLIDSVC.exe.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-208">The following commands get processes named WLIDSVC.exe.</span></span> <span data-ttu-id="d9ca1-209">Несмотря на то, что запрос использует ключевое слово LIKE, он требует точного соответствия, так как значение не содержит подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-209">Even though the query uses the Like keyword, it requires an exact match, because the value does not include any wildcard characters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a><span data-ttu-id="d9ca1-210">ИСПОЛЬЗОВАНИЕ ОПЕРАТОРА OR</span><span class="sxs-lookup"><span data-stu-id="d9ca1-210">USING THE OR OPERATOR</span></span>

<span data-ttu-id="d9ca1-211">Чтобы указать несколько независимых условий, используйте ключевое слово или.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-211">To specify multiple independent conditions, use the Or keyword.</span></span> <span data-ttu-id="d9ca1-212">Ключевое слово или присутствует в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-212">The Or keyword appears in the Where clause.</span></span> <span data-ttu-id="d9ca1-213">Он выполняет включающую операцию или для двух (или более) условий и возвращает элементы, соответствующие любому из условий.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-213">It performs an inclusive OR operation on two (or more) conditions and returns items that meet any of the conditions.</span></span>

<span data-ttu-id="d9ca1-214">Оператор или имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d9ca1-214">The Or operator has the following format:</span></span>

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

<span data-ttu-id="d9ca1-215">Например, следующие команды получают все экземпляры класса WMI Win32_Process, но возвращают их только в том случае, если имя процесса имеет значение winword.exe или excel.exe.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-215">For example, the following commands get all instances of the Win32_Process WMI class but returns them only if the process name is winword.exe or excel.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

<span data-ttu-id="d9ca1-216">Оператор или можно использовать с более чем двумя условиями.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-216">The Or statement can be used with more than two conditions.</span></span> <span data-ttu-id="d9ca1-217">В следующем запросе инструкция или возвращает Winword.exe, Excel.exe или Powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-217">In the following query, the Or statement gets Winword.exe, Excel.exe, or Powershell.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a><span data-ttu-id="d9ca1-218">ИСПОЛЬЗОВАНИЕ ОПЕРАТОРА AND</span><span class="sxs-lookup"><span data-stu-id="d9ca1-218">USING THE AND OPERATOR</span></span>

<span data-ttu-id="d9ca1-219">Чтобы указать несколько связанных условий, используйте ключевое слово и.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-219">To specify multiple related conditions, use the And keyword.</span></span> <span data-ttu-id="d9ca1-220">Ключевое слово и отображается в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-220">The And keyword appears in the Where clause.</span></span> <span data-ttu-id="d9ca1-221">Он возвращает элементы, соответствующие всем условиям.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-221">It returns items that meet all of the conditions.</span></span>

<span data-ttu-id="d9ca1-222">Оператор and имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d9ca1-222">The And operator has the following format:</span></span>

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

<span data-ttu-id="d9ca1-223">Например, следующие команды получают процессы с именем "Winword.exe" и ИДЕНТИФИКАТОРом процесса 6512.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-223">For example, the following commands get processes that have a name of "Winword.exe" and the process ID of 6512.</span></span>

<span data-ttu-id="d9ca1-224">Обратите внимание, что команды используют командлет Get-CimInstance.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-224">Note that the commands use the Get-CimInstance cmdlet.</span></span>

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

<span data-ttu-id="d9ca1-225">Все операторы, включая операторы LIKE, допустимы с операторами OR и.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-225">All operators, including the Like operators are valid with the Or and And operators.</span></span> <span data-ttu-id="d9ca1-226">Кроме того, можно сочетать операторы OR и и в одном запросе с круглыми скобками, которые указывают Windows PowerShell, какие предложения должны обрабатываться первыми.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-226">And, you can combine the Or and And operators in a single query with parentheses that tell Windows PowerShell which clauses to process first.</span></span>

<span data-ttu-id="d9ca1-227">Эта команда использует символ продолжения Windows PowerShell ('), разделите команду на две строки.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-227">This command uses the Windows PowerShell continuation character (\`) divide the command into two lines.</span></span>

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a><span data-ttu-id="d9ca1-228">ПОИСК ЗНАЧЕНИЙ NULL</span><span class="sxs-lookup"><span data-stu-id="d9ca1-228">SEARCHING FOR NULL VALUES</span></span>

<span data-ttu-id="d9ca1-229">Поиск значений NULL в WMI является сложной задачей, так как это может привести к непредсказуемым результатам.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-229">Searching for null values in WMI is challenging, because it can lead to unpredictable results.</span></span> <span data-ttu-id="d9ca1-230">Значение NULL не равно нулю и не является эквивалентным или пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-230">Null is not zero and it is not equivalent or to an empty string.</span></span> <span data-ttu-id="d9ca1-231">Некоторые свойства класса WMI инициализированы, а другие — нет, поэтому поиск значений NULL может не работать для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-231">Some WMI class properties are initialized and others are not, so a search for null might not work for all properties.</span></span>

<span data-ttu-id="d9ca1-232">Чтобы найти значения NULL, используйте оператор is со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-232">To search for null values, use the Is operator with a value of "null".</span></span>

<span data-ttu-id="d9ca1-233">Например, следующие команды получают процессы, имеющие значение NULL для свойства Инталлдате.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-233">For example, the following commands get processes that have a null value for the IntallDate property.</span></span> <span data-ttu-id="d9ca1-234">Команды возвращают множество процессов.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-234">The commands return many processes.</span></span>

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="d9ca1-235">В отличие от этого, следующая команда возвращает учетные записи пользователей, имеющие значение NULL для свойства Description.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-235">In contrast, the following command, gets user accounts that have a null value for the Description property.</span></span> <span data-ttu-id="d9ca1-236">Эта команда не возвращает никаких учетных записей пользователей, хотя большинство учетных записей пользователей не имеют значения для свойства Description.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-236">This command does not return any user accounts, even though most user accounts do not have any value for the Description property.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="d9ca1-237">Чтобы найти учетные записи пользователей, не имеющие значения для свойства Description, используйте оператор равенства, чтобы получить пустую строку.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-237">To find the user accounts that have no value for the Description property, use the equality operator to get an empty string.</span></span> <span data-ttu-id="d9ca1-238">Чтобы представить пустую строку, используйте две последовательные одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-238">To represent the empty string, use two consecutive single quotation marks.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a><span data-ttu-id="d9ca1-239">ИСПОЛЬЗОВАНИЕ TRUE ИЛИ FALSE</span><span class="sxs-lookup"><span data-stu-id="d9ca1-239">USING TRUE OR FALSE</span></span>

<span data-ttu-id="d9ca1-240">Для получения логических значений в свойствах объектов WMI используйте значения true и false.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-240">To get Boolean values in the properties of WMI objects, use True and False.</span></span>
<span data-ttu-id="d9ca1-241">Для них регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-241">They are not case sensitive.</span></span>

<span data-ttu-id="d9ca1-242">Следующий WQL-запрос возвращает только локальные учетные записи пользователей с компьютера, присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-242">The following WQL query returns only local user accounts from a domain joined computer.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

<span data-ttu-id="d9ca1-243">Чтобы найти учетные записи домена, используйте значение false, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-243">To find domain accounts, use a value of False, as shown in the following example.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a><span data-ttu-id="d9ca1-244">ИСПОЛЬЗОВАНИЕ ESCAPE-СИМВОЛА</span><span class="sxs-lookup"><span data-stu-id="d9ca1-244">USING THE ESCAPE CHARACTER</span></span>

<span data-ttu-id="d9ca1-245">WQL использует обратную косую черту ( \) в качестве escape-символа).</span><span class="sxs-lookup"><span data-stu-id="d9ca1-245">WQL uses the backslash (\) as its escape character.</span></span> <span data-ttu-id="d9ca1-246">Это отличается от Windows PowerShell, в котором используется символ обратной кавычки (').</span><span class="sxs-lookup"><span data-stu-id="d9ca1-246">This is different from Windows PowerShell, which uses the backtick character (\`).</span></span>

<span data-ttu-id="d9ca1-247">Кавычки и символы, используемые в кавычках, часто требуют экранирования, чтобы они не были правильно интерпретированы.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-247">Quotation marks, and the characters used for quotation marks, often need to be escaped so that they are not misinterpreted.</span></span>

<span data-ttu-id="d9ca1-248">Чтобы найти пользователя, имя которого содержит одинарные кавычки, используйте обратную косую черту для экранирования одиночных кавычек, как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-248">To find a user whose name includes a single quotation mark, use a backslash to escape the single quotation mark, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

<span data-ttu-id="d9ca1-249">В некоторых случаях обратная косая черта также должна быть экранирована.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-249">In some case, the backslash also needs to be escaped.</span></span> <span data-ttu-id="d9ca1-250">Например, следующие команды создают недопустимую ошибку запроса из-за обратной косой черты в значении заголовка.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-250">For example, the following commands generate an Invalid Query error due to the backslash in the Caption value.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

<span data-ttu-id="d9ca1-251">Чтобы экранировать обратную косую черту, используйте второй символ обратной косой черты, как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="d9ca1-251">To escape the backslash, use a second backslash character, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a><span data-ttu-id="d9ca1-252">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="d9ca1-252">SEE ALSO</span></span>

[<span data-ttu-id="d9ca1-253">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="d9ca1-253">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="d9ca1-254">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="d9ca1-254">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="d9ca1-255">about_WMI</span><span class="sxs-lookup"><span data-stu-id="d9ca1-255">about_WMI</span></span>](about_WMI.md)

[<span data-ttu-id="d9ca1-256">about_WMI_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d9ca1-256">about_WMI_Cmdlets</span></span>](about_WMI_Cmdlets.md)
