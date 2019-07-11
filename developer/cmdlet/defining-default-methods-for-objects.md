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
ms.openlocfilehash: af554cde5e888f2a008028010332caa473151622
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733981"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="7c5bb-102">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="7c5bb-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="7c5bb-103">При расширении объекты .NET Framework, можно добавить код методов и методов скриптов к объектам.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span> <span data-ttu-id="7c5bb-104">XML, который используется для определения этих методов описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="7c5bb-105">В следующих разделах относятся, например из типов файла Types.ps1xml в каталоге установки Windows PowerShell (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="7c5bb-105">The examples in the following sections are from the Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="code-methods"></a><span data-ttu-id="7c5bb-106">Методы кода</span><span class="sxs-lookup"><span data-stu-id="7c5bb-106">Code Methods</span></span>

<span data-ttu-id="7c5bb-107">Метод код ссылается на статический метод объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-107">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="7c5bb-108">В следующем примере **ConvertLargeIntegerToInt64** добавляется метод [System.Xml.Xmlnode? Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode) типа.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-108">In the following example, the **ConvertLargeIntegerToInt64** method is added to the [System.Xml.Xmlnode?Displayproperty=Fullname](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="7c5bb-109">[PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) элемент определяет расширенный метод как метод код.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-109">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="7c5bb-110">[Имя](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) элемент задает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-110">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="7c5bb-111">И [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) элемент указывает статический метод.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-111">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="7c5bb-112">(Можно также добавить [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) элемент членам [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) элемент.)</span><span class="sxs-lookup"><span data-stu-id="7c5bb-112">(You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.)</span></span>

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodemethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a><span data-ttu-id="7c5bb-113">Методы сценариев</span><span class="sxs-lookup"><span data-stu-id="7c5bb-113">Script Methods</span></span>

<span data-ttu-id="7c5bb-114">Метод скрипт определяет метод, значение которого является результатом выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-114">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="7c5bb-115">В следующем примере **ConvertToDateTime** добавляется метод [System.Management.Managementobject? Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject) типа.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-115">In the following example, the **ConvertToDateTime** method is added to the [System.Management.Managementobject?Displayproperty=Fullname](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="7c5bb-116">[PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) элемент определяет расширенный метод как метод скрипта.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-116">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element defines the extended method as a script method.</span></span> <span data-ttu-id="7c5bb-117">[Имя](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) элемент задает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-117">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="7c5bb-118">И [скрипт](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) элемент указывает сценарий, который создает значение метода.</span><span class="sxs-lookup"><span data-stu-id="7c5bb-118">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="7c5bb-119">(Можно также добавить [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) элемент членам [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) элемент.)</span><span class="sxs-lookup"><span data-stu-id="7c5bb-119">(You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7c5bb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7c5bb-120">See Also</span></span>

[<span data-ttu-id="7c5bb-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c5bb-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
