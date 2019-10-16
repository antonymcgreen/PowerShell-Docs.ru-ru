---
title: Представление списка (GroupBy) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2e66c86-83a7-4148-8575-c28d6d429d4f
caps.latest.revision: 6
ms.openlocfilehash: c178c4a48f9595001bcc249d5f55886fa54bb9f2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365143"
---
# <a name="list-view-groupby"></a><span data-ttu-id="38a7c-102">Представление списка (с группировкой)</span><span class="sxs-lookup"><span data-stu-id="38a7c-102">List View (GroupBy)</span></span>

<span data-ttu-id="38a7c-103">В этом примере показано, как реализовать представление списка, которое разделяет строки списка на группы.</span><span class="sxs-lookup"><span data-stu-id="38a7c-103">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="38a7c-104">В этом представлении списка отображаются свойства [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые командлетом [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) .</span><span class="sxs-lookup"><span data-stu-id="38a7c-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="38a7c-105">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="38a7c-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="38a7c-106">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="38a7c-106">To load this formatting file</span></span>

1. <span data-ttu-id="38a7c-107">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="38a7c-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="38a7c-108">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="38a7c-108">Save the text file.</span></span> <span data-ttu-id="38a7c-109">Не забудьте добавить в файл расширение `format.ps1xml`, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="38a7c-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="38a7c-110">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="38a7c-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="38a7c-111">Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38a7c-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="38a7c-112">При выполнении командлета необходимо использовать параметр `prependPath`, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="38a7c-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="38a7c-113">Демонстрирующее</span><span class="sxs-lookup"><span data-stu-id="38a7c-113">Demonstrates</span></span>

<span data-ttu-id="38a7c-114">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="38a7c-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="38a7c-115">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="38a7c-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="38a7c-116">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="38a7c-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="38a7c-117">Элемент [GroupBy](./viewselectedby-element-format.md) , определяющий, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="38a7c-117">The [GroupBy](./viewselectedby-element-format.md) element that defines how a new group of objects is displayed.</span></span>

- <span data-ttu-id="38a7c-118">Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="38a7c-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="38a7c-119">Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="38a7c-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="38a7c-120">Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.</span><span class="sxs-lookup"><span data-stu-id="38a7c-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="38a7c-121">Пример</span><span class="sxs-lookup"><span data-stu-id="38a7c-121">Example</span></span>

<span data-ttu-id="38a7c-122">Следующий XML-код определяет представление списка, которое запускает новую группу всякий раз, когда изменяется значение свойства [System. ServiceProcess. ServiceController. status](/dotnet/api/System.ServiceProcess.ServiceController.Status) .</span><span class="sxs-lookup"><span data-stu-id="38a7c-122">The following XML defines a list view that starts a new group whenever the value of the [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) property changes.</span></span> <span data-ttu-id="38a7c-123">При запуске каждой группы отображается пользовательская метка, которая содержит новое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="38a7c-123">When each group is started, a custom label is displayed that includes the new value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
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

<span data-ttu-id="38a7c-124">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="38a7c-124">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span> <span data-ttu-id="38a7c-125">Windows PowerShell автоматически добавляет пустые строки, добавленные до и после метки группы.</span><span class="sxs-lookup"><span data-stu-id="38a7c-125">The blank lines added before and after the group label are automatically added by Windows PowerShell.</span></span>

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="38a7c-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="38a7c-126">See Also</span></span>

[<span data-ttu-id="38a7c-127">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="38a7c-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="38a7c-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="38a7c-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)