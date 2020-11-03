---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227965"
---
# <span data-ttu-id="94823-103">New-WebServiceProxy</span><span class="sxs-lookup"><span data-stu-id="94823-103">New-WebServiceProxy</span></span>

## <span data-ttu-id="94823-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="94823-104">SYNOPSIS</span></span>
<span data-ttu-id="94823-105">Создает объект прокси веб-службы, который позволяет использовать веб-службу и управлять ею в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94823-105">Creates a Web service proxy object that lets you use and manage the Web service in PowerShell.</span></span>

## <span data-ttu-id="94823-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94823-106">SYNTAX</span></span>

### <span data-ttu-id="94823-107">Неучетные данные (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="94823-107">NoCredentials (Default)</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### <span data-ttu-id="94823-108">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="94823-108">Credential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="94823-109">уседефаулткредентиал</span><span class="sxs-lookup"><span data-stu-id="94823-109">UseDefaultCredential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## <span data-ttu-id="94823-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="94823-110">DESCRIPTION</span></span>

<span data-ttu-id="94823-111">`New-WebServiceProxy`Командлет позволяет использовать веб-службу в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94823-111">The `New-WebServiceProxy` cmdlet lets you use a Web service in PowerShell.</span></span> <span data-ttu-id="94823-112">Командлет подключается к веб-службе и создает объект прокси веб-службы в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94823-112">The cmdlet connects to a Web service and creates a Web service proxy object in PowerShell.</span></span> <span data-ttu-id="94823-113">Прокси-объект можно использовать для управления веб-службой.</span><span class="sxs-lookup"><span data-stu-id="94823-113">You can use the proxy object to manage the Web service.</span></span>

<span data-ttu-id="94823-114">Веб-служба — это программа на основе XML, которая обменивается данными по сети, особенно через Интернет.</span><span class="sxs-lookup"><span data-stu-id="94823-114">A Web service is an XML-based program that exchanges data over a network, especially over the Internet.</span></span> <span data-ttu-id="94823-115">Платформа Microsoft .NET Framework включает прокси-объекты веб-служб, представляющие веб-службы в виде объектов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94823-115">The Microsoft .NET Framework provides Web service proxy objects that represent the Web service as a .NET Framework object.</span></span>

## <span data-ttu-id="94823-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="94823-116">EXAMPLES</span></span>

### <span data-ttu-id="94823-117">Пример 1. Создание учетной записи-посредника для веб-службы</span><span class="sxs-lookup"><span data-stu-id="94823-117">Example 1: Create a proxy for a Web service</span></span>

<span data-ttu-id="94823-118">В этом примере создается .NET Framework прокси веб-службы калькулятора в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94823-118">This example creates a .NET Framework proxy of the calculator Web service in Windows PowerShell.</span></span>

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### <span data-ttu-id="94823-119">Пример 2. Создание прокси для веб-службы и указание пространства имен и класса</span><span class="sxs-lookup"><span data-stu-id="94823-119">Example 2: Create a proxy for a Web service and specify namespace and class</span></span>

<span data-ttu-id="94823-120">В этом примере `New-WebServiceProxy` командлет используется для создания .NET Framework прокси веб-службы калькулятора.</span><span class="sxs-lookup"><span data-stu-id="94823-120">This example uses the `New-WebServiceProxy` cmdlet to create a .NET Framework proxy of the calculator Web service.</span></span>

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

<span data-ttu-id="94823-121">В команде используется параметр **URI** для указания универсального кода ресурса (URI), а также параметров **пространства имен** и **класса** для указания пространства имен и класса объекта.</span><span class="sxs-lookup"><span data-stu-id="94823-121">The command uses the **Uri** parameter to specify the URI and the **Namespace** and **Class** parameters to specify the namespace and class of the object.</span></span>

### <span data-ttu-id="94823-122">Пример 3. Отображение методов прокси веб-службы</span><span class="sxs-lookup"><span data-stu-id="94823-122">Example 3: Display methods of a Web service proxy</span></span>

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

<span data-ttu-id="94823-123">В этом примере `Get-Member` командлет используется для вывода методов объекта прокси веб-службы в `$calc` переменной.</span><span class="sxs-lookup"><span data-stu-id="94823-123">This example uses the `Get-Member` cmdlet to display the methods of the Web service proxy object in the `$calc` variable.</span></span> <span data-ttu-id="94823-124">Мы используем эти методы в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="94823-124">We uses these methods in the following example.</span></span>

<span data-ttu-id="94823-125">Обратите внимание, что имя **TypeName** объекта прокси, WebServiceProxy, отражает имена пространств имен и классов, которые были указаны в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="94823-125">Notice that the **TypeName** of the proxy object, WebServiceProxy, reflects the namespace and class names that were specified in the previous example.</span></span>

### <span data-ttu-id="94823-126">Пример 4. использование прокси веб-службы</span><span class="sxs-lookup"><span data-stu-id="94823-126">Example 4: Use a Web service proxy</span></span>

```powershell
PS> $calc.Multiply(6,7)
42
```

<span data-ttu-id="94823-127">В этом примере используется прокси веб-службы, хранящийся в `$calc` переменной.</span><span class="sxs-lookup"><span data-stu-id="94823-127">This example uses the Web service proxy stored in the `$calc` variable.</span></span> <span data-ttu-id="94823-128">Команда использует метод **умножения** прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="94823-128">The command uses the **Multiply** method of the proxy.</span></span>

## <span data-ttu-id="94823-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94823-129">PARAMETERS</span></span>

### <span data-ttu-id="94823-130">-Class</span><span class="sxs-lookup"><span data-stu-id="94823-130">-Class</span></span>

<span data-ttu-id="94823-131">Задает имя прокси-класса, который командлет создает для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="94823-131">Specifies a name for the proxy class that the cmdlet creates for the Web service.</span></span> <span data-ttu-id="94823-132">Значение этого параметра используется вместе с параметром **Namespace** , чтобы предоставить полное имя класса.</span><span class="sxs-lookup"><span data-stu-id="94823-132">The value of this parameter is used together with the **Namespace** parameter to provide a fully qualified name for the class.</span></span> <span data-ttu-id="94823-133">Значение по умолчанию создается на основе универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="94823-133">The default value is generated from the Uniform Resource Identifier (URI).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94823-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="94823-134">-Credential</span></span>

<span data-ttu-id="94823-135">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="94823-135">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="94823-136">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="94823-136">The default is the current user.</span></span> <span data-ttu-id="94823-137">Этот параметр служит альтернативой параметру **UseDefaultCredential** .</span><span class="sxs-lookup"><span data-stu-id="94823-137">This is an alternative to using the **UseDefaultCredential** parameter.</span></span>

<span data-ttu-id="94823-138">Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="94823-138">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="94823-139">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="94823-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94823-140">-Namespace</span><span class="sxs-lookup"><span data-stu-id="94823-140">-Namespace</span></span>

<span data-ttu-id="94823-141">Задает пространство имен для нового класса.</span><span class="sxs-lookup"><span data-stu-id="94823-141">Specifies a namespace for the new class.</span></span>

<span data-ttu-id="94823-142">Значение этого параметра используется вместе со значением параметра **Class** для создания полного имени класса.</span><span class="sxs-lookup"><span data-stu-id="94823-142">The value of this parameter is used together with the value of the **Class** parameter to generate a fully qualified name for the class.</span></span> <span data-ttu-id="94823-143">Значение по умолчанию — **Microsoft. PowerShell. Commands. неввебсервицепрокси. аутоженератедтипес** плюс тип, созданный из универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="94823-143">The default value is **Microsoft.PowerShell.Commands.NewWebserviceProxy.AutogeneratedTypes** plus a type that is generated from the URI.</span></span>

<span data-ttu-id="94823-144">Можно задать значение параметра **пространства имен** , чтобы можно было обращаться к нескольким веб-службам с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="94823-144">You can set the value of the **Namespace** parameter so that you can access multiple Web services that have the same name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94823-145">— URI</span><span class="sxs-lookup"><span data-stu-id="94823-145">-Uri</span></span>

<span data-ttu-id="94823-146">Задает URI веб-службы.</span><span class="sxs-lookup"><span data-stu-id="94823-146">Specifies the URI of the Web service.</span></span> <span data-ttu-id="94823-147">Введите URI или путь и имя файла, содержащего описание службы.</span><span class="sxs-lookup"><span data-stu-id="94823-147">Enter a URI or the path and filename of a file that contains a service description.</span></span>

<span data-ttu-id="94823-148">URI должен возвращать `.asmx` страницу или страницу, которая возвращает описание службы.</span><span class="sxs-lookup"><span data-stu-id="94823-148">The URI must return an `.asmx` page or to a page that returns a service description.</span></span> <span data-ttu-id="94823-149">Чтобы вернуть описание службы веб-службы, созданной с помощью ASP.NET, добавьте "? WSDL "по URL-адресу Web Service (например, `http://www.contoso.com/MyWebService.asmx?WSDL` ).</span><span class="sxs-lookup"><span data-stu-id="94823-149">To return a service description of a Web service that was created using ASP.NET, append "?WSDL" to the URL of the Web service (for example, `http://www.contoso.com/MyWebService.asmx?WSDL`).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94823-150">-Уседефаулткредентиал</span><span class="sxs-lookup"><span data-stu-id="94823-150">-UseDefaultCredential</span></span>

<span data-ttu-id="94823-151">Указывает, что этот командлет использует учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94823-151">Indicates that this cmdlet uses the default credential.</span></span> <span data-ttu-id="94823-152">Этот командлет задает для свойства **уседефаулткредентиал** в результирующем прокси-объекте значение true.</span><span class="sxs-lookup"><span data-stu-id="94823-152">This cmdlet sets the **UseDefaultCredential** property in the resulting proxy object to True.</span></span> <span data-ttu-id="94823-153">Это альтернатива использованию параметра **Credential** .</span><span class="sxs-lookup"><span data-stu-id="94823-153">This is an alternative to using the **Credential** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94823-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="94823-154">CommonParameters</span></span>

<span data-ttu-id="94823-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="94823-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94823-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="94823-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94823-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="94823-157">INPUTS</span></span>

### <span data-ttu-id="94823-158">Нет</span><span class="sxs-lookup"><span data-stu-id="94823-158">None</span></span>

<span data-ttu-id="94823-159">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="94823-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="94823-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="94823-160">OUTPUTS</span></span>

### <span data-ttu-id="94823-161">Объект прокси веб-службы</span><span class="sxs-lookup"><span data-stu-id="94823-161">A Web service proxy object</span></span>

<span data-ttu-id="94823-162">Этот командлет возвращает объект прокси веб-службы.</span><span class="sxs-lookup"><span data-stu-id="94823-162">This cmdlet returns a Web service proxy object.</span></span> <span data-ttu-id="94823-163">Пространство имен и класс объекта определяются параметрами команды.</span><span class="sxs-lookup"><span data-stu-id="94823-163">The namespace and class of the object are determined by the parameters of the command.</span></span> <span data-ttu-id="94823-164">Значение по умолчанию создается на основе входного универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="94823-164">The default is generated from the input URI.</span></span>

## <span data-ttu-id="94823-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="94823-165">NOTES</span></span>

<span data-ttu-id="94823-166">`New-WebServiceProxy` использует класс **System .NET. WebClient** для загрузки указанной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="94823-166">`New-WebServiceProxy` uses the **System.Net.WebClient** class to load the specified Web service.</span></span>

## <span data-ttu-id="94823-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="94823-167">RELATED LINKS</span></span>

[<span data-ttu-id="94823-168">New-Service</span><span class="sxs-lookup"><span data-stu-id="94823-168">New-Service</span></span>](New-Service.md)
