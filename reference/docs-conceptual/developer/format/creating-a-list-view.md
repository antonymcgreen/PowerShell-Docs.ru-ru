---
title: Создание представления списка | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c7a40ca-1786-46f0-bab5-6ce229daa7ee
caps.latest.revision: 14
ms.openlocfilehash: 25d24063501196d44e0f806a55bb699c82f771ce
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368983"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="9718c-102">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="9718c-102">Creating a List View</span></span>

<span data-ttu-id="9718c-103">Представление списка отображает данные в одном столбце (в последовательном порядке).</span><span class="sxs-lookup"><span data-stu-id="9718c-103">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="9718c-104">Данные, отображаемые в списке, могут быть значением свойства .NET или значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="9718c-104">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="9718c-105">Отображение представления списка</span><span class="sxs-lookup"><span data-stu-id="9718c-105">A List View Display</span></span>

<span data-ttu-id="9718c-106">В следующих выходных данных показано, как Windows PowerShell отображает свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые командлетом [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="9718c-106">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="9718c-107">В этом примере были возвращены три объекта, каждый из которых отделяется от предыдущего объекта на пустую строку.</span><span class="sxs-lookup"><span data-stu-id="9718c-107">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

```powershell
Get-Service | format-list
```

```output
Name                : AEADIFilters
DisplayName         : Andrea ADI Filters Service
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess

Name                : AeLookupSvc
DisplayName         : Application Experience
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32ShareProcess

Name                : AgereModemAudio
DisplayName         : Agere Modem Call Progress Audio
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : True
ServiceType         : Win32OwnProcess
...
```

## <a name="defining-the-list-view"></a><span data-ttu-id="9718c-108">Определение представления списка</span><span class="sxs-lookup"><span data-stu-id="9718c-108">Defining the List View</span></span>

<span data-ttu-id="9718c-109">В следующем коде XML показана схема представления списка для отображения нескольких свойств [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , объект.</span><span class="sxs-lookup"><span data-stu-id="9718c-109">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="9718c-110">Необходимо указать каждое свойство, которое должно отображаться в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-110">You must specify each property that you want displayed in the list view.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

<span data-ttu-id="9718c-111">Для определения представления списка используются следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="9718c-111">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="9718c-112">Элемент [View](./view-element-format.md) является родительским элементом представления списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-112">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="9718c-113">(Это тот же родительский элемент для представлений таблицы, широкие и настраиваемых элементов управления.)</span><span class="sxs-lookup"><span data-stu-id="9718c-113">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="9718c-114">Элемент [Name](./name-element-for-view-format.md) указывает имя представления.</span><span class="sxs-lookup"><span data-stu-id="9718c-114">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="9718c-115">Этот элемент является обязательным для всех представлений.</span><span class="sxs-lookup"><span data-stu-id="9718c-115">This element is required for all views.</span></span>

- <span data-ttu-id="9718c-116">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет объекты, которые используют представление.</span><span class="sxs-lookup"><span data-stu-id="9718c-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="9718c-117">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-117">This element is required.</span></span>

- <span data-ttu-id="9718c-118">Элемент [GroupBy](./groupby-element-for-view-format.md) определяет, когда отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="9718c-118">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="9718c-119">Новая группа запускается каждый раз при изменении значения определенного свойства или сценария.</span><span class="sxs-lookup"><span data-stu-id="9718c-119">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="9718c-120">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-120">This element is optional.</span></span>

- <span data-ttu-id="9718c-121">Элемент [Controls](./controls-element-for-view-format.md) определяет пользовательские элементы управления, определяемые представлением списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-121">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="9718c-122">Элементы управления позволяют дополнительно указать способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="9718c-122">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="9718c-123">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-123">This element is optional.</span></span> <span data-ttu-id="9718c-124">Представление может определять собственные пользовательские элементы управления или использовать стандартные элементы управления, которые могут использоваться любыми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="9718c-124">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="9718c-125">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-125">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="9718c-126">Элемент [ListControl](./listcontrol-element-format.md) определяет, что отображается в представлении и как оно форматируется.</span><span class="sxs-lookup"><span data-stu-id="9718c-126">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="9718c-127">Как и во всех других представлениях, представление списка может отображать значения свойств объектов или значений, создаваемых скриптом.</span><span class="sxs-lookup"><span data-stu-id="9718c-127">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="9718c-128">Пример полного файла форматирования, определяющего простое представление списка, см. в разделе [представление списка (базовый)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-128">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="9718c-129">Предоставление определений для представления списка</span><span class="sxs-lookup"><span data-stu-id="9718c-129">Providing Definitions for Your List View</span></span>

<span data-ttu-id="9718c-130">Представления списка могут предоставлять одно или несколько определений с помощью дочерних элементов элемента [ListControl](./listcontrol-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="9718c-130">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="9718c-131">Как правило, представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="9718c-131">Typically, a view will have only one definition.</span></span> <span data-ttu-id="9718c-132">В следующем примере представление предоставляет одно определение, в котором отображаются несколько свойств [System. Diagnostics. Process? DisplayProperty = FullName](/dotnet/api/System.Diagnostics.Process) , объект.</span><span class="sxs-lookup"><span data-stu-id="9718c-132">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="9718c-133">В представлении списка может отображаться значение свойства или значение скрипта (не показано в примере).</span><span class="sxs-lookup"><span data-stu-id="9718c-133">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>

```

<span data-ttu-id="9718c-134">Следующие XML-элементы можно использовать для предоставления определений для представления списка:</span><span class="sxs-lookup"><span data-stu-id="9718c-134">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="9718c-135">Элемент [ListControl](./listcontrol-element-format.md) и его дочерние элементы определяют, что отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="9718c-135">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="9718c-136">Элемент [листентриес](./listentries-element-for-listcontrol-format.md) предоставляет определения представления.</span><span class="sxs-lookup"><span data-stu-id="9718c-136">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="9718c-137">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="9718c-137">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="9718c-138">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-138">This element is required.</span></span>

- <span data-ttu-id="9718c-139">Элемент [листентри](./listentry-element-for-listcontrol-format.md) предоставляет определение представления.</span><span class="sxs-lookup"><span data-stu-id="9718c-139">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="9718c-140">Требуется по крайней мере один [листентри](./listentry-element-for-listcontrol-format.md) ; Однако максимальное количество элементов, которые можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="9718c-140">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="9718c-141">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="9718c-141">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="9718c-142">Элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) указывает объекты, отображаемые конкретным определением.</span><span class="sxs-lookup"><span data-stu-id="9718c-142">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="9718c-143">Этот элемент является необязательным и необходим только при определении нескольких элементов [листентри](./listentry-element-for-listcontrol-format.md) , отображающих разные объекты.</span><span class="sxs-lookup"><span data-stu-id="9718c-143">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="9718c-144">Элемент [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) указывает свойства и скрипты, значения которых отображаются в строках представления списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-144">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="9718c-145">Элемент [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) указывает свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-145">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="9718c-146">В представлении списка должно быть указано по крайней мере одно свойство или скрипт.</span><span class="sxs-lookup"><span data-stu-id="9718c-146">A list view must specify at least one property or script.</span></span> <span data-ttu-id="9718c-147">Максимальное число строк, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="9718c-147">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="9718c-148">Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) указывает свойство, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="9718c-148">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="9718c-149">Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-149">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="9718c-150">Элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="9718c-150">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="9718c-151">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-151">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="9718c-152">Элемент [Label](./label-element-for-listitem-for-listcontrol-format.md) Указывает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="9718c-152">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="9718c-153">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-153">This element is optional.</span></span> <span data-ttu-id="9718c-154">Если метка не указана, отображается имя свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="9718c-154">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="9718c-155">Полный пример см. в разделе [представление списка (метки)](./list-view-labels.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-155">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="9718c-156">Элемент [итемселектионкондитион](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) указывает условие, которое должно существовать для отображения строки.</span><span class="sxs-lookup"><span data-stu-id="9718c-156">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="9718c-157">Дополнительные сведения о добавлении условий в представление списка см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-157">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="9718c-158">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-158">This element is optional.</span></span>

- <span data-ttu-id="9718c-159">Элемент [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) задает шаблон, используемый для вывода значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="9718c-159">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="9718c-160">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-160">This element is optional.</span></span>

<span data-ttu-id="9718c-161">Пример полного файла форматирования, определяющего простое представление списка, см. в разделе [представление списка (базовый)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-161">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="9718c-162">Определение объектов, использующих представление списка</span><span class="sxs-lookup"><span data-stu-id="9718c-162">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="9718c-163">Существует два способа определения объектов .NET, использующих представление списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-163">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="9718c-164">Элемент [виевселектедби](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться всеми определениями представления, или можно использовать элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) для определения объектов, отображаемых определенным определением представления.</span><span class="sxs-lookup"><span data-stu-id="9718c-164">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="9718c-165">В большинстве случаев представление имеет только одно определение, поэтому объекты обычно определяются элементом [виевселектедби](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="9718c-165">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="9718c-166">В следующем примере показано, как определить объекты, отображаемые представлением списка с помощью элементов [виевселектедби](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="9718c-166">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="9718c-167">Количество элементов [TypeName](./typename-element-for-viewselectedby-format.md) , которые можно указать, не ограничено, и их порядок не важен.</span><span class="sxs-lookup"><span data-stu-id="9718c-167">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="9718c-168">Для указания объектов, используемых представлением списка, можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="9718c-168">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="9718c-169">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-169">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="9718c-170">Элемент [TypeName](./typename-element-for-viewselectedby-format.md) задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="9718c-170">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="9718c-171">Требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="9718c-171">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="9718c-172">Необходимо указать по крайней мере один тип или набор элементов для представления, но максимальное количество заданных объектов не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="9718c-172">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="9718c-173">Пример полного файла форматирования см. в разделе [представление списка (базовый)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-173">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="9718c-174">В следующем примере используются элементы [виевселектедби](./viewselectedby-element-format.md) и [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="9718c-174">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="9718c-175">Используйте наборы выбора, в которых имеется связанный набор объектов, отображаемых с помощью нескольких представлений, например при определении представления списка и табличного представления для тех же объектов.</span><span class="sxs-lookup"><span data-stu-id="9718c-175">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="9718c-176">Дополнительные сведения о создании набора выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-176">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="9718c-177">Для указания объектов, используемых представлением списка, можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="9718c-177">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="9718c-178">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="9718c-178">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="9718c-179">Элемент [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) указывает набор объектов, которые могут быть отображены представлением.</span><span class="sxs-lookup"><span data-stu-id="9718c-179">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="9718c-180">Необходимо указать хотя бы один набор выбора или тип для представления, но максимальное количество элементов, которое можно указать, не существует.</span><span class="sxs-lookup"><span data-stu-id="9718c-180">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="9718c-181">В следующем примере показано, как определить объекты, отображаемые определенным определением представления списка с помощью элемента [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="9718c-181">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="9718c-182">С помощью этого элемента можно указать имя типа .NET объекта, набор элементов выбора объектов или условие выбора, которое указывает, когда используется определение.</span><span class="sxs-lookup"><span data-stu-id="9718c-182">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="9718c-183">Дополнительные сведения о создании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-183">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="9718c-184">Следующие XML-элементы можно использовать для указания объектов, которые используются в определенном определении представления списка:</span><span class="sxs-lookup"><span data-stu-id="9718c-184">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="9718c-185">Элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) определяет, какие объекты отображаются в определении.</span><span class="sxs-lookup"><span data-stu-id="9718c-185">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="9718c-186">Элемент [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) указывает объект .NET, который отображается в определении.</span><span class="sxs-lookup"><span data-stu-id="9718c-186">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="9718c-187">При использовании этого элемента требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="9718c-187">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="9718c-188">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="9718c-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="9718c-189">Элемент [селектионсетнаме](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показан) задает набор объектов, которые могут отображаться в этом определении.</span><span class="sxs-lookup"><span data-stu-id="9718c-189">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="9718c-190">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="9718c-190">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="9718c-191">Элемент [селектионкондитион](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="9718c-191">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="9718c-192">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="9718c-192">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="9718c-193">Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-193">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="9718c-194">Отображение групп объектов в представлении списка</span><span class="sxs-lookup"><span data-stu-id="9718c-194">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="9718c-195">Можно разделить объекты, отображаемые представлением списка, на группы.</span><span class="sxs-lookup"><span data-stu-id="9718c-195">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="9718c-196">Это не означает, что вы определяете группу, а только то, что Windows PowerShell запускает новую группу всякий раз, когда изменяется значение определенного свойства или сценария.</span><span class="sxs-lookup"><span data-stu-id="9718c-196">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="9718c-197">В следующем примере новая группа запускается всякий раз, когда изменяется свойство [System. ServiceProcess. ServiceController. serviceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) .</span><span class="sxs-lookup"><span data-stu-id="9718c-197">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="9718c-198">Следующие XML-элементы используются для определения времени запуска группы:</span><span class="sxs-lookup"><span data-stu-id="9718c-198">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="9718c-199">Элемент [GroupBy](./groupby-element-for-view-format.md) определяет свойство или скрипт, который запускает новую группу и определяет, как будет отображаться группа.</span><span class="sxs-lookup"><span data-stu-id="9718c-199">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="9718c-200">Элемент [PropertyName](./propertyname-element-for-groupby-format.md) указывает свойство, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="9718c-200">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="9718c-201">Необходимо указать свойство или скрипт для запуска группы, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-201">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="9718c-202">Элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) указывает скрипт, который запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="9718c-202">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="9718c-203">Необходимо указать скрипт или свойство для запуска группы, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-203">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="9718c-204">Элемент [Label](./label-element-for-groupby-format.md) определяет метку, которая отображается в начале каждой группы.</span><span class="sxs-lookup"><span data-stu-id="9718c-204">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="9718c-205">В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает значение, вызвавшее новую группу, и добавляет пустую строку до и после метки.</span><span class="sxs-lookup"><span data-stu-id="9718c-205">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="9718c-206">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-206">This element is optional.</span></span>

- <span data-ttu-id="9718c-207">Элемент [Ошибка customcontrol](./customcontrol-element-for-groupby-format.md) определяет элемент управления, используемый для вывода данных.</span><span class="sxs-lookup"><span data-stu-id="9718c-207">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="9718c-208">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-208">This element is optional.</span></span>

- <span data-ttu-id="9718c-209">Элемент [кустомконтролнаме](./customcontrolname-element-for-groupby-format.md) указывает общий элемент управления или представление, которое используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="9718c-209">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="9718c-210">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9718c-210">This element is optional.</span></span>

<span data-ttu-id="9718c-211">Пример полного файла форматирования, определяющего группы, см. в разделе [представление списка (GroupBy)](./list-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="9718c-211">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="9718c-212">Использование строк формата</span><span class="sxs-lookup"><span data-stu-id="9718c-212">Using Format Strings</span></span>

<span data-ttu-id="9718c-213">Строки форматирования можно добавить в представление, чтобы дополнительно определить способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="9718c-213">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="9718c-214">В следующем примере показано, как определить строку форматирования для значения свойства `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="9718c-214">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="9718c-215">Для указания шаблона формата можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="9718c-215">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="9718c-216">Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) указывает данные, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="9718c-216">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="9718c-217">Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) указывает свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="9718c-217">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="9718c-218">Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-218">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="9718c-219">Элемент [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="9718c-219">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="9718c-220">Элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (не показан) задает скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="9718c-220">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="9718c-221">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-221">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="9718c-222">В следующем примере вызывается метод `ToString` для форматирования значения скрипта.</span><span class="sxs-lookup"><span data-stu-id="9718c-222">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="9718c-223">Скрипты могут вызывать любой метод объекта.</span><span class="sxs-lookup"><span data-stu-id="9718c-223">Scripts can call any method of an object.</span></span> <span data-ttu-id="9718c-224">Таким образом, если у объекта есть метод, например `ToString`, имеющий параметры форматирования, скрипт может вызвать этот метод для форматирования выходного значения скрипта.</span><span class="sxs-lookup"><span data-stu-id="9718c-224">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="9718c-225">Следующий XML-элемент можно использовать для вызова метода `ToString`:</span><span class="sxs-lookup"><span data-stu-id="9718c-225">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="9718c-226">Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) указывает данные, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="9718c-226">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="9718c-227">Элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) (не показан) задает скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="9718c-227">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="9718c-228">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9718c-228">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="9718c-229">См. также:</span><span class="sxs-lookup"><span data-stu-id="9718c-229">See Also</span></span>

[<span data-ttu-id="9718c-230">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9718c-230">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)
