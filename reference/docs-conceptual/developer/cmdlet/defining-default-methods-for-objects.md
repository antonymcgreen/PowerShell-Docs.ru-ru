---
title: Определение методов по умолчанию для объектов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 10917de9e897fc1eed362430d63ff5b9cb7e813d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774598"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="164c2-102">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="164c2-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="164c2-103">При расширении .NET Framework объектов в объекты можно добавлять методы кода и методы скриптов.</span><span class="sxs-lookup"><span data-stu-id="164c2-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="164c2-104">XML-код, используемый для определения этих методов, описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="164c2-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="164c2-105">Примеры в следующих разделах взяты из `Types.ps1xml` файла типов в каталоге установки Windows PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="164c2-105">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="164c2-106">Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="164c2-106">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="164c2-107">Методы кода</span><span class="sxs-lookup"><span data-stu-id="164c2-107">Code methods</span></span>

<span data-ttu-id="164c2-108">Метод Code ссылается на статический метод объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="164c2-108">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="164c2-109">В следующем примере метод **ToString** добавляется в тип [узлаSystem.Xml.Xml](/dotnet/api/System.Xml.XmlNode) .</span><span class="sxs-lookup"><span data-stu-id="164c2-109">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="164c2-110">Элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) определяет расширенный метод как метод кода.</span><span class="sxs-lookup"><span data-stu-id="164c2-110">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="164c2-111">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="164c2-111">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="164c2-112">И элемент [кодереференце](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) указывает статический метод.</span><span class="sxs-lookup"><span data-stu-id="164c2-112">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="164c2-113">Можно также добавить элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .</span><span class="sxs-lookup"><span data-stu-id="164c2-113">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a><span data-ttu-id="164c2-114">Методы скриптов</span><span class="sxs-lookup"><span data-stu-id="164c2-114">Script methods</span></span>

<span data-ttu-id="164c2-115">Метод скрипта определяет метод, значение которого является выходным значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="164c2-115">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="164c2-116">В следующем примере метод **ConvertToDateTime** добавляется в тип [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) .</span><span class="sxs-lookup"><span data-stu-id="164c2-116">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="164c2-117">Элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) определяет расширенный метод как метод скрипта.</span><span class="sxs-lookup"><span data-stu-id="164c2-117">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element defines the extended method as a script method.</span></span> <span data-ttu-id="164c2-118">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="164c2-118">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="164c2-119">И элемент [script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) указывает скрипт, который создает значение метода.</span><span class="sxs-lookup"><span data-stu-id="164c2-119">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="164c2-120">Можно также добавить элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .</span><span class="sxs-lookup"><span data-stu-id="164c2-120">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="164c2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="164c2-121">See also</span></span>

[<span data-ttu-id="164c2-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="164c2-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
