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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861580"
---
# <a name="creating-a-list-view"></a><span data-ttu-id="cd73b-102">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="cd73b-102">Creating a List View</span></span>

<span data-ttu-id="cd73b-103">Представление списка отображает данные в виде одного столбца (в последовательном порядке).</span><span class="sxs-lookup"><span data-stu-id="cd73b-103">A list view displays data in a single column (in sequential order).</span></span> <span data-ttu-id="cd73b-104">Данные, отображаемые в списке может быть значение свойства .NET или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-104">The data displayed in the list can be the value of a .NET property or the value of a script.</span></span>

## <a name="a-list-view-display"></a><span data-ttu-id="cd73b-105">Отображения представления списка</span><span class="sxs-lookup"><span data-stu-id="cd73b-105">A List View Display</span></span>

<span data-ttu-id="cd73b-106">Ниже показано, как Windows PowerShell отображает свойства [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета.</span><span class="sxs-lookup"><span data-stu-id="cd73b-106">The following output shows how Windows PowerShell displays the properties of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects that are returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="cd73b-107">В этом примере были возвращены три объекта, с каждым объектом, который отделен от предыдущего объекта с пустыми строками.</span><span class="sxs-lookup"><span data-stu-id="cd73b-107">In this example, three objects were returned, with each object separated from the preceding object by a blank line.</span></span>

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

## <a name="defining-the-list-view"></a><span data-ttu-id="cd73b-108">Определение представления списка</span><span class="sxs-lookup"><span data-stu-id="cd73b-108">Defining the List View</span></span>

<span data-ttu-id="cd73b-109">Следующий код XML показывает схему представления списка для отображения нескольких свойств [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-109">The following XML shows the list view schema for displaying several properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="cd73b-110">Укажите каждое свойство, которое будет отображаться в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-110">You must specify each property that you want displayed in the list view.</span></span>

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

<span data-ttu-id="cd73b-111">Следующие элементы XML используются для определения представления списка:</span><span class="sxs-lookup"><span data-stu-id="cd73b-111">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="cd73b-112">[Представление](./view-element-format.md) элемент является родительским для элемента представления списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-112">The [View](./view-element-format.md) element is the parent element of the list view.</span></span> <span data-ttu-id="cd73b-113">(Это же родительского элемента для таблицы, представления широкий и пользовательских элементов управления).</span><span class="sxs-lookup"><span data-stu-id="cd73b-113">(This is the same parent element for the table, wide, and custom control views.)</span></span>

- <span data-ttu-id="cd73b-114">[Имя](./name-element-for-view-format.md) элемент задает имя представления.</span><span class="sxs-lookup"><span data-stu-id="cd73b-114">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="cd73b-115">Этот элемент является обязательным для всех представлений.</span><span class="sxs-lookup"><span data-stu-id="cd73b-115">This element is required for all views.</span></span>

- <span data-ttu-id="cd73b-116">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, используемые представления.</span><span class="sxs-lookup"><span data-stu-id="cd73b-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="cd73b-117">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-117">This element is required.</span></span>

- <span data-ttu-id="cd73b-118">[GroupBy](./groupby-element-for-view-format.md) элемент определяет, когда отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="cd73b-118">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="cd73b-119">Новая группа запускается при каждом изменении значения определенных свойств или скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-119">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="cd73b-120">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-120">This element is optional.</span></span>

- <span data-ttu-id="cd73b-121">[Элементов управления](./controls-element-for-view-format.md) элемент определяет пользовательские элементы управления, которые определены в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-121">The [Controls](./controls-element-for-view-format.md) element defines the custom controls that are defined by the list view.</span></span> <span data-ttu-id="cd73b-122">Элементы управления позволяют для указания способа отображения данных.</span><span class="sxs-lookup"><span data-stu-id="cd73b-122">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="cd73b-123">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-123">This element is optional.</span></span> <span data-ttu-id="cd73b-124">Представления можно определить свои собственные пользовательские элементы управления, или он может использовать стандартные элементы управления, которые могут использоваться с любого представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="cd73b-124">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="cd73b-125">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-125">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="cd73b-126">[ListControl](./listcontrol-element-format.md) элемент определяет отображаемые в представлении и форматирования.</span><span class="sxs-lookup"><span data-stu-id="cd73b-126">The [ListControl](./listcontrol-element-format.md) element defines what is displayed in the view and how it is formatted.</span></span> <span data-ttu-id="cd73b-127">Как и с другими представлениями, представление списка можно отобразить значения свойств объекта или значения, создаваемые сценарием.</span><span class="sxs-lookup"><span data-stu-id="cd73b-127">Similar to all other views, a list view can display the values of object properties or values generated by script.</span></span>

<span data-ttu-id="cd73b-128">Например, полный файл форматирования, определяющий простое представление списка, см. в разделе [представление списка (Basic)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-128">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-list-view"></a><span data-ttu-id="cd73b-129">Предоставляет определения для представления списка</span><span class="sxs-lookup"><span data-stu-id="cd73b-129">Providing Definitions for Your List View</span></span>

<span data-ttu-id="cd73b-130">Списки можно указать одно или несколько определений с помощью дочерних элементов элемента [ListControl](./listcontrol-element-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="cd73b-130">List views can provide one or more definitions by using the child elements of the [ListControl](./listcontrol-element-format.md) element.</span></span> <span data-ttu-id="cd73b-131">Как правило представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="cd73b-131">Typically, a view will have only one definition.</span></span> <span data-ttu-id="cd73b-132">В следующем примере, представление будет содержать одного определения, отображающий несколько свойств [System.Diagnostics.Process? Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-132">In the following example, the view provides a single definition that displays several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="cd73b-133">Представление списка можно отобразить значение свойства или значение сценария (не показано в примере).</span><span class="sxs-lookup"><span data-stu-id="cd73b-133">A list view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="cd73b-134">Следующие элементы XML может использоваться для предоставления определения для представления списка:</span><span class="sxs-lookup"><span data-stu-id="cd73b-134">The following XML elements can be used to provide definitions for a list view:</span></span>

- <span data-ttu-id="cd73b-135">[ListControl](./listcontrol-element-format.md) элемент и его дочерние элементы определяют, отображаемые в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-135">The [ListControl](./listcontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="cd73b-136">[ListEntries](./listentries-element-for-listcontrol-format.md) элемент предоставляет определения представления.</span><span class="sxs-lookup"><span data-stu-id="cd73b-136">The [ListEntries](./listentries-element-for-listcontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="cd73b-137">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="cd73b-137">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="cd73b-138">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-138">This element is required.</span></span>

- <span data-ttu-id="cd73b-139">[ListEntry](./listentry-element-for-listcontrol-format.md) элемент предоставляет определение представления.</span><span class="sxs-lookup"><span data-stu-id="cd73b-139">The [ListEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="cd73b-140">По крайней мере один [ListEntry](./listentry-element-for-listcontrol-format.md) требуется; тем не менее, не ограничено максимальное количество элементов, которые могут быть добавлены.</span><span class="sxs-lookup"><span data-stu-id="cd73b-140">At least one [ListEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="cd73b-141">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="cd73b-141">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="cd73b-142">[EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент определяет объекты, которые отображаются по специфическим определением.</span><span class="sxs-lookup"><span data-stu-id="cd73b-142">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="cd73b-143">Этот элемент является необязательным и требуется только в том случае, при определении нескольких [ListEntry](./listentry-element-for-listcontrol-format.md) элементы, отображающие разные объекты.</span><span class="sxs-lookup"><span data-stu-id="cd73b-143">This element is optional and is needed only when you define multiple [ListEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="cd73b-144">[ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) определяет свойства и скрипты, значения которых отображаются в строках представления "list".</span><span class="sxs-lookup"><span data-stu-id="cd73b-144">The [ListItems](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies the properties and scripts whose values are displayed in the rows of the list view.</span></span>

- <span data-ttu-id="cd73b-145">[ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) элемент указывает свойство или скрипта, значение которого отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-145">The [ListItem](./listitems-element-for-listentry-for-listcontrol-format.md) element specifies a property or script whose value is displayed in a row of the list view.</span></span> <span data-ttu-id="cd73b-146">Представление списка необходимо указать по крайней мере одно свойство или скрипт.</span><span class="sxs-lookup"><span data-stu-id="cd73b-146">A list view must specify at least one property or script.</span></span> <span data-ttu-id="cd73b-147">Не ограничено максимальное число строк, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="cd73b-147">There is no maximum limit to the number of rows that can be specified.</span></span>

- <span data-ttu-id="cd73b-148">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) определяет свойство, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="cd73b-148">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="cd73b-149">Необходимо указать свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-149">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="cd73b-150">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) элемент указывает сценарий, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="cd73b-150">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="cd73b-151">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-151">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="cd73b-152">[Метка](./label-element-for-listitem-for-listcontrol-format.md) элемент указывает метку, которая отображается слева от значения свойства или сценарий, в строке.</span><span class="sxs-lookup"><span data-stu-id="cd73b-152">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element specifies the label that is displayed to the left of the property or script value in the row.</span></span> <span data-ttu-id="cd73b-153">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-153">This element is optional.</span></span> <span data-ttu-id="cd73b-154">Если метка не указана, отображается имя свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="cd73b-154">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="cd73b-155">Полный пример см. в разделе [представление списка (метки)](./list-view-labels.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-155">For a complete example, see [List View (Labels)](./list-view-labels.md).</span></span>

- <span data-ttu-id="cd73b-156">[ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) элемент указывает условие, которое должен существовать для строки для отображения.</span><span class="sxs-lookup"><span data-stu-id="cd73b-156">The [ItemSelectionCondition](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) element specifies a condition that must exist for the row to be displayed.</span></span> <span data-ttu-id="cd73b-157">Дополнительные сведения о добавлении условий в представлении списка см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-157">For more information about adding conditions to the list view, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span> <span data-ttu-id="cd73b-158">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-158">This element is optional.</span></span>

- <span data-ttu-id="cd73b-159">[FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) элемент определяет шаблон, который используется для отображения значения свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="cd73b-159">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a pattern that is used to display the value of the property or script.</span></span> <span data-ttu-id="cd73b-160">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-160">This element is optional.</span></span>

<span data-ttu-id="cd73b-161">Например, полный файл форматирования, определяющий простое представление списка, см. в разделе [представление списка (Basic)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-161">For an example of a complete formatting file that defines a simple list view, see [List View (Basic)](./list-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-list-view"></a><span data-ttu-id="cd73b-162">Определив объекты, используемые в представлении списка</span><span class="sxs-lookup"><span data-stu-id="cd73b-162">Defining the Objects That Use the List View</span></span>

<span data-ttu-id="cd73b-163">Существует два способа определить, какие объекты .NET использованию представления списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-163">There are two ways to define which .NET objects use the list view.</span></span> <span data-ttu-id="cd73b-164">Можно использовать [ViewSelectedBy](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться все определения представления, или [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент, чтобы определить, какие объекты будут отображаться по Определение конкретного представления.</span><span class="sxs-lookup"><span data-stu-id="cd73b-164">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="cd73b-165">В большинстве случаев представление имеет только одно определение, поэтому обычно определяются объекты [ViewSelectedBy](./viewselectedby-element-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="cd73b-165">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="cd73b-166">В следующем примере показано, как для определения объектов, которые отображаются в представлении списка с помощью [ViewSelectedBy](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="cd73b-166">The following example shows how to define the objects that are displayed by the list view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="cd73b-167">Нет ограничений на число [TypeName](./typename-element-for-viewselectedby-format.md) элементов можно указать, что их порядок не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="cd73b-167">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="cd73b-168">Чтобы указать объекты, которые используются в представлении списка можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="cd73b-168">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="cd73b-169">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-169">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="cd73b-170">[TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает объект .NET, которое отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-170">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="cd73b-171">Полное имя типа .NET является обязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-171">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="cd73b-172">Необходимо указать по крайней мере один тип или выбора для представления, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="cd73b-172">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="cd73b-173">Например, полный файл форматирования, см. в разделе [представление списка (Basic)](./list-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-173">For an example of a complete formatting file, see [List View (Basic)](./list-view-basic.md).</span></span>

<span data-ttu-id="cd73b-174">В следующем примере используется [ViewSelectedBy](./viewselectedby-element-format.md) и [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="cd73b-174">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="cd73b-175">Используйте наборы выделения, где, что у вас есть набор связанных объектов, которые отображаются в нескольких представлениях, например при определении представления списка и представление таблицы для те же объекты.</span><span class="sxs-lookup"><span data-stu-id="cd73b-175">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="cd73b-176">Дополнительные сведения о том, как создать набор выбора см. в разделе [определение наборы выделения](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-176">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

<span data-ttu-id="cd73b-177">Чтобы указать объекты, которые используются в представлении списка можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="cd73b-177">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="cd73b-178">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="cd73b-178">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="cd73b-179">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элемент указывает набор объектов, которые могут отображаться в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-179">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="cd73b-180">Необходимо указать по крайней мере одного набора или тип для представления, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="cd73b-180">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="cd73b-181">В следующем примере показано, как для определения объектов, отображаемых командлетом точное определение представления списка, используя [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="cd73b-181">The following example shows how to define the objects displayed by a specific definition of the list view using the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element.</span></span> <span data-ttu-id="cd73b-182">С помощью этого элемента, можно указать имя типа .NET объект набора выбора объектов и выбора условие, которое указывает, когда используется определение.</span><span class="sxs-lookup"><span data-stu-id="cd73b-182">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="cd73b-183">Дополнительные сведения о том, как для создания выделения условий см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-183">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</ListEntry>
```

<span data-ttu-id="cd73b-184">Чтобы указать объекты, которые используются с конкретным определением в представлении списка можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="cd73b-184">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="cd73b-185">[EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент определяет, какие объекты отображаются с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="cd73b-185">The [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="cd73b-186">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) элемент указывает объект .NET, которое отображается с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="cd73b-186">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="cd73b-187">При использовании этого элемента, требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="cd73b-187">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="cd73b-188">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="cd73b-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="cd73b-189">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает набор объектов, которые могут отображаться в соответствии с этим определением.</span><span class="sxs-lookup"><span data-stu-id="cd73b-189">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="cd73b-190">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="cd73b-190">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="cd73b-191">[SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) элемент (не показано) определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="cd73b-191">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="cd73b-192">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="cd73b-192">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="cd73b-193">Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-193">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-list-view"></a><span data-ttu-id="cd73b-194">Отображение групп объектов в представлении списка</span><span class="sxs-lookup"><span data-stu-id="cd73b-194">Displaying Groups of Objects in a List View</span></span>

<span data-ttu-id="cd73b-195">Можно разделить объекты, которые отображаются в представлении списка в группы.</span><span class="sxs-lookup"><span data-stu-id="cd73b-195">You can separate the objects that are displayed by the list view into groups.</span></span> <span data-ttu-id="cd73b-196">Это не означает, что можно определить группу, только для Windows PowerShell запускает новую группу, при каждом изменении значения определенных свойств или скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-196">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="cd73b-197">В следующем примере запускается группу всякий раз, когда значение [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="cd73b-197">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="cd73b-198">Следующие элементы XML используются для определения при запуске группы:</span><span class="sxs-lookup"><span data-stu-id="cd73b-198">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="cd73b-199">[GroupBy](./groupby-element-for-view-format.md) элемент определяет свойства или сценарий, который запускает новую группу и определяет порядок отображения группы.</span><span class="sxs-lookup"><span data-stu-id="cd73b-199">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="cd73b-200">[PropertyName](./propertyname-element-for-groupby-format.md) элемент указывает свойство, которое запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="cd73b-200">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="cd73b-201">Необходимо указать свойство или скрипт для запуска в группу, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-201">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="cd73b-202">[ScriptBlock](./scriptblock-element-for-groupby-format.md) элемент указывает сценарий, который запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="cd73b-202">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="cd73b-203">Необходимо указать сценарий или свойство для запуска в группу, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-203">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="cd73b-204">[Метка](./label-element-for-groupby-format.md) элемент определяет метку, которая отображается в начале каждой группы.</span><span class="sxs-lookup"><span data-stu-id="cd73b-204">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="cd73b-205">Помимо текст, заданный этим элементом Windows PowerShell отображает значение, которое активируется новая группа и добавляет пустой строки до и после метки.</span><span class="sxs-lookup"><span data-stu-id="cd73b-205">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="cd73b-206">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-206">This element is optional.</span></span>

- <span data-ttu-id="cd73b-207">[Пользовательский элемент управления](./customcontrol-element-for-groupby-format.md) элемент определяет элемент управления, который используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="cd73b-207">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="cd73b-208">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-208">This element is optional.</span></span>

- <span data-ttu-id="cd73b-209">[CustomControlName](./customcontrolname-element-for-groupby-format.md) элемент указывает общий или просмотра элемента управления, который используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="cd73b-209">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="cd73b-210">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cd73b-210">This element is optional.</span></span>

<span data-ttu-id="cd73b-211">Например, полный файл форматирования, который определяет группы, см. в разделе [представление списка (GroupBy)](./list-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="cd73b-211">For an example of a complete formatting file that defines groups, see [List View (GroupBy)](./list-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="cd73b-212">С помощью строки формата</span><span class="sxs-lookup"><span data-stu-id="cd73b-212">Using Format Strings</span></span>

<span data-ttu-id="cd73b-213">Строки форматирования можно добавить в представление, чтобы более детально определить способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="cd73b-213">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="cd73b-214">Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.</span><span class="sxs-lookup"><span data-stu-id="cd73b-214">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

<span data-ttu-id="cd73b-215">Следующие элементы XML может использоваться для указания шаблона формата:</span><span class="sxs-lookup"><span data-stu-id="cd73b-215">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="cd73b-216">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) элемент указывает данные, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-216">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="cd73b-217">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-217">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="cd73b-218">Необходимо указать свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-218">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="cd73b-219">[FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-219">The [FormatString](./formatstring-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

- <span data-ttu-id="cd73b-220">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-220">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="cd73b-221">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-221">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="cd73b-222">В следующем примере `ToString` метод вызывается для форматирования значения переменной скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-222">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="cd73b-223">Скрипты можно вызвать любой метод объекта.</span><span class="sxs-lookup"><span data-stu-id="cd73b-223">Scripts can call any method of an object.</span></span> <span data-ttu-id="cd73b-224">Таким образом Если объект имеет метод, такой как `ToString`, с параметрами форматирования, скрипт можно вызвать этот метод для форматирования значения выходных данных сценария.</span><span class="sxs-lookup"><span data-stu-id="cd73b-224">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="cd73b-225">Следующий XML-элемент может использоваться для вызова метода `ToString` метод:</span><span class="sxs-lookup"><span data-stu-id="cd73b-225">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="cd73b-226">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) элемент указывает данные, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-226">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="cd73b-227">[ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="cd73b-227">The [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="cd73b-228">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="cd73b-228">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd73b-229">См. также</span><span class="sxs-lookup"><span data-stu-id="cd73b-229">See Also</span></span>

[<span data-ttu-id="cd73b-230">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd73b-230">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)
