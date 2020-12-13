---
ms.date: 09/13/2016
ms.topic: reference
title: Определение методов по умолчанию для объектов
description: Определение методов по умолчанию для объектов
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355533"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="61384-103">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="61384-103">Defining Default Methods for Objects</span></span>

<span data-ttu-id="61384-104">При расширении .NET Framework объектов в объекты можно добавлять методы кода и методы скриптов.</span><span class="sxs-lookup"><span data-stu-id="61384-104">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="61384-105">XML-код, используемый для определения этих методов, описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="61384-105">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="61384-106">Примеры в следующих разделах взяты из `Types.ps1xml` файла типов в каталоге установки Windows PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="61384-106">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="61384-107">Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="61384-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="61384-108">Методы кода</span><span class="sxs-lookup"><span data-stu-id="61384-108">Code methods</span></span>

<span data-ttu-id="61384-109">Метод Code ссылается на статический метод объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61384-109">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="61384-110">В следующем примере метод **ToString** добавляется в тип [ узлаSystem.Xml.Xml](/dotnet/api/System.Xml.XmlNode) .</span><span class="sxs-lookup"><span data-stu-id="61384-110">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="61384-111">Элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) определяет расширенный метод как метод кода.</span><span class="sxs-lookup"><span data-stu-id="61384-111">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="61384-112">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="61384-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="61384-113">И элемент [кодереференце](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) указывает статический метод.</span><span class="sxs-lookup"><span data-stu-id="61384-113">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="61384-114">Можно также добавить элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="61384-114">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="61384-115">Методы скриптов</span><span class="sxs-lookup"><span data-stu-id="61384-115">Script methods</span></span>

<span data-ttu-id="61384-116">Метод скрипта определяет метод, значение которого является выходным значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="61384-116">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="61384-117">В следующем примере метод **ConvertToDateTime** добавляется в тип [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) .</span><span class="sxs-lookup"><span data-stu-id="61384-117">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="61384-118">Элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod) определяет расширенный метод как метод скрипта.</span><span class="sxs-lookup"><span data-stu-id="61384-118">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element defines the extended method as a script method.</span></span> <span data-ttu-id="61384-119">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="61384-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="61384-120">И элемент [script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) указывает скрипт, который создает значение метода.</span><span class="sxs-lookup"><span data-stu-id="61384-120">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="61384-121">Можно также добавить элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="61384-121">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="61384-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61384-122">See also</span></span>

[<span data-ttu-id="61384-123">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61384-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
