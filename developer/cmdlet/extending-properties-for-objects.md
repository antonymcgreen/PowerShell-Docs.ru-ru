---
title: Расширение свойств для объектов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: 496e363b041194563d46c09eee67a12055bb54b0
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057303"
---
# <a name="extending-properties-for-objects"></a><span data-ttu-id="eb2e6-102">Расширение свойств для объектов</span><span class="sxs-lookup"><span data-stu-id="eb2e6-102">Extending Properties for Objects</span></span>

<span data-ttu-id="eb2e6-103">При расширении объекты .NET Framework, можно добавить псевдоним свойства, свойства кода, свойства примечаний, свойства сценария и наборов свойств к объектам.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-103">When you extend .NET Framework objects, you can add alias properties, code properties, note properties, script properties, and property sets to the objects.</span></span> <span data-ttu-id="eb2e6-104">В следующих разделах описывается XML, который используется для определения этих свойств.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-104">The XML that is used to define these properties is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="eb2e6-105">В следующих разделах относятся, например из файла Types.ps1xml типы по умолчанию в каталоге установки Windows PowerShell (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="eb2e6-105">The examples in the following sections are from the default Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="alias-properties"></a><span data-ttu-id="eb2e6-106">Свойства псевдонима</span><span class="sxs-lookup"><span data-stu-id="eb2e6-106">Alias Properties</span></span>

<span data-ttu-id="eb2e6-107">Свойства псевдонима определяет новое имя для существующего свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-107">An alias property defines a new name for an existing property.</span></span>

<span data-ttu-id="eb2e6-108">В следующем примере `Count` свойство добавляется к [System.Array? Displayproperty = Fullname](/dotnet/api/System.Array) типа.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-108">In the following example, the `Count` property is added to the [System.Array?Displayproperty=Fullname](/dotnet/api/System.Array) type.</span></span> <span data-ttu-id="eb2e6-109">[AliasProperty](http://msdn.microsoft.com/en-us/b140038c-807a-4bb9-beca-332491cda1b1) элемент определяет расширенное свойство как свойство псевдонима.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-109">The [AliasProperty](http://msdn.microsoft.com/en-us/b140038c-807a-4bb9-beca-332491cda1b1) element defines the extended property as an alias property.</span></span> <span data-ttu-id="eb2e6-110">[Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент указывает новое имя.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-110">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the new name.</span></span> <span data-ttu-id="eb2e6-111">И [ReferencedMemberName](http://msdn.microsoft.com/en-us/0c5db6cc-9033-4d48-88a7-76b962882f7a) элемент задает существующее свойство, на который ссылается псевдоним.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-111">And, the [ReferencedMemberName](http://msdn.microsoft.com/en-us/0c5db6cc-9033-4d48-88a7-76b962882f7a) element specifies the existing property that is referenced by the alias.</span></span> <span data-ttu-id="eb2e6-112">(Можно также добавить [AliasProperty](http://msdn.microsoft.com/en-us/d6647953-94ad-4b0b-af2e-4dda6952dee1) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)</span><span class="sxs-lookup"><span data-stu-id="eb2e6-112">(You can also add the [AliasProperty](http://msdn.microsoft.com/en-us/d6647953-94ad-4b0b-af2e-4dda6952dee1) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

## <a name="code-properties"></a><span data-ttu-id="eb2e6-113">Свойства кода</span><span class="sxs-lookup"><span data-stu-id="eb2e6-113">Code Properties</span></span>

<span data-ttu-id="eb2e6-114">Свойство код ссылается на статическое свойство объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-114">A code property references a static property of a .NET Framework object.</span></span>

<span data-ttu-id="eb2e6-115">В следующем примере `Node` свойство добавляется к [System.IO.Directoryinfo? Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo) типа.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-115">In the following example, the `Node` property is added to the [System.IO.Directoryinfo?Displayproperty=Fullname](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="eb2e6-116">[CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) элемент определяет расширенное свойство как свойство кода.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-116">The [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) element defines the extended property as a code property.</span></span> <span data-ttu-id="eb2e6-117">[Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-117">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended property.</span></span> <span data-ttu-id="eb2e6-118">И [GetCodeReference](http://msdn.microsoft.com/en-us/62af34f5-cc22-42c0-9e0c-3bd0f5c1a4a0) элемент определяет статический метод, который ссылается расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-118">And, the [GetCodeReference](http://msdn.microsoft.com/en-us/62af34f5-cc22-42c0-9e0c-3bd0f5c1a4a0) element defines the static method that is referenced by the extended property.</span></span> <span data-ttu-id="eb2e6-119">(Можно также добавить [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)</span><span class="sxs-lookup"><span data-stu-id="eb2e6-119">(You can also add the [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>Microsoft.PowerShell.Commands.FileSystemProvider</TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

## <a name="note-properties"></a><span data-ttu-id="eb2e6-120">Свойства примечаний</span><span class="sxs-lookup"><span data-stu-id="eb2e6-120">Note Properties</span></span>

<span data-ttu-id="eb2e6-121">Свойство примечания определяет свойство, которое имеет статическое значение.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-121">A note property defines a property that has a static value.</span></span>

<span data-ttu-id="eb2e6-122">В следующем примере `Status` свойства (значение которого всегда является «Успех») добавляется к [System.IO.Directoryinfo? Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo) типа.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-122">In the following example, the `Status` property (whose value is always "Success") is added to the [System.IO.Directoryinfo?Displayproperty=Fullname](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="eb2e6-123">[NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) элемент определяет расширенное свойство как свойство примечания; [имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного свойства; и [значение](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) элемент Задает статическое значение расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-123">The [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) element defines the extended property as a note property; the [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended property; and the [Value](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) element specifies the static value of the extended property.</span></span> <span data-ttu-id="eb2e6-124">( [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) также можно добавить элемент к членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)</span><span class="sxs-lookup"><span data-stu-id="eb2e6-124">(The [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) element can also be added to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

## <a name="script-properties"></a><span data-ttu-id="eb2e6-125">Свойства сценария</span><span class="sxs-lookup"><span data-stu-id="eb2e6-125">Script Properties</span></span>

<span data-ttu-id="eb2e6-126">Свойство скрипт определяет свойство, значение которого является результатом выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-126">A script property defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="eb2e6-127">В следующем примере `VersionInfo` свойство добавляется к [System.IO.FileInfo? Displayproperty = Fullname](/dotnet/api/System.IO.FileInfo) типа.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-127">In the following example, the `VersionInfo` property is added to the [System.IO.FileInfo?Displayproperty=Fullname](/dotnet/api/System.IO.FileInfo) type.</span></span> <span data-ttu-id="eb2e6-128">[ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) элемент определяет расширенное свойство как свойство скрипта.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-128">The [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) element defines the extended property as a script property.</span></span> <span data-ttu-id="eb2e6-129">[Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-129">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended property.</span></span> <span data-ttu-id="eb2e6-130">И [GetScriptBlock](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) элемент указывает сценарий, который создает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-130">And, the [GetScriptBlock](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) element specifies the script that generates the property value.</span></span> <span data-ttu-id="eb2e6-131">(Можно также добавить [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) элемент членам [наборов элементов](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) элемент.)</span><span class="sxs-lookup"><span data-stu-id="eb2e6-131">(You can also add the [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
        [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

## <a name="property-sets"></a><span data-ttu-id="eb2e6-132">Наборы свойств</span><span class="sxs-lookup"><span data-stu-id="eb2e6-132">Property Sets</span></span>

<span data-ttu-id="eb2e6-133">Набор свойств определяется группа расширенные свойства, которые можно ссылаться по имени набора.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-133">A property set defines a group of extended properties that can be referenced by the name of the set.</span></span> <span data-ttu-id="eb2e6-134">Например `Property` параметр [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) командлета можно указать значение для отображения конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-134">For example, the `Property` parameter of the [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) cmdlet can specify a specific property set to be displayed.</span></span> <span data-ttu-id="eb2e6-135">Если указан набор свойств, отображаются только те свойства, которые принадлежат к набору.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-135">When a property set is specified, only those properties that belong to the set are displayed.</span></span>

<span data-ttu-id="eb2e6-136">Нет никаких ограничений на количество наборов свойств, которые могут быть определены для объекта.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-136">There is no restriction on the number of property sets that can be defined for an object.</span></span> <span data-ttu-id="eb2e6-137">Тем не менее наборов свойств, используемый для определения свойств отображения по умолчанию объекта должно быть указано в наборе элементов PSStandardMembers.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-137">However, the property sets used to define the default display properties of an object must be specified within the PSStandardMembers member set.</span></span> <span data-ttu-id="eb2e6-138">В файле Types.ps1xml типы имена набора свойств по умолчанию включают DefaultDisplayProperty DefaultDisplayPropertySet и DefaultKeyPropertySet.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-138">In the Types.ps1xml types file, the default property set names include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="eb2e6-139">Все наборы дополнительные свойства, добавленные в набор элементов PSStandardMembers игнорируются.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-139">Any additional property sets that you add to the PSStandardMembers member set are ignored.</span></span>

<span data-ttu-id="eb2e6-140">В следующем примере добавляется набор свойств DefaultDisplayPropertySet набором элементов PSStandardMembers [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) типа.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-140">In the following example, the DefaultDisplayPropertySet property set is added to the PSStandardMembers member set of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) type.</span></span> <span data-ttu-id="eb2e6-141">[PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) элемент определяет группу свойств.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-141">The [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) element defines the group of properties.</span></span> <span data-ttu-id="eb2e6-142">[Имя](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) элемент задает имя набора свойств.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-142">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the property set.</span></span> <span data-ttu-id="eb2e6-143">И [ReferencedProperties](http://msdn.microsoft.com/en-us/5e620423-8679-4fbf-b6db-9f79288e4786) элемент определяет свойства набора.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-143">And, the [ReferencedProperties](http://msdn.microsoft.com/en-us/5e620423-8679-4fbf-b6db-9f79288e4786) element specifies the properties of the set.</span></span> <span data-ttu-id="eb2e6-144">(Можно также добавить [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) элемент членам [тип](http://msdn.microsoft.com/en-us/e5dbd353-d6b2-40a1-92b6-6f1fea744ebe) элемент.)</span><span class="sxs-lookup"><span data-stu-id="eb2e6-144">(You can also add the [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) element to the members of the [Type](http://msdn.microsoft.com/en-us/e5dbd353-d6b2-40a1-92b6-6f1fea744ebe) element.)</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
           <Name>DefaultDisplayPropertySet</Name>
           <ReferencedProperties>
            <Name>Status</Name
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="eb2e6-145">См. также</span><span class="sxs-lookup"><span data-stu-id="eb2e6-145">See Also</span></span>

[<span data-ttu-id="eb2e6-146">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb2e6-146">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
