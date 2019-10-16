---
title: Создание расширенного представления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4303c5-b451-4ccb-9831-b17a17ceac20
caps.latest.revision: 16
ms.openlocfilehash: 651de5d3bc2619f20438f3951ac5a8c4b0bf46d4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368953"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="0b1d7-102">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="0b1d7-102">Creating a Wide View</span></span>

<span data-ttu-id="0b1d7-103">В расширенном представлении отображается одно значение для каждого отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-103">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="0b1d7-104">Отображаемое значение может быть значением свойства объекта .NET или значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-104">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="0b1d7-105">По умолчанию для этого представления отсутствует метка или заголовок.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-105">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="0b1d7-106">Отображение расширенного представления</span><span class="sxs-lookup"><span data-stu-id="0b1d7-106">A Wide View Display</span></span>

<span data-ttu-id="0b1d7-107">В следующем примере показано, как Windows PowerShell отображает объект [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) , возвращаемый командлетом [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , когда его выходные данные передаются в командлет [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-107">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="0b1d7-108">(По умолчанию командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) возвращает табличное представление.) В этом примере два столбца используются для вывода имени процесса для каждого возвращаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-108">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="0b1d7-109">Имя свойства объекта не отображается, только значение свойства.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-109">The name of the object's property is not displayed, only the value of the property.</span></span>

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

## <a name="defining-the-wide-view"></a><span data-ttu-id="0b1d7-110">Определение расширенного представления</span><span class="sxs-lookup"><span data-stu-id="0b1d7-110">Defining the Wide View</span></span>

<span data-ttu-id="0b1d7-111">В следующем коде XML показана схема широкой схемы представления для объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-111">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="0b1d7-112">Для определения широкого представления используются следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-112">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="0b1d7-113">Элемент [View](./view-element-format.md) является родительским элементом для широкого представления.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-113">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="0b1d7-114">(Это тот же родительский элемент для представлений таблицы, списка и пользовательского элемента управления.)</span><span class="sxs-lookup"><span data-stu-id="0b1d7-114">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="0b1d7-115">Элемент [Name](./name-element-for-view-format.md) указывает имя представления.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-115">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="0b1d7-116">Этот элемент является обязательным для всех представлений.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-116">This element is required for all views.</span></span>

- <span data-ttu-id="0b1d7-117">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет объекты, которые используют представление.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="0b1d7-118">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-118">This element is required.</span></span>

- <span data-ttu-id="0b1d7-119">Элемент [GroupBy](./groupby-element-for-view-format.md) определяет, когда отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-119">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="0b1d7-120">Новая группа запускается каждый раз при изменении значения определенного свойства или сценария.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-120">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="0b1d7-121">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-121">This element is optional.</span></span>

- <span data-ttu-id="0b1d7-122">Элементы [управления](./controls-element-for-view-format.md) определяют пользовательские элементы управления, определяемые широким представлением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-122">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="0b1d7-123">Элементы управления позволяют дополнительно указать способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-123">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="0b1d7-124">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-124">This element is optional.</span></span> <span data-ttu-id="0b1d7-125">Представление может определять собственные пользовательские элементы управления или использовать стандартные элементы управления, которые могут использоваться любыми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-125">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="0b1d7-126">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-126">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="0b1d7-127">Элемент [видеконтрол](./widecontrol-element-format.md) и его дочерние элементы определяют, что отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-127">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="0b1d7-128">В предыдущем примере представление предназначено для отображения свойства [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-128">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="0b1d7-129">Пример полного файла форматирования, определяющего простое представление, см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-129">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="0b1d7-130">Предоставление определений для вашего широкого представления</span><span class="sxs-lookup"><span data-stu-id="0b1d7-130">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="0b1d7-131">Широкие представления могут предоставлять одно или несколько определений с помощью дочерних элементов элемента [видеконтрол](./widecontrol-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-131">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="0b1d7-132">Как правило, представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-132">Typically, a view will have only one definition.</span></span> <span data-ttu-id="0b1d7-133">В следующем примере представление предоставляет одно определение, которое отображает значение свойства [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-133">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="0b1d7-134">В расширенном представлении может отображаться значение свойства или значение скрипта (не показано в примере).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-134">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

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

<span data-ttu-id="0b1d7-135">Следующие XML-элементы можно использовать для определения расширенного представления:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-135">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="0b1d7-136">Элемент [видеконтрол](./widecontrol-element-format.md) и его дочерние элементы определяют, что отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-136">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="0b1d7-137">Элемент [AutoSize](./autosize-element-for-widecontrol-format.md) указывает, корректируется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-137">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="0b1d7-138">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-138">This element is optional.</span></span>

- <span data-ttu-id="0b1d7-139">Элемент [columnNumber](./columnnumber-element-for-widecontrol-format.md) указывает количество столбцов, отображаемых в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-139">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="0b1d7-140">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-140">This element is optional.</span></span>

- <span data-ttu-id="0b1d7-141">Элемент [видинтриес](./wideentries-element-for-widecontrol-format.md) предоставляет определения представления.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-141">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="0b1d7-142">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-142">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="0b1d7-143">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-143">This element is required.</span></span>

- <span data-ttu-id="0b1d7-144">Элемент [видинтри](./wideentry-element-for-widecontrol-format.md) предоставляет определение представления.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-144">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="0b1d7-145">Требуется по крайней мере один [видинтри](./wideentry-element-for-widecontrol-format.md) ; Однако максимальное количество элементов, которые можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-145">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="0b1d7-146">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-146">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="0b1d7-147">Элемент [ентриселектедби](./entryselectedby-element-for-wideentry-format.md) указывает объекты, отображаемые конкретным определением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-147">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="0b1d7-148">Этот элемент является необязательным и необходим только при определении нескольких элементов [видинтри](./wideentry-element-for-widecontrol-format.md) , отображающих разные объекты.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-148">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="0b1d7-149">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) указывает данные, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-149">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="0b1d7-150">В отличие от других типов представлений, широкий элемент управления может отображать только один элемент.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-150">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="0b1d7-151">Элемент [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) указывает свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-151">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="0b1d7-152">Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-152">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="0b1d7-153">Элемент [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) задает скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-153">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="0b1d7-154">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-154">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="0b1d7-155">Элемент [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) указывает шаблон, используемый для вывода данных.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-155">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="0b1d7-156">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-156">This element is optional.</span></span>

<span data-ttu-id="0b1d7-157">Пример полного файла форматирования, определяющего определение расширенного представления, см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-157">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="0b1d7-158">Определение объектов, использующих широкие представления</span><span class="sxs-lookup"><span data-stu-id="0b1d7-158">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="0b1d7-159">Существует два способа определения объектов .NET, использующих широкое представление.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-159">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="0b1d7-160">Элемент [виевселектедби](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться всеми определениями представления, или можно использовать элемент [ентриселектедби](./entryselectedby-element-for-wideentry-format.md) для определения объектов, отображаемых определенным определением представления.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-160">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="0b1d7-161">В большинстве случаев представление имеет только одно определение, поэтому объекты обычно определяются элементом [виевселектедби](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-161">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="0b1d7-162">В следующем примере показано, как определить объекты, отображаемые в расширенном представлении с помощью элементов [виевселектедби](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-162">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="0b1d7-163">Количество элементов [TypeName](./typename-element-for-viewselectedby-format.md) , которые можно указать, не ограничено, и их порядок не важен.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-163">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="0b1d7-164">Следующие XML-элементы можно использовать для указания объектов, используемых в расширенном представлении:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-164">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="0b1d7-165">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-165">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="0b1d7-166">Элемент [TypeName](./typename-element-for-viewselectedby-format.md) указывает .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-166">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="0b1d7-167">Требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-167">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="0b1d7-168">Необходимо указать по крайней мере один тип или набор элементов для представления, но максимальное количество заданных объектов не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-168">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="0b1d7-169">Пример полного файла форматирования см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-169">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="0b1d7-170">В следующем примере используются элементы [виевселектедби](./viewselectedby-element-format.md) и [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-170">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="0b1d7-171">Используйте наборы выбора, в которых имеется связанный набор объектов, отображаемых с помощью нескольких представлений, например при определении расширенного представления и табличного представления для тех же объектов.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-171">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="0b1d7-172">Дополнительные сведения о создании набора выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-172">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="0b1d7-173">Следующие XML-элементы можно использовать для указания объектов, используемых в расширенном представлении:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-173">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="0b1d7-174">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-174">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="0b1d7-175">Элемент [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) указывает набор объектов, которые могут быть отображены представлением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-175">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="0b1d7-176">Необходимо указать хотя бы один набор выбора или тип для представления, но максимальное количество элементов, которое можно указать, не существует.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-176">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="0b1d7-177">В следующем примере показано, как определить объекты, отображаемые определенным определением расширенного представления с помощью элемента [ентриселектедби](./entryselectedby-element-for-wideentry-format.md) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-177">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="0b1d7-178">С помощью этого элемента можно указать имя типа .NET объекта, набор элементов выбора объектов или условие выбора, которое указывает, когда используется определение.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-178">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="0b1d7-179">Дополнительные сведения о создании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-179">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="0b1d7-180">Следующие XML-элементы можно использовать для указания объектов, которые используются в определенном определении расширенного представления:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-180">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="0b1d7-181">Элемент [ентриселектедби](./entryselectedby-element-for-wideentry-format.md) определяет, какие объекты отображаются в определении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-181">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="0b1d7-182">Элемент [TypeName](./typename-element-for-viewselectedby-format.md) указывает .NET, отображаемый определением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-182">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="0b1d7-183">При использовании этого элемента требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-183">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="0b1d7-184">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-184">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="0b1d7-185">Элемент [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) (не показан) задает набор объектов, которые могут отображаться в этом определении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-185">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="0b1d7-186">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-186">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="0b1d7-187">Элемент [селектионкондитион](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) (не показано) указывает условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-187">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="0b1d7-188">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-188">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="0b1d7-189">Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-189">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="0b1d7-190">Отображение групп объектов в широком представлении</span><span class="sxs-lookup"><span data-stu-id="0b1d7-190">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="0b1d7-191">Объекты, отображаемые в расширенном представлении, можно разделить на группы.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-191">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="0b1d7-192">Это не означает, что вы определяете группу, а только то, что Windows PowerShell запускает новую группу всякий раз, когда изменяется значение определенного свойства или сценария.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-192">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="0b1d7-193">В следующем примере новая группа запускается всякий раз, когда изменяется свойство [System. ServiceProcess. ServiceController. serviceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) .</span><span class="sxs-lookup"><span data-stu-id="0b1d7-193">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="0b1d7-194">Следующие XML-элементы используются для определения времени запуска группы:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-194">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="0b1d7-195">Элемент [GroupBy](./groupby-element-for-view-format.md) определяет свойство или скрипт, который запускает новую группу и определяет, как будет отображаться группа.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-195">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="0b1d7-196">Элемент [PropertyName](./propertyname-element-for-groupby-format.md) указывает свойство, которое запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-196">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="0b1d7-197">Необходимо указать свойство или скрипт для запуска группы, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-197">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="0b1d7-198">Элемент [ScriptBlock](./scriptblock-element-for-groupby-format.md) указывает скрипт, который запускает новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-198">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="0b1d7-199">Необходимо указать скрипт или свойство для запуска группы, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-199">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="0b1d7-200">Элемент [Label](./label-element-for-groupby-format.md) определяет метку, которая отображается в начале каждой группы.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-200">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="0b1d7-201">В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает значение, вызвавшее новую группу, и добавляет пустую строку до и после метки.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-201">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="0b1d7-202">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-202">This element is optional.</span></span>

- <span data-ttu-id="0b1d7-203">Элемент [Ошибка customcontrol](./customcontrol-element-for-groupby-format.md) определяет элемент управления, используемый для вывода данных.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-203">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="0b1d7-204">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-204">This element is optional.</span></span>

- <span data-ttu-id="0b1d7-205">Элемент [кустомконтролнаме](./customcontrolname-element-for-groupby-format.md) указывает общий элемент управления или представление, которое используется для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-205">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="0b1d7-206">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-206">This element is optional.</span></span>

<span data-ttu-id="0b1d7-207">Пример полного файла форматирования, определяющего группы, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d7-207">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="0b1d7-208">Использование строк формата</span><span class="sxs-lookup"><span data-stu-id="0b1d7-208">Using Format Strings</span></span>

<span data-ttu-id="0b1d7-209">Строки форматирования можно добавить в расширенное представление, чтобы дополнительно определить способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-209">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="0b1d7-210">В следующем примере показано, как определить строку форматирования для значения свойства `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-210">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="0b1d7-211">Для указания шаблона формата можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-211">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="0b1d7-212">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) указывает данные, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-212">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="0b1d7-213">Элемент [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) указывает свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-213">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="0b1d7-214">Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="0b1d7-215">Элемент [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-215">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="0b1d7-216">Элемент [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (не показан) задает скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-216">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="0b1d7-217">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-217">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="0b1d7-218">В следующем примере вызывается метод `ToString` для форматирования значения скрипта.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-218">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="0b1d7-219">Скрипты могут вызывать любой метод объекта.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-219">Scripts can call any method of an object.</span></span> <span data-ttu-id="0b1d7-220">Таким образом, если у объекта есть метод, например `ToString`, имеющий параметры форматирования, скрипт может вызвать этот метод для форматирования выходного значения скрипта.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-220">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="0b1d7-221">Следующий XML-элемент можно использовать для вызова метода `ToString`:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-221">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="0b1d7-222">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) указывает данные, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-222">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="0b1d7-223">Элемент [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) (не показан) задает скрипт, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-223">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="0b1d7-224">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0b1d7-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b1d7-225">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b1d7-225">See Also</span></span>

[<span data-ttu-id="0b1d7-226">Широкой вид (базовый)</span><span class="sxs-lookup"><span data-stu-id="0b1d7-226">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="0b1d7-227">Расширенное представление (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="0b1d7-227">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="0b1d7-228">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1d7-228">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
