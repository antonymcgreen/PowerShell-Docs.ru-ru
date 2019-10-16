---
title: Расширение свойств объектов | Документация Майкрософт
ms.custom: ''
ms.date: 08/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: 3b14007384cca0d0cfa35655aee437adf73b1ff0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364453"
---
# <a name="extending-properties-for-objects"></a><span data-ttu-id="b0526-102">Расширение свойств для объектов</span><span class="sxs-lookup"><span data-stu-id="b0526-102">Extending Properties for Objects</span></span>

<span data-ttu-id="b0526-103">При расширении .NET Framework объектов можно добавить свойства псевдонима, свойства кода, свойства примечаний, свойства скрипта и наборы свойств в объекты.</span><span class="sxs-lookup"><span data-stu-id="b0526-103">When you extend .NET Framework objects, you can add alias properties, code properties, note properties, script properties, and property sets to the objects.</span></span> <span data-ttu-id="b0526-104">XML-код, определяющий эти свойства, описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b0526-104">The XML that defines these properties is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="b0526-105">Примеры в следующих разделах относятся к файлу `Types.ps1xml` типов по умолчанию в каталоге установки PowerShell (`$PSHOME`).</span><span class="sxs-lookup"><span data-stu-id="b0526-105">The examples in the following sections are from the default `Types.ps1xml` types file in the PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="b0526-106">Дополнительные сведения см. в разделе [About types. ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="b0526-106">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="alias-properties"></a><span data-ttu-id="b0526-107">Свойства псевдонима</span><span class="sxs-lookup"><span data-stu-id="b0526-107">Alias properties</span></span>

<span data-ttu-id="b0526-108">Свойство Alias определяет новое имя для существующего свойства.</span><span class="sxs-lookup"><span data-stu-id="b0526-108">An alias property defines a new name for an existing property.</span></span>

<span data-ttu-id="b0526-109">В следующем примере свойство **Count** добавляется к типу [System. Array](/dotnet/api/System.Array) .</span><span class="sxs-lookup"><span data-stu-id="b0526-109">In the following example, the **Count** property is added to the [System.Array](/dotnet/api/System.Array) type.</span></span> <span data-ttu-id="b0526-110">Элемент [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) определяет расширенное свойство как свойство Alias.</span><span class="sxs-lookup"><span data-stu-id="b0526-110">The [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) element defines the extended property as an alias property.</span></span> <span data-ttu-id="b0526-111">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает новое имя.</span><span class="sxs-lookup"><span data-stu-id="b0526-111">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the new name.</span></span> <span data-ttu-id="b0526-112">И элемент [референцедмембернаме](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) указывает на существующее свойство, на которое ссылается псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b0526-112">And, the [ReferencedMemberName](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) element specifies the existing property that is referenced by the alias.</span></span> <span data-ttu-id="b0526-113">Можно также добавить элемент `AliasProperty` в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="b0526-113">You can also add the `AliasProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="code-properties"></a><span data-ttu-id="b0526-114">Свойства кода</span><span class="sxs-lookup"><span data-stu-id="b0526-114">Code properties</span></span>

<span data-ttu-id="b0526-115">Свойство Code ссылается на статическое свойство объекта .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0526-115">A code property references a static property of a .NET Framework object.</span></span>

<span data-ttu-id="b0526-116">В следующем примере свойство **mode** добавляется к типу [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) .</span><span class="sxs-lookup"><span data-stu-id="b0526-116">In the following example, the **Mode** property is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="b0526-117">Элемент [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) определяет расширенное свойство как свойство Code.</span><span class="sxs-lookup"><span data-stu-id="b0526-117">The [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) element defines the extended property as a code property.</span></span> <span data-ttu-id="b0526-118">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="b0526-118">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="b0526-119">И элемент [жеткодереференце](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) определяет статический метод, на который ссылается расширенное свойство.</span><span class="sxs-lookup"><span data-stu-id="b0526-119">And, the [GetCodeReference](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) element defines the static method that is referenced by the extended property.</span></span> <span data-ttu-id="b0526-120">Можно также добавить элемент `CodeProperty` в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="b0526-120">You can also add the `CodeProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="note-properties"></a><span data-ttu-id="b0526-121">Свойства заметки</span><span class="sxs-lookup"><span data-stu-id="b0526-121">Note properties</span></span>

<span data-ttu-id="b0526-122">Свойство Note определяет свойство, имеющее статическое значение.</span><span class="sxs-lookup"><span data-stu-id="b0526-122">A note property defines a property that has a static value.</span></span>

<span data-ttu-id="b0526-123">В следующем примере свойство **Status** , значение которого всегда равно **Success**, добавляется в тип [System. IO. DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) .</span><span class="sxs-lookup"><span data-stu-id="b0526-123">In the following example, the **Status** property, whose value is always **Success**, is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="b0526-124">Элемент [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) определяет расширенное свойство как свойство Note.</span><span class="sxs-lookup"><span data-stu-id="b0526-124">The [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) element defines the extended property as a note property.</span></span> <span data-ttu-id="b0526-125">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="b0526-125">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="b0526-126">Элемент [value](/dotnet/api/system.management.automation.psnoteproperty.value) указывает статическое значение расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="b0526-126">The [Value](/dotnet/api/system.management.automation.psnoteproperty.value) element specifies the static value of the extended property.</span></span> <span data-ttu-id="b0526-127">Элемент `NoteProperty` также можно добавить в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="b0526-127">The `NoteProperty` element can also be added to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="script-properties"></a><span data-ttu-id="b0526-128">Свойства скрипта</span><span class="sxs-lookup"><span data-stu-id="b0526-128">Script properties</span></span>

<span data-ttu-id="b0526-129">Свойство скрипта определяет свойство, значение которого является выходным значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0526-129">A script property defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="b0526-130">В следующем примере свойство **versionInfo** добавляется в тип [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) .</span><span class="sxs-lookup"><span data-stu-id="b0526-130">In the following example, the **VersionInfo** property is added to the [System.IO.FileInfo](/dotnet/api/System.IO.FileInfo) type.</span></span> <span data-ttu-id="b0526-131">Элемент [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) определяет расширенное свойство как свойство скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0526-131">The [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) element defines the extended property as a script property.</span></span> <span data-ttu-id="b0526-132">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="b0526-132">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="b0526-133">И элемент [жетскриптблокк](/dotnet/api/system.management.automation.psscriptproperty.getterscript) указывает скрипт, который создает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="b0526-133">And, the [GetScriptBlock](/dotnet/api/system.management.automation.psscriptproperty.getterscript) element specifies the script that generates the property value.</span></span> <span data-ttu-id="b0526-134">Можно также добавить элемент `ScriptProperty` в элементы элемента [мемберсетс](/dotnet/api/system.management.automation.psmemberset) .</span><span class="sxs-lookup"><span data-stu-id="b0526-134">You can also add the `ScriptProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="property-sets"></a><span data-ttu-id="b0526-135">Наборы свойств</span><span class="sxs-lookup"><span data-stu-id="b0526-135">Property sets</span></span>

<span data-ttu-id="b0526-136">Набор свойств определяет группу расширенных свойств, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="b0526-136">A property set defines a group of extended properties that can be referenced by the name of the set.</span></span>
<span data-ttu-id="b0526-137">Например, параметр свойства [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)
 может указывать конкретный набор свойств для отображения.</span><span class="sxs-lookup"><span data-stu-id="b0526-137">For example, the [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)
**Property** parameter can specify a specific property set to be displayed.</span></span> <span data-ttu-id="b0526-138">Если задан набор свойств, отображаются только те свойства, которые принадлежат набору.</span><span class="sxs-lookup"><span data-stu-id="b0526-138">When a property set is specified, only those properties that belong to the set are displayed.</span></span>

<span data-ttu-id="b0526-139">Количество наборов свойств, которые могут быть определены для объекта, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="b0526-139">There's no restriction on the number of property sets that can be defined for an object.</span></span> <span data-ttu-id="b0526-140">Однако наборы свойств, используемые для определения свойств экрана по умолчанию для объекта, должны быть указаны в наборе элементов **псстандардмемберс** .</span><span class="sxs-lookup"><span data-stu-id="b0526-140">However, the property sets used to define the default display properties of an object must be specified within the **PSStandardMembers** member set.</span></span> <span data-ttu-id="b0526-141">В файле типа `Types.ps1xml` имена наборов свойств по умолчанию включают **дефаултдисплайпроперти**, **дефаултдисплайпропертисет**и **дефаулткэйпропертисет**.</span><span class="sxs-lookup"><span data-stu-id="b0526-141">In the `Types.ps1xml` types file, the default property set names include **DefaultDisplayProperty**, **DefaultDisplayPropertySet**, and **DefaultKeyPropertySet**.</span></span> <span data-ttu-id="b0526-142">Все дополнительные наборы свойств, добавляемые в набор элементов **псстандардмемберс** , игнорируются.</span><span class="sxs-lookup"><span data-stu-id="b0526-142">Any additional property sets that you add to the **PSStandardMembers** member set are ignored.</span></span>

<span data-ttu-id="b0526-143">В следующем примере набор свойств **дефаултдисплайпропертисет** добавляется в набор элементов **псстандардмемберс** типа [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="b0526-143">In the following example, the **DefaultDisplayPropertySet** property set is added to the **PSStandardMembers** member set of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) type.</span></span> <span data-ttu-id="b0526-144">Элемент набора [свойств](/dotnet/api/system.management.automation.pspropertyset) определяет группу свойств.</span><span class="sxs-lookup"><span data-stu-id="b0526-144">The [PropertySet](/dotnet/api/system.management.automation.pspropertyset) element defines the group of properties.</span></span> <span data-ttu-id="b0526-145">Элемент [Name](/dotnet/api/system.management.automation.psmemberinfo.name) указывает имя набора свойств.</span><span class="sxs-lookup"><span data-stu-id="b0526-145">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the property set.</span></span> <span data-ttu-id="b0526-146">И элемент [референцедпропертиес](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) указывает свойства набора.</span><span class="sxs-lookup"><span data-stu-id="b0526-146">And, the [ReferencedProperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) element specifies the properties of the set.</span></span> <span data-ttu-id="b0526-147">Можно также добавить элемент `PropertySet` в элементы элемента [Type](/dotnet/api/system.management.automation.pstypename) .</span><span class="sxs-lookup"><span data-stu-id="b0526-147">You can also add the `PropertySet` element to the members of the [Type](/dotnet/api/system.management.automation.pstypename) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b0526-148">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b0526-148">See also</span></span>

[<span data-ttu-id="b0526-149">О типах. ps1xml</span><span class="sxs-lookup"><span data-stu-id="b0526-149">About Types.ps1xml</span></span>](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[<span data-ttu-id="b0526-150">System. Management. Automation</span><span class="sxs-lookup"><span data-stu-id="b0526-150">System.Management.Automation</span></span>](/dotnet/api/System.Management.Automation)

[<span data-ttu-id="b0526-151">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0526-151">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
