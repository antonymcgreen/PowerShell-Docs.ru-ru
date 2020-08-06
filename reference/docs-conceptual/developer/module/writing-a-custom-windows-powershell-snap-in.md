---
title: Написание пользовательской оснастки Windows PowerShell | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- snap-ins [PowerShell SDK], custom PSSnapin example
- cmdlets [PowerShell SDK], specified in snap-ins
ms.openlocfilehash: 3672dcc2e962b6795888ab5be3d461380e379315
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779222"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="29a41-102">Написание пользовательской оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29a41-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="29a41-103">В этом примере показано, как создать оснастку Windows PowerShell, которая регистрирует определенные командлеты.</span><span class="sxs-lookup"><span data-stu-id="29a41-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="29a41-104">С помощью этого типа оснастки вы указываете, какие командлеты, поставщики, типы или форматы нужно зарегистрировать.</span><span class="sxs-lookup"><span data-stu-id="29a41-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="29a41-105">Дополнительные сведения о написании оснастки, которая регистрирует все командлеты и поставщики в сборке, см. [в разделе написание оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="29a41-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="29a41-106">Для создания оснастки Windows PowerShell, которая регистрирует определенные командлеты.</span><span class="sxs-lookup"><span data-stu-id="29a41-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="29a41-107">Добавьте атрибут Рунинсталлераттрибуте.</span><span class="sxs-lookup"><span data-stu-id="29a41-107">Add the RunInstallerAttribute attribute.</span></span>
2. <span data-ttu-id="29a41-108">Создайте открытый класс, производный от класса [System. Management. Automation. кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="29a41-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="29a41-109">В этом примере имя класса — «Кустомпсснапинтест».</span><span class="sxs-lookup"><span data-stu-id="29a41-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="29a41-110">Добавьте открытое свойство для имени оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="29a41-111">При именовании оснасток не используйте следующие символы: `#` , `.` , `,` ,, `(` `)` , `{` , `}` , `[` , `]` , `&` , `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` `` ` `` ,,,,,,,,,,,,,,`*`</span><span class="sxs-lookup"><span data-stu-id="29a41-111">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

   <span data-ttu-id="29a41-112">В этом примере имя оснастки — «Кустомпсснапинтест».</span><span class="sxs-lookup"><span data-stu-id="29a41-112">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="29a41-113">Добавьте открытое свойство для поставщика оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-113">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="29a41-114">В этом примере поставщиком является "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="29a41-114">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="29a41-115">Добавьте открытое свойство для ресурса поставщика оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-115">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="29a41-116">В этом примере ресурсом поставщика является "Кустомпсснапинтест, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="29a41-116">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="29a41-117">Добавьте открытое свойство для описания оснастки (обязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-117">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="29a41-118">В этом примере описание: "это пользовательская оснастка Windows PowerShell, которая включает `Test-HelloWorld` `Test-CustomSnapinTest` командлеты и".</span><span class="sxs-lookup"><span data-stu-id="29a41-118">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets".</span></span>

7. <span data-ttu-id="29a41-119">Добавьте открытое свойство для ресурса описания оснастки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-119">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="29a41-120">В этом примере ресурсом поставщика является:</span><span class="sxs-lookup"><span data-stu-id="29a41-120">In this example, the vendor resource is:</span></span>

   > <span data-ttu-id="29a41-121">Кустомпсснапинтест, это пользовательская оснастка Windows PowerShell, которая включает командлеты Test-HelloWorld и Test-Кустомснапинтест.</span><span class="sxs-lookup"><span data-stu-id="29a41-121">CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="29a41-122">Укажите командлеты, принадлежащие к пользовательской оснастке (необязательно), с помощью класса [System. Management. Automation. пространства. кмдлетконфигуратионентри](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) .</span><span class="sxs-lookup"><span data-stu-id="29a41-122">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="29a41-123">Добавляемые здесь сведения включают имя командлета, его тип .NET и имя файла справки командлета (формат имени файла справки командлета должен быть `name.dll-help.xml` ).</span><span class="sxs-lookup"><span data-stu-id="29a41-123">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be `name.dll-help.xml`).</span></span>

   <span data-ttu-id="29a41-124">В этом примере добавляются командлеты Test-HelloWorld и Тесткустомснапинтест.</span><span class="sxs-lookup"><span data-stu-id="29a41-124">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="29a41-125">Укажите поставщиков, принадлежащих к пользовательской оснастке (необязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-125">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="29a41-126">В этом примере не указаны поставщики.</span><span class="sxs-lookup"><span data-stu-id="29a41-126">This example does not specify any providers.</span></span>

10. <span data-ttu-id="29a41-127">Укажите типы, принадлежащие к пользовательской оснастке (необязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-127">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="29a41-128">В этом примере не указаны типы.</span><span class="sxs-lookup"><span data-stu-id="29a41-128">This example does not specify any types.</span></span>

11. <span data-ttu-id="29a41-129">Укажите форматы, принадлежащие к пользовательской оснастке (необязательно).</span><span class="sxs-lookup"><span data-stu-id="29a41-129">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="29a41-130">В этом примере не указаны никакие форматы.</span><span class="sxs-lookup"><span data-stu-id="29a41-130">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="29a41-131">Пример</span><span class="sxs-lookup"><span data-stu-id="29a41-131">Example</span></span>

<span data-ttu-id="29a41-132">В этом примере показано, как написать пользовательскую оснастку Windows PowerShell, которая может использоваться для регистрации `Test-HelloWorld` `Test-CustomSnapinTest` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="29a41-132">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets.</span></span> <span data-ttu-id="29a41-133">Имейте в виду, что в этом примере полная сборка может содержать другие командлеты и поставщики, которые не будут зарегистрированы в этой оснастке.</span><span class="sxs-lookup"><span data-stu-id="29a41-133">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
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
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
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
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="29a41-134">Дополнительные сведения о регистрации оснасток см. в разделе [Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85)) [руководства программиста Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md).</span><span class="sxs-lookup"><span data-stu-id="29a41-134">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="29a41-135">См. также</span><span class="sxs-lookup"><span data-stu-id="29a41-135">See Also</span></span>

<span data-ttu-id="29a41-136">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="29a41-136">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="29a41-137">Пакет SDK оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29a41-137">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
