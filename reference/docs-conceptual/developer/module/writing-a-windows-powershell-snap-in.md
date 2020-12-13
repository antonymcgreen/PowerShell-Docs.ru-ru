---
ms.date: 09/13/2016
ms.topic: reference
title: Написание оснастки Windows PowerShell
description: Написание оснастки Windows PowerShell
ms.openlocfilehash: f658c2fa1211bfb77d2e8edd3999ce7f92df13bb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659443"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="7d697-103">Написание оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d697-103">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="7d697-104">В этом примере показано, как создать оснастку Windows PowerShell, которая может использоваться для регистрации всех командлетов и поставщиков Windows PowerShell в сборке.</span><span class="sxs-lookup"><span data-stu-id="7d697-104">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="7d697-105">При использовании этого типа оснастки не следует выбирать командлеты и поставщики, которые нужно зарегистрировать.</span><span class="sxs-lookup"><span data-stu-id="7d697-105">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="7d697-106">Чтобы создать оснастку, которая позволяет выбрать регистрируемые объекты, см. раздел [написание пользовательской оснастки Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="7d697-106">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="7d697-107">Написание оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d697-107">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="7d697-108">Добавьте атрибут Рунинсталлераттрибуте.</span><span class="sxs-lookup"><span data-stu-id="7d697-108">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="7d697-109">Создайте открытый класс, производный от класса [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="7d697-109">Create a public class that derives from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="7d697-110">В этом примере имя класса — «GetProcPSSnapIn01».</span><span class="sxs-lookup"><span data-stu-id="7d697-110">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="7d697-111">Добавьте открытое свойство для имени оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="7d697-111">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="7d697-112">При именовании оснасток не используйте следующие символы: `#` , `.` , `,` ,, `(` `)` , `{` , `}` , `[` , `]` , `&` , `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` `` ` `` ,,,,,,,,,,,,,, `*`</span><span class="sxs-lookup"><span data-stu-id="7d697-112">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

    <span data-ttu-id="7d697-113">В этом примере имя оснастки — «GetProcPSSnapIn01».</span><span class="sxs-lookup"><span data-stu-id="7d697-113">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="7d697-114">Добавьте открытое свойство для поставщика оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="7d697-114">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="7d697-115">В этом примере поставщиком является "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="7d697-115">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="7d697-116">Добавьте открытое свойство для ресурса поставщика оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="7d697-116">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="7d697-117">В этом примере ресурсом поставщика является "GetProcPSSnapIn01, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="7d697-117">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="7d697-118">Добавьте открытое свойство для описания оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="7d697-118">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="7d697-119">В этом примере описание: «это оснастка Windows PowerShell, которая регистрирует командлет Get-proc».</span><span class="sxs-lookup"><span data-stu-id="7d697-119">In this example, the description is "This is a Windows PowerShell snap-in that registers the  get-proc cmdlet".</span></span>

7. <span data-ttu-id="7d697-120">Добавьте открытое свойство для ресурса описания оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="7d697-120">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="7d697-121">В этом примере ресурсом поставщика является «GetProcPSSnapIn01, это оснастка Windows PowerShell, которая регистрирует командлет Get-proc».</span><span class="sxs-lookup"><span data-stu-id="7d697-121">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in  that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="7d697-122">Пример</span><span class="sxs-lookup"><span data-stu-id="7d697-122">Example</span></span>

<span data-ttu-id="7d697-123">В этом примере показано, как создать оснастку Windows PowerShell, которая может использоваться для регистрации командлета Get-Proc в оболочке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d697-123">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="7d697-124">Имейте в виду, что в этом примере полная сборка будет содержать только класс оснастки GetProcPSSnapIn01 и `Get-Proc` класс командлета.</span><span class="sxs-lookup"><span data-stu-id="7d697-124">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the `Get-Proc` cmdlet class.</span></span>

```csharp
[RunInstaller(true)]
public class GetProcPSSnapIn01 : PSSnapIn
{
  /// <summary>
  /// Create an instance of the GetProcPSSnapIn01 class.
  /// </summary>
  public GetProcPSSnapIn01()
         : base()
  {
  }

  /// <summary>
  /// Specify the name of the PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "GetProcPSSnapIn01";
    }
  }

  /// <summary>
  /// Specify the vendor for the PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,VendorName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
      return "GetProcPSSnapIn01,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
      return "GetProcPSSnapIn01,This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="7d697-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d697-125">See Also</span></span>

<span data-ttu-id="7d697-126">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="7d697-126">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="7d697-127">Пакет SDK Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d697-127">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
