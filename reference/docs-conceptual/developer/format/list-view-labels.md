---
title: Представление списка (метки) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53442bb1-74a3-49f9-9150-3bc3081a7565
caps.latest.revision: 6
ms.openlocfilehash: 27de41c88e224f7610c10a764e51524016ecc8cb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362793"
---
# <a name="list-view-labels"></a><span data-ttu-id="72d87-102">Представление списка (метки)</span><span class="sxs-lookup"><span data-stu-id="72d87-102">List View (Labels)</span></span>

<span data-ttu-id="72d87-103">В этом примере показано, как реализовать представление списка, в котором отображается пользовательская метка для каждой строки списка.</span><span class="sxs-lookup"><span data-stu-id="72d87-103">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="72d87-104">В этом представлении списка отображаются свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемое командлетом [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) .</span><span class="sxs-lookup"><span data-stu-id="72d87-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="72d87-105">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="72d87-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="72d87-106">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="72d87-106">To load this formatting file</span></span>

1. <span data-ttu-id="72d87-107">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="72d87-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="72d87-108">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="72d87-108">Save the text file.</span></span> <span data-ttu-id="72d87-109">Не забудьте добавить в файл расширение `format.ps1xml`, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="72d87-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="72d87-110">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="72d87-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="72d87-111">Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72d87-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="72d87-112">При выполнении командлета необходимо использовать параметр `prependPath`, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="72d87-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="72d87-113">Демонстрирующее</span><span class="sxs-lookup"><span data-stu-id="72d87-113">Demonstrates</span></span>

<span data-ttu-id="72d87-114">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="72d87-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="72d87-115">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="72d87-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="72d87-116">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="72d87-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="72d87-117">Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="72d87-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="72d87-118">Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="72d87-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="72d87-119">Элемент [Label](./label-element-for-listitem-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="72d87-119">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="72d87-120">Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.</span><span class="sxs-lookup"><span data-stu-id="72d87-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="72d87-121">Пример</span><span class="sxs-lookup"><span data-stu-id="72d87-121">Example</span></span>

<span data-ttu-id="72d87-122">Следующий XML-код определяет представление списка, в каждой строке которого отображается пользовательская метка.</span><span class="sxs-lookup"><span data-stu-id="72d87-122">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="72d87-123">В этом случае метка содержит имя свойства с каждой буквой в прописной буквы и словом "свойство".</span><span class="sxs-lookup"><span data-stu-id="72d87-123">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="72d87-124">В каждой строке отображается имя свойства, за которым следует значение свойства.</span><span class="sxs-lookup"><span data-stu-id="72d87-124">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="72d87-125">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="72d87-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="72d87-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="72d87-126">See Also</span></span>

[<span data-ttu-id="72d87-127">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="72d87-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="72d87-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="72d87-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
