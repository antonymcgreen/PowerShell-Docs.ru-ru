---
title: Параметры командлета динамической | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 2fc73b6ef5a862fafb7a3c8fe3da19ac71bafc05
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853810"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="c2bc6-102">Динамические параметры командлетов</span><span class="sxs-lookup"><span data-stu-id="c2bc6-102">Cmdlet Dynamic Parameters</span></span>

<span data-ttu-id="c2bc6-103">Командлеты можно определить параметры, доступные для пользователя специальных условиях, например, если аргумент другого параметра конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-103">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="c2bc6-104">Эти параметры будут добавлены во время выполнения и называются *динамических параметров* так, как они добавляются только в том случае, когда они нужны.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-104">These parameters are added at runtime and are referred to as *dynamic parameters* because they are added only when they are needed.</span></span> <span data-ttu-id="c2bc6-105">Например можно создать командлет, который добавляет несколько параметров, только в том случае, если указан параметр определенного коммутатора.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-105">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="c2bc6-106">Поставщики и функции Windows PowerShell можно также определить динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-106">Providers and Windows PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-windows-powershell-cmdlets"></a><span data-ttu-id="c2bc6-107">Динамические параметры в командлетах Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2bc6-107">Dynamic Parameters in Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c2bc6-108">Windows PowerShell использует динамические параметры в некоторых из его командлетов поставщика.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-108">Windows PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="c2bc6-109">Например `Get-Item` и `Get-ChildItem` добавьте командлеты `CodeSigningCert` параметра во время выполнения при `Path` параметр командлета путь поставщика сертификата.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-109">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a `CodeSigningCert` parameter at runtime when the `Path` parameter of the cmdlet specifies the Certificate provider path.</span></span> <span data-ttu-id="c2bc6-110">Если `Path` параметр командлета указывает путь для другого поставщика, `CodeSigningCert` параметра не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-110">If the `Path` parameter of the cmdlet specifies a path for a different provider, the `CodeSigningCert` parameter is not available.</span></span>

<span data-ttu-id="c2bc6-111">В следующих примерах показывается как `CodeSigningCert` добавлен параметр во время выполнения при `Get-Item` выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-111">The following examples show how the `CodeSigningCert` parameter is added at runtime when the `Get-Item` cmdlet is run.</span></span>

<span data-ttu-id="c2bc6-112">В первом примере среда выполнения Windows PowerShell добавлен параметр, а командлет прошла успешно.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-112">In the first example, the Windows PowerShell runtime has added the parameter, and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -codesigningcert
```

```output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="c2bc6-113">Во втором примере диск файловой системы указан и возвращается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-113">In the second example, a FileSystem drive is specified, and an error is returned.</span></span> <span data-ttu-id="c2bc6-114">Сообщение об ошибке указывает, что `CodeSigningCert` параметр не найден.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-114">The error message indicates that the `CodeSigningCert` parameter cannot be found.</span></span>

```powershell
Get-Item -Path C:\ -codesigningcert
```

```output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="c2bc6-115">Поддержка динамических параметров</span><span class="sxs-lookup"><span data-stu-id="c2bc6-115">Support for Dynamic Parameters</span></span>

<span data-ttu-id="c2bc6-116">Для поддержки динамических параметров, код командлета должен включать следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-116">To support dynamic parameters, the cmdlet code must include the following elements.</span></span>

<span data-ttu-id="c2bc6-117">[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) этот интерфейс предоставляет метод, который получает динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-117">[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="c2bc6-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="c2bc6-118">Example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

<span data-ttu-id="c2bc6-119">[System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) этот метод извлекает объект, который содержит определения динамических параметров.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-119">[System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="c2bc6-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="c2bc6-120">Example:</span></span>

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

<span data-ttu-id="c2bc6-121">Класс динамических параметров в этот класс определяет параметры для добавления.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-121">Dynamic Parameter class This class defines the parameters to be added.</span></span> <span data-ttu-id="c2bc6-122">Этот класс должен включать атрибут параметра для каждого параметра и дополнительные атрибуты псевдоним и проверки, которые необходимы с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="c2bc6-122">This class must include a Parameter attribute for each parameter and any optional Alias and Validation attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="c2bc6-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="c2bc6-123">Example:</span></span>

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

<span data-ttu-id="c2bc6-124">Полный пример, который поддерживает динамические параметры командлета, см. в разделе [как объявить динамических параметров](./how-to-declare-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c2bc6-124">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2bc6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c2bc6-125">See Also</span></span>

[<span data-ttu-id="c2bc6-126">System.Management.Automation.Idynamicparameters</span><span class="sxs-lookup"><span data-stu-id="c2bc6-126">System.Management.Automation.Idynamicparameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="c2bc6-127">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span><span class="sxs-lookup"><span data-stu-id="c2bc6-127">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="c2bc6-128">Как объявить динамических параметров</span><span class="sxs-lookup"><span data-stu-id="c2bc6-128">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="c2bc6-129">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2bc6-129">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
