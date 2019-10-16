---
title: Динамические параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 19d31f6b619dff23e7e35bb53d2397f4f41eb728
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369883"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="bfc6a-102">Динамические параметры командлета</span><span class="sxs-lookup"><span data-stu-id="bfc6a-102">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="bfc6a-103">Командлеты могут определять параметры, доступные пользователю в особых условиях, например, если аргумент другого параметра является определенным значением.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-103">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="bfc6a-104">Эти параметры добавляются во время выполнения и называются динамическими параметрами, так как они добавляются только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-104">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="bfc6a-105">Например, можно создать командлет, добавляющий несколько параметров только в том случае, если указан определенный параметр Switch.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-105">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc6a-106">Поставщики и функции PowerShell также могут определять динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-106">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="bfc6a-107">Динамические параметры в командлетах PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfc6a-107">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="bfc6a-108">PowerShell использует динамические параметры в нескольких командлетах поставщика.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-108">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="bfc6a-109">Например, командлеты `Get-Item` и `Get-ChildItem` добавляют параметр **CodeSigningCert** во время выполнения, когда параметр **path** указывает путь к поставщику **сертификата** .</span><span class="sxs-lookup"><span data-stu-id="bfc6a-109">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="bfc6a-110">Если параметр **path** задает путь для другого поставщика, параметр **CodeSigningCert** недоступен.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-110">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="bfc6a-111">В следующих примерах показано, как параметр **CodeSigningCert** добавляется во время выполнения при выполнении `Get-Item`.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-111">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="bfc6a-112">В этом примере среда выполнения PowerShell добавила параметр, а командлет — успешно.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-112">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="bfc6a-113">В этом примере указывается диск **файловой** системы, и возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-113">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="bfc6a-114">Сообщение об ошибке указывает, что не удается найти параметр **CodeSigningCert** .</span><span class="sxs-lookup"><span data-stu-id="bfc6a-114">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="bfc6a-115">Поддержка динамических параметров</span><span class="sxs-lookup"><span data-stu-id="bfc6a-115">Support for dynamic parameters</span></span>

<span data-ttu-id="bfc6a-116">Для поддержки динамических параметров в код командлета должны быть добавлены следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-116">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="bfc6a-117">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="bfc6a-117">Interface</span></span>

<span data-ttu-id="bfc6a-118">[System. Management. Automation. идинамикпараметерс](/dotnet/api/System.Management.Automation.IDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="bfc6a-118">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="bfc6a-119">Этот интерфейс предоставляет метод, который получает динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-119">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="bfc6a-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="bfc6a-120">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="bfc6a-121">Метод</span><span class="sxs-lookup"><span data-stu-id="bfc6a-121">Method</span></span>

<span data-ttu-id="bfc6a-122">[System. Management. Automation. идинамикпараметерс. жетдинамикпараметерс](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="bfc6a-122">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="bfc6a-123">Этот метод извлекает объект, содержащий определения динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-123">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="bfc6a-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="bfc6a-124">For example:</span></span>

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a><span data-ttu-id="bfc6a-125">Класс</span><span class="sxs-lookup"><span data-stu-id="bfc6a-125">Class</span></span>

<span data-ttu-id="bfc6a-126">Класс, определяющий динамические параметры, которые необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-126">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="bfc6a-127">Этот класс должен включать атрибут **Parameter** для каждого параметра, а также любые дополнительные атрибуты **псевдонима** и **проверки** , необходимые для командлета.</span><span class="sxs-lookup"><span data-stu-id="bfc6a-127">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="bfc6a-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="bfc6a-128">For example:</span></span>

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

<span data-ttu-id="bfc6a-129">Полный пример командлета, поддерживающего динамические параметры, см. [в разделе Объявление динамических параметров](./how-to-declare-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bfc6a-129">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bfc6a-130">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bfc6a-130">See also</span></span>

[<span data-ttu-id="bfc6a-131">System. Management. Automation. Идинамикпараметерс</span><span class="sxs-lookup"><span data-stu-id="bfc6a-131">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="bfc6a-132">System. Management. Automation. Идинамикпараметерс. Жетдинамикпараметерс</span><span class="sxs-lookup"><span data-stu-id="bfc6a-132">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="bfc6a-133">Объявление динамических параметров</span><span class="sxs-lookup"><span data-stu-id="bfc6a-133">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="bfc6a-134">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfc6a-134">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
