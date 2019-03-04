---
title: Создание широкое представление | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4303c5-b451-4ccb-9831-b17a17ceac20
caps.latest.revision: 16
ms.openlocfilehash: 651de5d3bc2619f20438f3951ac5a8c4b0bf46d4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858500"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="ee71f-102">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="ee71f-102">Creating a Wide View</span></span>

<span data-ttu-id="ee71f-103">Широкое представление отображает одно значение для каждого объекта, который отображается.</span><span class="sxs-lookup"><span data-stu-id="ee71f-103">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="ee71f-104">Отображаемое значение может быть значение свойства объекта .NET или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-104">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="ee71f-105">По умолчанию отсутствует метка или заголовок для этого представления.</span><span class="sxs-lookup"><span data-stu-id="ee71f-105">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="ee71f-106">Отображение широкое представление</span><span class="sxs-lookup"><span data-stu-id="ee71f-106">A Wide View Display</span></span>

<span data-ttu-id="ee71f-107">В следующем примере показано, как Windows PowerShell отображает [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объект, возвращаемый [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) передается по конвейеру выходные данные командлета [ Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) командлета.</span><span class="sxs-lookup"><span data-stu-id="ee71f-107">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="ee71f-108">(По умолчанию [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлет возвращает представление таблицы.) В этом примере два столбца используются для отображения имени процесса для каждого возвращенного объекта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-108">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="ee71f-109">Имя свойства объекта не отображается, только значение свойства.</span><span class="sxs-lookup"><span data-stu-id="ee71f-109">The name of the object's property is not displayed, only the value of the property.</span></span>

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a><span data-ttu-id="ee71f-110">Определение широкое представление</span><span class="sxs-lookup"><span data-stu-id="ee71f-110">Defining the Wide View</span></span>

<span data-ttu-id="ee71f-111">Следующий код XML показывает широкое представление схемы для [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-111">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

<span data-ttu-id="ee71f-112">Следующие элементы XML используются для определения широкое представление:</span><span class="sxs-lookup"><span data-stu-id="ee71f-112">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="ee71f-113">[Представление](./view-element-format.md) элемент является родительским для элемента широкое представление.</span><span class="sxs-lookup"><span data-stu-id="ee71f-113">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="ee71f-114">(Это же родительский элемент для таблицы, список и представления пользовательского элемента управления).</span><span class="sxs-lookup"><span data-stu-id="ee71f-114">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="ee71f-115">[Имя](./name-element-for-view-format.md) элемент задает имя представления.</span><span class="sxs-lookup"><span data-stu-id="ee71f-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="ee71f-116">Этот элемент является обязательным для всех представлений.</span><span class="sxs-lookup"><span data-stu-id="ee71f-116">This element is required for all views.</span></span>

- <span data-ttu-id="ee71f-117">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, используемые представления.</span><span class="sxs-lookup"><span data-stu-id="ee71f-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="ee71f-118">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-118">This element is required.</span></span>

- <span data-ttu-id="ee71f-119">[GroupBy](./groupby-element-for-view-format.md) элемент определяет, когда отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="ee71f-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="ee71f-120">Новая группа запускается при каждом изменении значения определенных свойств или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="ee71f-121">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-121">This element is optional.</span></span>

- <span data-ttu-id="ee71f-122">[Элементов управления](./controls-element-for-view-format.md) элементов определяет пользовательские элементы управления, которые определяются широкое представление.</span><span class="sxs-lookup"><span data-stu-id="ee71f-122">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="ee71f-123">Элементы управления позволяют для указания способа отображения данных.</span><span class="sxs-lookup"><span data-stu-id="ee71f-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="ee71f-124">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-124">This element is optional.</span></span> <span data-ttu-id="ee71f-125">Представления можно определить свои собственные пользовательские элементы управления, или он может использовать стандартные элементы управления, которые могут использоваться с любого представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="ee71f-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="ee71f-126">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="ee71f-127">[WideControl](./widecontrol-element-format.md) элемент и его дочерние элементы определяют, отображаемые в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-127">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="ee71f-128">В приведенном выше примере представление предназначена для отображения [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) свойство.</span><span class="sxs-lookup"><span data-stu-id="ee71f-128">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="ee71f-129">Например, полный файл форматирования, который определяет простой широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-129">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="ee71f-130">Предоставляет определения для вашей широкое представление</span><span class="sxs-lookup"><span data-stu-id="ee71f-130">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="ee71f-131">Широкие представления можно указать одно или несколько определений с помощью дочерних элементов элемента [WideControl](./widecontrol-element-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="ee71f-131">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="ee71f-132">Как правило представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="ee71f-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="ee71f-133">В следующем примере, представление будет содержать одно определение, которое отображает значение [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) свойство.</span><span class="sxs-lookup"><span data-stu-id="ee71f-133">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="ee71f-134">Широкое представление может отображать значение свойства или значение сценария (не показано в примере).</span><span class="sxs-lookup"><span data-stu-id="ee71f-134">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="ee71f-135">Следующие элементы XML может использоваться для предоставления определения для широкое представление:</span><span class="sxs-lookup"><span data-stu-id="ee71f-135">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="ee71f-136">[WideControl](./widecontrol-element-format.md) элемент и его дочерние элементы определяют, отображаемые в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-136">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="ee71f-137">[AutoSize](./autosize-element-for-widecontrol-format.md) элемент указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных.</span><span class="sxs-lookup"><span data-stu-id="ee71f-137">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="ee71f-138">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-138">This element is optional.</span></span>

- <span data-ttu-id="ee71f-139">[ColumnNumber](./columnnumber-element-for-widecontrol-format.md) элемент указывает количество столбцов, отображаемых в широком представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-139">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="ee71f-140">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-140">This element is optional.</span></span>

- <span data-ttu-id="ee71f-141">[WideEntries](./wideentries-element-for-widecontrol-format.md) элемент предоставляет определения представления.</span><span class="sxs-lookup"><span data-stu-id="ee71f-141">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="ee71f-142">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="ee71f-142">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="ee71f-143">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-143">This element is required.</span></span>

- <span data-ttu-id="ee71f-144">[WideEntry](./wideentry-element-for-widecontrol-format.md) элемент предоставляет определение представления.</span><span class="sxs-lookup"><span data-stu-id="ee71f-144">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="ee71f-145">По крайней мере один [WideEntry](./wideentry-element-for-widecontrol-format.md) требуется; тем не менее, не ограничено максимальное количество элементов, которые могут быть добавлены.</span><span class="sxs-lookup"><span data-stu-id="ee71f-145">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="ee71f-146">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="ee71f-146">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="ee71f-147">[EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент определяет объекты, которые отображаются по специфическим определением.</span><span class="sxs-lookup"><span data-stu-id="ee71f-147">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="ee71f-148">Этот элемент является необязательным и требуется только в том случае, при определении нескольких [WideEntry](./wideentry-element-for-widecontrol-format.md) элементы, отображающие разные объекты.</span><span class="sxs-lookup"><span data-stu-id="ee71f-148">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="ee71f-149">[WideItem](./wideitem-element-for-widecontrol-format.md) элемент указывает данные, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-149">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="ee71f-150">В отличие от других типов представлений ширину элемента управления можно отобразить только один элемент.</span><span class="sxs-lookup"><span data-stu-id="ee71f-150">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="ee71f-151">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-151">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="ee71f-152">Необходимо указать свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-152">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="ee71f-153">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) элемент указывает сценарий, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-153">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="ee71f-154">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-154">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="ee71f-155">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) элемент определяет шаблон, который используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="ee71f-155">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="ee71f-156">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-156">This element is optional.</span></span>

<span data-ttu-id="ee71f-157">Например, полный файл форматирования, определяющий определение широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-157">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="ee71f-158">Определение объектов, использующих широкое представление</span><span class="sxs-lookup"><span data-stu-id="ee71f-158">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="ee71f-159">Чтобы определить, какие объекты .NET использовать широкое представление двумя способами.</span><span class="sxs-lookup"><span data-stu-id="ee71f-159">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="ee71f-160">Можно использовать [ViewSelectedBy](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться все определения представления, или [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент, чтобы определить, какие объекты будут отображаться по Определение конкретного представления.</span><span class="sxs-lookup"><span data-stu-id="ee71f-160">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="ee71f-161">В большинстве случаев представление имеет только одно определение, поэтому обычно определяются объекты [ViewSelectedBy](./viewselectedby-element-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="ee71f-161">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="ee71f-162">В следующем примере показано, как для определения объектов, отображаемых элементом в широком представлении с помощью [ViewSelectedBy](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="ee71f-162">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="ee71f-163">Нет ограничений на число [TypeName](./typename-element-for-viewselectedby-format.md) элементов можно указать, что их порядок не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="ee71f-163">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="ee71f-164">Чтобы указать объекты, используемые широкое представление можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="ee71f-164">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="ee71f-165">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет, какие объекты отображаются по широкое представление.</span><span class="sxs-lookup"><span data-stu-id="ee71f-165">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="ee71f-166">[TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает .NET, которое отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-166">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="ee71f-167">Полное имя типа .NET является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-167">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="ee71f-168">Необходимо указать по крайней мере один тип или выбора для представления, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="ee71f-168">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="ee71f-169">Например, полный файл форматирования, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-169">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="ee71f-170">В следующем примере используется [ViewSelectedBy](./viewselectedby-element-format.md) и [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="ee71f-170">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="ee71f-171">Используйте наборы выделения, где, что у вас есть набор связанных объектов, которые отображаются в нескольких представлениях, например при определении широкое представление и представление таблицы для те же объекты.</span><span class="sxs-lookup"><span data-stu-id="ee71f-171">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="ee71f-172">Дополнительные сведения о том, как создать набор выбора см. в разделе [определение наборы выделения](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-172">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="ee71f-173">Чтобы указать объекты, используемые широкое представление можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="ee71f-173">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="ee71f-174">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет, какие объекты отображаются по широкое представление.</span><span class="sxs-lookup"><span data-stu-id="ee71f-174">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="ee71f-175">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элемент указывает набор объектов, которые могут отображаться в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-175">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="ee71f-176">Необходимо указать по крайней мере одного набора или тип для представления, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="ee71f-176">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="ee71f-177">В следующем примере показано, как для определения объектов, отображаемых командлетом точное определение широкое представление, используя [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="ee71f-177">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="ee71f-178">С помощью этого элемента, можно указать имя типа .NET объект набора выбора объектов и выбора условие, которое указывает, когда используется определение.</span><span class="sxs-lookup"><span data-stu-id="ee71f-178">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="ee71f-179">Дополнительные сведения о том, как для создания выделения условий см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-179">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="ee71f-180">Чтобы указать объекты, которые используются с конкретным определением широкое представление можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="ee71f-180">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="ee71f-181">[EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) элемент определяет, какие объекты отображаются с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="ee71f-181">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="ee71f-182">[TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает .NET, которое отображается с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="ee71f-182">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="ee71f-183">При использовании этого элемента требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="ee71f-183">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="ee71f-184">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="ee71f-184">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="ee71f-185">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) (не показано) указывает набор объектов, которые могут отображаться в соответствии с этим определением.</span><span class="sxs-lookup"><span data-stu-id="ee71f-185">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="ee71f-186">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="ee71f-186">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="ee71f-187">[SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) элемент (не показано) определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="ee71f-187">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="ee71f-188">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="ee71f-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="ee71f-189">Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-189">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="ee71f-190">Отображение групп объектов в широком представлении</span><span class="sxs-lookup"><span data-stu-id="ee71f-190">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="ee71f-191">Можно разделить объекты, которые отображаются по широкое представление, в группы.</span><span class="sxs-lookup"><span data-stu-id="ee71f-191">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="ee71f-192">Это не означает, что можно определить группу, только для Windows PowerShell запускает новую группу, при каждом изменении значения определенных свойств или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-192">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="ee71f-193">В следующем примере запускается группу всякий раз, когда значение [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="ee71f-193">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="ee71f-194">Следующие элементы XML используются для определения при запуске группы:</span><span class="sxs-lookup"><span data-stu-id="ee71f-194">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="ee71f-195">[GroupBy](./groupby-element-for-view-format.md) элемент определяет свойства или сценарий, который запускает новую группу и определяет порядок отображения группы.</span><span class="sxs-lookup"><span data-stu-id="ee71f-195">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="ee71f-196">[PropertyName](./propertyname-element-for-groupby-format.md) элемент указывает свойство, которое запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="ee71f-196">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="ee71f-197">Необходимо указать свойство или скрипт для запуска в группу, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-197">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="ee71f-198">[ScriptBlock](./scriptblock-element-for-groupby-format.md) элемент указывает сценарий, который запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="ee71f-198">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="ee71f-199">Необходимо указать сценарий или свойство для запуска в группу, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-199">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="ee71f-200">[Метка](./label-element-for-groupby-format.md) элемент определяет метку, которая отображается в начале каждой группы.</span><span class="sxs-lookup"><span data-stu-id="ee71f-200">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="ee71f-201">Помимо текст, заданный этим элементом Windows PowerShell отображает значение, которое активируется новая группа и добавляет пустой строки до и после метки.</span><span class="sxs-lookup"><span data-stu-id="ee71f-201">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="ee71f-202">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-202">This element is optional.</span></span>

- <span data-ttu-id="ee71f-203">[Пользовательский элемент управления](./customcontrol-element-for-groupby-format.md) элемент определяет элемент управления, который используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="ee71f-203">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="ee71f-204">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-204">This element is optional.</span></span>

- <span data-ttu-id="ee71f-205">[CustomControlName](./customcontrolname-element-for-groupby-format.md) элемент указывает общий или просмотра элемента управления, который используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="ee71f-205">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="ee71f-206">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ee71f-206">This element is optional.</span></span>

<span data-ttu-id="ee71f-207">Например, полный файл форматирования, который определяет группы, см. в разделе [широкое представление (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="ee71f-207">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="ee71f-208">С помощью строки формата</span><span class="sxs-lookup"><span data-stu-id="ee71f-208">Using Format Strings</span></span>

<span data-ttu-id="ee71f-209">Строки форматирования могут добавляться в широком представлении, чтобы более детально определить способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="ee71f-209">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="ee71f-210">Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.</span><span class="sxs-lookup"><span data-stu-id="ee71f-210">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="ee71f-211">Следующие элементы XML может использоваться для указания шаблона формата:</span><span class="sxs-lookup"><span data-stu-id="ee71f-211">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="ee71f-212">[WideItem](./wideitem-element-for-widecontrol-format.md) элемент указывает данные, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-212">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="ee71f-213">[PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-213">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="ee71f-214">Необходимо указать свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="ee71f-215">[FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении</span><span class="sxs-lookup"><span data-stu-id="ee71f-215">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="ee71f-216">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-216">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="ee71f-217">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-217">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="ee71f-218">В следующем примере `ToString` метод вызывается для форматирования значения переменной скрипта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-218">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="ee71f-219">Скрипты можно вызвать любой метод объекта.</span><span class="sxs-lookup"><span data-stu-id="ee71f-219">Scripts can call any method of an object.</span></span> <span data-ttu-id="ee71f-220">Таким образом Если объект имеет метод, такой как `ToString`, с параметрами форматирования, скрипт можно вызвать этот метод для форматирования значения выходных данных сценария.</span><span class="sxs-lookup"><span data-stu-id="ee71f-220">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="ee71f-221">Следующий XML-элемент может использоваться для вызова метода `ToString` метод:</span><span class="sxs-lookup"><span data-stu-id="ee71f-221">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="ee71f-222">[WideItem](./wideitem-element-for-widecontrol-format.md) элемент указывает данные, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-222">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="ee71f-223">[ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) элемент (не показано) указывает сценарий, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ee71f-223">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="ee71f-224">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ee71f-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee71f-225">См. также</span><span class="sxs-lookup"><span data-stu-id="ee71f-225">See Also</span></span>

[<span data-ttu-id="ee71f-226">Широкое представление (Basic)</span><span class="sxs-lookup"><span data-stu-id="ee71f-226">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="ee71f-227">Широкое представление (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="ee71f-227">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="ee71f-228">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee71f-228">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
