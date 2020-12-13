---
ms.date: 09/13/2016
ms.topic: reference
title: Представление списка (базовое)
description: Представление списка (базовое)
ms.openlocfilehash: d80ac9c6143b976d8bc13e2b184e4f5a2f8a37ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666643"
---
# <a name="list-view-basic"></a><span data-ttu-id="8035c-103">Представление списка (базовое)</span><span class="sxs-lookup"><span data-stu-id="8035c-103">List View (Basic)</span></span>

<span data-ttu-id="8035c-104">В этом примере показано, как реализовать базовое представление списка, в котором отображается [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые командлетом [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="8035c-104">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="8035c-105">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="8035c-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="8035c-106">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="8035c-106">To load this formatting file</span></span>

1. <span data-ttu-id="8035c-107">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="8035c-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="8035c-108">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="8035c-108">Save the text file.</span></span> <span data-ttu-id="8035c-109">Не забудьте добавить `format.ps1xml` расширение в файл, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="8035c-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="8035c-110">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="8035c-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="8035c-111">Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8035c-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="8035c-112">Этот параметр необходимо использовать `prependPath` при выполнении командлета, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="8035c-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8035c-113">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="8035c-113">Demonstrates</span></span>

<span data-ttu-id="8035c-114">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="8035c-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="8035c-115">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="8035c-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="8035c-116">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="8035c-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="8035c-117">Элемент [ListControl](./listcontrol-element-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="8035c-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="8035c-118">Элемент [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) , который определяет, что отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="8035c-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="8035c-119">Элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) , определяющий отображаемое свойство.</span><span class="sxs-lookup"><span data-stu-id="8035c-119">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="8035c-120">Пример</span><span class="sxs-lookup"><span data-stu-id="8035c-120">Example</span></span>

<span data-ttu-id="8035c-121">Следующий XML-код определяет представление списка, в котором отображаются четыре свойства элемента [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , объект.</span><span class="sxs-lookup"><span data-stu-id="8035c-121">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="8035c-122">В каждой строке отображается имя свойства, за которым следует значение свойства.</span><span class="sxs-lookup"><span data-stu-id="8035c-122">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
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
</Configuration>
```

<span data-ttu-id="8035c-123">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="8035c-123">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Name        : Fax
DisplayName : Fax
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
Status      : Running
ServiceType : Win32OwnProcess

Name        : fdPHost
DisplayName : Function Discovery Provider Host
Status      : Stopped
ServiceType : Win32ShareProcess

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
Status      : Running
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
Status      : Running
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="8035c-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="8035c-124">See Also</span></span>

[<span data-ttu-id="8035c-125">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="8035c-125">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="8035c-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8035c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
