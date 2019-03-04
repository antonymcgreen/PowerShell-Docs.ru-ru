---
title: Представление (метки) списка | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53442bb1-74a3-49f9-9150-3bc3081a7565
caps.latest.revision: 6
ms.openlocfilehash: 2bb62ab3e4fa1db9b3af8c82eb9035aa4f3e31c0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860130"
---
# <a name="list-view-labels"></a><span data-ttu-id="9b5ab-102">Представление списка (метки)</span><span class="sxs-lookup"><span data-stu-id="9b5ab-102">List View (Labels)</span></span>

<span data-ttu-id="9b5ab-103">В этом примере показано, как реализовать пользовательскую метку для каждой строки списка отображаются: представление списка.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-103">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="9b5ab-104">Это представление списка отображает свойства [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объект, возвращаемый [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="9b5ab-105">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9b5ab-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>
<span data-ttu-id="9b5ab-106">В этом примере показано, как реализовать пользовательскую метку для каждой строки списка отображаются: представление списка.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-106">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="9b5ab-107">Это представление списка отображает свойства [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объект, возвращаемый [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) командлета.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-107">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="9b5ab-108">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9b5ab-108">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="9b5ab-109">Для загрузки этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="9b5ab-109">To load this formatting file</span></span>

1. <span data-ttu-id="9b5ab-110">Скопируйте XML-код из примера в разделе этой статьи, в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-110">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="9b5ab-111">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-111">Save the text file.</span></span> <span data-ttu-id="9b5ab-112">Не забудьте добавить `format.ps1xml` расширения в файл, чтобы он определялся как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-112">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="9b5ab-113">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущем сеансе: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-113">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="9b5ab-114">Этот файл форматирования определяют способ отображения объекта, который уже определен в файле форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-114">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="9b5ab-115">Необходимо использовать `prependPath` параметра при выполнении командлета, а не удается загрузить это форматирование файла как модуль.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-115">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="9b5ab-116">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="9b5ab-116">Demonstrates</span></span>

<span data-ttu-id="9b5ab-117">Этот файл форматирования показаны следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="9b5ab-117">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="9b5ab-118">[Имя](./name-element-for-view-format.md) элемент для представления.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-118">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="9b5ab-119">[ViewSelectedBy](./viewselectedby-element-format.md) элемент, который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="9b5ab-120">[ListControl](./listcontrol-element-format.md) элемент, который определяет, какое свойство отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-120">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="9b5ab-121">[ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) элемент, который определяет, что отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-121">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="9b5ab-122">[Метка](./label-element-for-listitem-for-listcontrol-format.md) элемент, который определяет, что отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-122">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="9b5ab-123">[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) элемент, который определяет, какое свойство отображается.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-123">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="9b5ab-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9b5ab-124">Example</span></span>

<span data-ttu-id="9b5ab-125">Следующий код XML определяет представления списка, отображает пользовательскую метку в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-125">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="9b5ab-126">В этом случае метка включает в себя имя свойства с каждой буквы и слово «property».</span><span class="sxs-lookup"><span data-stu-id="9b5ab-126">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="9b5ab-127">В каждой строке отображается имя свойства со следующим значением свойства.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-127">In each row, the name of the property is displayed followed by the value of the property.</span></span>

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

<span data-ttu-id="9b5ab-128">В следующем примере показано, как Windows PowerShell отображает [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объектов после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="9b5ab-128">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9b5ab-129">См. также</span><span class="sxs-lookup"><span data-stu-id="9b5ab-129">See Also</span></span>

[<span data-ttu-id="9b5ab-130">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="9b5ab-130">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="9b5ab-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b5ab-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
