---
title: Как написать простой командлет | Документация Майкрософт
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067745"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="40c64-102">Как написать командлет</span><span class="sxs-lookup"><span data-stu-id="40c64-102">How to write a cmdlet</span></span>

<span data-ttu-id="40c64-103">В этой статье показано, как написать командлет.</span><span class="sxs-lookup"><span data-stu-id="40c64-103">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="40c64-104">`Send-Greeting` Командлет принимает имя одного пользователя в качестве входных данных, а затем записывает приветствие этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="40c64-104">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="40c64-105">Несмотря на то, что командлет не выполняет много работы, в этом примере демонстрируются основные разделы командлета.</span><span class="sxs-lookup"><span data-stu-id="40c64-105">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="40c64-106">Описывается, как создать командлет</span><span class="sxs-lookup"><span data-stu-id="40c64-106">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="40c64-107">Чтобы объявить класс как командлет, используйте **командлет** атрибута.</span><span class="sxs-lookup"><span data-stu-id="40c64-107">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="40c64-108">**Командлет** атрибут задает глагол и существительное для имени командлета.</span><span class="sxs-lookup"><span data-stu-id="40c64-108">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="40c64-109">Дополнительные сведения о **командлет** атрибут, см. в разделе [объявление CmdletAttribute](cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="40c64-109">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="40c64-110">Укажите имя класса.</span><span class="sxs-lookup"><span data-stu-id="40c64-110">Specify the name of the class.</span></span>

3. <span data-ttu-id="40c64-111">Укажите, что командлет является производным от любого из следующих классов:</span><span class="sxs-lookup"><span data-stu-id="40c64-111">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="40c64-112">System.Management.Automation.Cmdlet</span><span class="sxs-lookup"><span data-stu-id="40c64-112">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="40c64-113">System.Management.Automation.PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="40c64-113">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="40c64-114">Чтобы определить параметры для командлета, используйте **параметр** атрибута.</span><span class="sxs-lookup"><span data-stu-id="40c64-114">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="40c64-115">В этом случае только один обязательный параметр указан.</span><span class="sxs-lookup"><span data-stu-id="40c64-115">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="40c64-116">Дополнительные сведения о **параметр** атрибут, см. в разделе [ParameterAttribute объявление](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="40c64-116">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="40c64-117">Переопределите метод, который обрабатывает входные данные обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="40c64-117">Override the input processing method that processes the input.</span></span> <span data-ttu-id="40c64-118">В этом случае [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределяется метод.</span><span class="sxs-lookup"><span data-stu-id="40c64-118">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="40c64-119">Чтобы написать приветствие, используйте метод [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span><span class="sxs-lookup"><span data-stu-id="40c64-119">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="40c64-120">Приветствие отображается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="40c64-120">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="40c64-121">Пример</span><span class="sxs-lookup"><span data-stu-id="40c64-121">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="40c64-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="40c64-122">See also</span></span>

[<span data-ttu-id="40c64-123">System.Management.Automation.Cmdlet</span><span class="sxs-lookup"><span data-stu-id="40c64-123">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="40c64-124">System.Management.Automation.PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="40c64-124">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="40c64-125">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="40c64-125">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="40c64-126">System.Management.Automation.Cmdlet.WriteObject</span><span class="sxs-lookup"><span data-stu-id="40c64-126">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="40c64-127">Объявление CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="40c64-127">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="40c64-128">Объявление ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="40c64-128">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="40c64-129">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40c64-129">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)