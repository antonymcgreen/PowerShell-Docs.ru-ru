---
ms.date: 01/15/2019
ms.topic: reference
title: Как написать простой командлет
description: Как написать простой командлет
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646501"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="6993d-103">Написание командлета</span><span class="sxs-lookup"><span data-stu-id="6993d-103">How to write a cmdlet</span></span>

<span data-ttu-id="6993d-104">В этой статье показано, как написать командлет.</span><span class="sxs-lookup"><span data-stu-id="6993d-104">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="6993d-105">`Send-Greeting`Командлет принимает одно имя пользователя в качестве входных данных, а затем записывает приветствие этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="6993d-105">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="6993d-106">Хотя командлет не выполняет много операций, в этом примере демонстрируются основные разделы командлета.</span><span class="sxs-lookup"><span data-stu-id="6993d-106">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="6993d-107">Действия по написанию командлета</span><span class="sxs-lookup"><span data-stu-id="6993d-107">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="6993d-108">Чтобы объявить класс в качестве командлета, используйте атрибут **командлета** .</span><span class="sxs-lookup"><span data-stu-id="6993d-108">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="6993d-109">Атрибут **командлета** задает глагол и существительное для имени командлета.</span><span class="sxs-lookup"><span data-stu-id="6993d-109">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="6993d-110">Дополнительные сведения об атрибуте **командлета** см. в описании [объявления CmdletAttribute](cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="6993d-110">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="6993d-111">Укажите имя класса.</span><span class="sxs-lookup"><span data-stu-id="6993d-111">Specify the name of the class.</span></span>

3. <span data-ttu-id="6993d-112">Укажите, что командлет является производным от любого из следующих классов:</span><span class="sxs-lookup"><span data-stu-id="6993d-112">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="6993d-113">System. Management. Automation. командлет</span><span class="sxs-lookup"><span data-stu-id="6993d-113">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="6993d-114">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="6993d-114">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="6993d-115">Чтобы определить параметры для командлета, используйте атрибут **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="6993d-115">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="6993d-116">В этом случае указывается только один обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6993d-116">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="6993d-117">Дополнительные сведения об атрибуте **Parameter** см. в разделе [объявление параметераттрибуте](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="6993d-117">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="6993d-118">Переопределите метод обработки ввода, обрабатывающий входные данные.</span><span class="sxs-lookup"><span data-stu-id="6993d-118">Override the input processing method that processes the input.</span></span> <span data-ttu-id="6993d-119">В этом случае метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределен.</span><span class="sxs-lookup"><span data-stu-id="6993d-119">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="6993d-120">Чтобы написать приветствие, используйте метод [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span><span class="sxs-lookup"><span data-stu-id="6993d-120">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="6993d-121">Приветствие отображается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6993d-121">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="6993d-122">Пример</span><span class="sxs-lookup"><span data-stu-id="6993d-122">Example</span></span>

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="6993d-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6993d-123">See also</span></span>

[<span data-ttu-id="6993d-124">System. Management. Automation. командлет</span><span class="sxs-lookup"><span data-stu-id="6993d-124">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="6993d-125">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="6993d-125">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="6993d-126">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="6993d-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="6993d-127">System. Management. Automation. командлет. WriteObject</span><span class="sxs-lookup"><span data-stu-id="6993d-127">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="6993d-128">Объявление CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="6993d-128">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="6993d-129">Объявление Параметераттрибуте</span><span class="sxs-lookup"><span data-stu-id="6993d-129">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="6993d-130">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6993d-130">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
