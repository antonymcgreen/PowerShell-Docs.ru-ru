---
title: Представление (Basic) списка | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 918f381c-43e6-4594-a468-a40bfa8a16d6
caps.latest.revision: 7
ms.openlocfilehash: 1c683693c331ccfaf7355a0dd51801ed6fd39b3b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853310"
---
# <a name="list-view-basic"></a><span data-ttu-id="3fbca-102">Представление списка (базовое)</span><span class="sxs-lookup"><span data-stu-id="3fbca-102">List View (Basic)</span></span>

<span data-ttu-id="3fbca-103">В этом примере показано, как реализовать представление базовый список, отображающий [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объектов, возвращенных [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета.</span><span class="sxs-lookup"><span data-stu-id="3fbca-103">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="3fbca-104">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="3fbca-104">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>
<span data-ttu-id="3fbca-105">В этом примере показано, как реализовать представление базовый список, отображающий [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объектов, возвращенных [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета.</span><span class="sxs-lookup"><span data-stu-id="3fbca-105">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="3fbca-106">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="3fbca-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="3fbca-107">Для загрузки этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="3fbca-107">To load this formatting file</span></span>

1. <span data-ttu-id="3fbca-108">Скопируйте XML-код из примера в разделе этой статьи, в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3fbca-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="3fbca-109">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3fbca-109">Save the text file.</span></span> <span data-ttu-id="3fbca-110">Не забудьте добавить `format.ps1xml` расширения в файл, чтобы он определялся как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="3fbca-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="3fbca-111">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущем сеансе: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="3fbca-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="3fbca-112">Этот файл форматирования определяют способ отображения объекта, который уже определен в файле форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fbca-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="3fbca-113">Необходимо использовать `prependPath` параметра при выполнении командлета, а не удается загрузить это форматирование файла как модуль.</span><span class="sxs-lookup"><span data-stu-id="3fbca-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3fbca-114">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="3fbca-114">Demonstrates</span></span>

<span data-ttu-id="3fbca-115">Этот файл форматирования показаны следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="3fbca-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="3fbca-116">[Имя](./name-element-for-view-format.md) элемент для представления.</span><span class="sxs-lookup"><span data-stu-id="3fbca-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="3fbca-117">[ViewSelectedBy](./viewselectedby-element-format.md) элемент, который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="3fbca-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="3fbca-118">[ListControl](./listcontrol-element-format.md) элемент, который определяет, какое свойство отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="3fbca-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="3fbca-119">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) элемент, который определяет, что отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="3fbca-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="3fbca-120">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) элемент, который определяет, какое свойство отображается.</span><span class="sxs-lookup"><span data-stu-id="3fbca-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="3fbca-121">Пример</span><span class="sxs-lookup"><span data-stu-id="3fbca-121">Example</span></span>

<span data-ttu-id="3fbca-122">Следующий XML-код определяет представление списка, которое отображает четыре свойства [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="3fbca-122">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="3fbca-123">В каждой строке отображается имя свойства со следующим значением свойства.</span><span class="sxs-lookup"><span data-stu-id="3fbca-123">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="3fbca-124">В следующем примере показано, как Windows PowerShell отображает [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объектов после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="3fbca-124">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3fbca-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3fbca-125">See Also</span></span>

[<span data-ttu-id="3fbca-126">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="3fbca-126">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="3fbca-127">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fbca-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
