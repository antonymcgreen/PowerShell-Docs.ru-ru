---
title: Определение методов по умолчанию для объектов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fe744a-485f-4c21-9623-1cb546372211
caps.latest.revision: 9
ms.openlocfilehash: 346a194c6b4c81aa61a6331cdb62ae380a17bb1e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365693"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="7f69d-102">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="7f69d-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="7f69d-103">При расширении .NET Framework объектов в объекты можно добавлять методы кода и методы скриптов.</span><span class="sxs-lookup"><span data-stu-id="7f69d-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="7f69d-104">XML-код, используемый для определения этих методов, описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7f69d-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="7f69d-105">Примеры в следующих разделах относятся к файлу типов `Types.ps1xml` в каталоге установки Windows PowerShell (`$PSHOME`).</span><span class="sxs-lookup"><span data-stu-id="7f69d-105">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="7f69d-106">Дополнительные сведения см. в разделе [About types. ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="7f69d-106">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="7f69d-107">Методы кода</span><span class="sxs-lookup"><span data-stu-id="7f69d-107">Code methods</span></span>

<span data-ttu-id="7f69d-108">Метод Code ссылается на статический метод объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f69d-108">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="7f69d-109">В следующем примере метод **ToString** добавляется в тип [System. XML. XMLNode](/dotnet/api/System.Xml.XmlNode) .</span><span class="sxs-lookup"><span data-stu-id="7f69d-109">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="7f69d-110">Элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) определяет расширенный метод как метод кода.</span><span class="sxs-lookup"><span data-stu-id="7f69d-110">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="7f69d-111">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="7f69d-111">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="7f69d-112">И элемент [кодереференце](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) указывает статический метод.</span><span class="sxs-lookup"><span data-stu-id="7f69d-112">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="7f69d-113">Можно также добавить элемент [пскодемесод](/dotnet/api/system.management.automation.pscodemethod) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .</span><span class="sxs-lookup"><span data-stu-id="7f69d-113">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="7f69d-114">Методы скриптов</span><span class="sxs-lookup"><span data-stu-id="7f69d-114">Script methods</span></span>

<span data-ttu-id="7f69d-115">Метод скрипта определяет метод, значение которого является выходным значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="7f69d-115">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="7f69d-116">В следующем примере метод **ConvertToDateTime** добавляется в тип [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) .</span><span class="sxs-lookup"><span data-stu-id="7f69d-116">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="7f69d-117">Элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) определяет расширенный метод как метод скрипта.</span><span class="sxs-lookup"><span data-stu-id="7f69d-117">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element defines the extended method as a script method.</span></span> <span data-ttu-id="7f69d-118">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) указывает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="7f69d-118">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="7f69d-119">И элемент [script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) указывает скрипт, который создает значение метода.</span><span class="sxs-lookup"><span data-stu-id="7f69d-119">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="7f69d-120">Можно также добавить элемент [псскриптмесод](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) в элементы элемента [псмемберсетс](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) .</span><span class="sxs-lookup"><span data-stu-id="7f69d-120">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7f69d-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7f69d-121">See also</span></span>

[<span data-ttu-id="7f69d-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f69d-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
