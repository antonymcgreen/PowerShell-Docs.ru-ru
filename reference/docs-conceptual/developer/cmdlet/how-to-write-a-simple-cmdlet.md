---
title: Написание простого командлета | Документация Майкрософт
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 9bd72e8f97c194c98adb1049f5a966549113fd12
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563889"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="79ec0-102">Написание командлета</span><span class="sxs-lookup"><span data-stu-id="79ec0-102">How to write a cmdlet</span></span>

<span data-ttu-id="79ec0-103">В этой статье показано, как написать командлет.</span><span class="sxs-lookup"><span data-stu-id="79ec0-103">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="79ec0-104">`Send-Greeting`Командлет принимает одно имя пользователя в качестве входных данных, а затем записывает приветствие этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="79ec0-104">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="79ec0-105">Хотя командлет не выполняет много операций, в этом примере демонстрируются основные разделы командлета.</span><span class="sxs-lookup"><span data-stu-id="79ec0-105">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="79ec0-106">Действия по написанию командлета</span><span class="sxs-lookup"><span data-stu-id="79ec0-106">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="79ec0-107">Чтобы объявить класс в качестве командлета, используйте атрибут **командлета** .</span><span class="sxs-lookup"><span data-stu-id="79ec0-107">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="79ec0-108">Атрибут **командлета** задает глагол и существительное для имени командлета.</span><span class="sxs-lookup"><span data-stu-id="79ec0-108">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="79ec0-109">Дополнительные сведения об атрибуте **командлета** см. в описании [объявления CmdletAttribute](cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="79ec0-109">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="79ec0-110">Укажите имя класса.</span><span class="sxs-lookup"><span data-stu-id="79ec0-110">Specify the name of the class.</span></span>

3. <span data-ttu-id="79ec0-111">Укажите, что командлет является производным от любого из следующих классов:</span><span class="sxs-lookup"><span data-stu-id="79ec0-111">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="79ec0-112">System. Management. Automation. командлет</span><span class="sxs-lookup"><span data-stu-id="79ec0-112">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="79ec0-113">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="79ec0-113">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="79ec0-114">Чтобы определить параметры для командлета, используйте атрибут **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="79ec0-114">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="79ec0-115">В этом случае указывается только один обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="79ec0-115">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="79ec0-116">Дополнительные сведения об атрибуте **Parameter** см. в разделе [объявление параметераттрибуте](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="79ec0-116">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="79ec0-117">Переопределите метод обработки ввода, обрабатывающий входные данные.</span><span class="sxs-lookup"><span data-stu-id="79ec0-117">Override the input processing method that processes the input.</span></span> <span data-ttu-id="79ec0-118">В этом случае метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределен.</span><span class="sxs-lookup"><span data-stu-id="79ec0-118">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="79ec0-119">Чтобы написать приветствие, используйте метод [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span><span class="sxs-lookup"><span data-stu-id="79ec0-119">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="79ec0-120">Приветствие отображается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="79ec0-120">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="79ec0-121">Пример</span><span class="sxs-lookup"><span data-stu-id="79ec0-121">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="79ec0-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79ec0-122">See also</span></span>

[<span data-ttu-id="79ec0-123">System. Management. Automation. командлет</span><span class="sxs-lookup"><span data-stu-id="79ec0-123">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="79ec0-124">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="79ec0-124">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="79ec0-125">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="79ec0-125">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="79ec0-126">System. Management. Automation. командлет. WriteObject</span><span class="sxs-lookup"><span data-stu-id="79ec0-126">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="79ec0-127">Объявление CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="79ec0-127">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="79ec0-128">Объявление Параметераттрибуте</span><span class="sxs-lookup"><span data-stu-id="79ec0-128">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="79ec0-129">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ec0-129">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
