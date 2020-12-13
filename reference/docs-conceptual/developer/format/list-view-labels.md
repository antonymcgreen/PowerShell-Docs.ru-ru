---
ms.date: 09/13/2016
ms.topic: reference
title: Представление списка (метки)
description: Представление списка (метки)
ms.openlocfilehash: 2d341ae95d025e0f95b5d88b96afb846b62b092f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666694"
---
# <a name="list-view-labels"></a><span data-ttu-id="57c8a-103">Представление списка (метки)</span><span class="sxs-lookup"><span data-stu-id="57c8a-103">List View (Labels)</span></span>

<span data-ttu-id="57c8a-104">В этом примере показано, как реализовать представление списка, в котором отображается пользовательская метка для каждой строки списка.</span><span class="sxs-lookup"><span data-stu-id="57c8a-104">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="57c8a-105">В этом представлении списка отображаются свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемое командлетом [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) .</span><span class="sxs-lookup"><span data-stu-id="57c8a-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="57c8a-106">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="57c8a-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="57c8a-107">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="57c8a-107">To load this formatting file</span></span>

1. <span data-ttu-id="57c8a-108">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="57c8a-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="57c8a-109">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="57c8a-109">Save the text file.</span></span> <span data-ttu-id="57c8a-110">Не забудьте добавить `format.ps1xml` расширение в файл, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="57c8a-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="57c8a-111">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="57c8a-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="57c8a-112">Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57c8a-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="57c8a-113">Этот параметр необходимо использовать `prependPath` при выполнении командлета, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="57c8a-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="57c8a-114">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="57c8a-114">Demonstrates</span></span>

<span data-ttu-id="57c8a-115">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="57c8a-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="57c8a-116">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="57c8a-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="57c8a-117">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="57c8a-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="57c8a-118">Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="57c8a-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="57c8a-119">Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="57c8a-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="57c8a-120">Элемент [Label](./label-element-for-listitem-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="57c8a-120">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="57c8a-121">Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.</span><span class="sxs-lookup"><span data-stu-id="57c8a-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="57c8a-122">Пример</span><span class="sxs-lookup"><span data-stu-id="57c8a-122">Example</span></span>

<span data-ttu-id="57c8a-123">Следующий XML-код определяет представление списка, в каждой строке которого отображается пользовательская метка.</span><span class="sxs-lookup"><span data-stu-id="57c8a-123">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="57c8a-124">В этом случае метка содержит имя свойства с каждой буквой в прописной буквы и словом "свойство".</span><span class="sxs-lookup"><span data-stu-id="57c8a-124">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="57c8a-125">В каждой строке отображается имя свойства, за которым следует значение свойства.</span><span class="sxs-lookup"><span data-stu-id="57c8a-125">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
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
            <Label>NAME property</Label>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <Label>DISPLAYNAME property</Label>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <Label>STATUS property</Label>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <Label>SERVICETYPE property</Label>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>

  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="57c8a-126">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="57c8a-126">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
NAME property        : Fax
DISPLAYNAME property : Fax
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FCSAM
DISPLAYNAME property : Microsoft Antimalware Service
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : fdPHost
DISPLAYNAME property : Function Discovery Provider Host
STATUS property      : Stopped
SERVICETYPE property : Win32ShareProcess

NAME property        : FDResPub
DISPLAYNAME property : Function Discovery Resource Publication
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache
DISPLAYNAME property : Windows Font Cache Service
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache3.0.0.0
DISPLAYNAME property : Windows Presentation Foundation Font Cache 3.0.0.0
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FSysAgent
DISPLAYNAME property : Microsoft Forefront System Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : FwcAgent
DISPLAYNAME property : Firewall Client Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="57c8a-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="57c8a-127">See Also</span></span>

[<span data-ttu-id="57c8a-128">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="57c8a-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="57c8a-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="57c8a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
