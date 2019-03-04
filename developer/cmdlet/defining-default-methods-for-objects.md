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
ms.openlocfilehash: fa0f0371856d8723af7ec17a4306de209a481a18
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861410"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="fb1ad-102">Определение методов по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="fb1ad-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="fb1ad-103">При расширении объекты .NET Framework, можно добавить код методов и методов скриптов к объектам.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span> <span data-ttu-id="fb1ad-104">XML, который используется для определения этих методов описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="fb1ad-105">В следующих разделах относятся, например из типов файла Types.ps1xml в каталоге установки Windows PowerShell (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="fb1ad-105">The examples in the following sections are from the Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="code-methods"></a><span data-ttu-id="fb1ad-106">Методы кода</span><span class="sxs-lookup"><span data-stu-id="fb1ad-106">Code Methods</span></span>

<span data-ttu-id="fb1ad-107">Метод код ссылается на статический метод объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-107">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="fb1ad-108">В следующем примере **ConvertLargeIntegerToInt64** добавляется метод [System.Xml.Xmlnode? Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode) типа.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-108">In the following example, the **ConvertLargeIntegerToInt64** method is added to the [System.Xml.Xmlnode?Displayproperty=Fullname](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="fb1ad-109">[CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) элемент определяет расширенный метод как метод код.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-109">The [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) element defines the extended method as a code method.</span></span> <span data-ttu-id="fb1ad-110">[Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-110">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended method.</span></span> <span data-ttu-id="fb1ad-111">И [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b) элемент указывает статический метод.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-111">And, the [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b) element specifies the static method.</span></span> <span data-ttu-id="fb1ad-112">(Можно также добавить [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)</span><span class="sxs-lookup"><span data-stu-id="fb1ad-112">(You can also add the [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="fb1ad-113">Методы сценариев</span><span class="sxs-lookup"><span data-stu-id="fb1ad-113">Script Methods</span></span>

<span data-ttu-id="fb1ad-114">Метод скрипт определяет метод, значение которого является результатом выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-114">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="fb1ad-115">В следующем примере **ConvertToDateTime** добавляется метод [System.Management.Managementobject? Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject) типа.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-115">In the following example, the **ConvertToDateTime** method is added to the [System.Management.Managementobject?Displayproperty=Fullname](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="fb1ad-116">[ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) элемент определяет расширенный метод как метод скрипта.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-116">The [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) element defines the extended method as a script method.</span></span> <span data-ttu-id="fb1ad-117">[Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного метода.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-117">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended method.</span></span> <span data-ttu-id="fb1ad-118">И [скрипт](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f) элемент указывает сценарий, который создает значение метода.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-118">And, the [Script](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f) element specifies the script that generates the method value.</span></span> <span data-ttu-id="fb1ad-119">(Можно также добавить [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)</span><span class="sxs-lookup"><span data-stu-id="fb1ad-119">(You can also add the [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="fb1ad-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fb1ad-120">See Also</span></span>

[<span data-ttu-id="fb1ad-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb1ad-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)