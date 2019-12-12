---
title: Расширенное представление (GroupBy) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39388197-4ff9-4889-aa32-526011afa1f6
caps.latest.revision: 6
ms.openlocfilehash: e95ec550a7815a76a8bd7f9526dfa405a9644360
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367953"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="a7758-102">Широкое представление (с группировкой)</span><span class="sxs-lookup"><span data-stu-id="a7758-102">Wide View (GroupBy)</span></span>

<span data-ttu-id="a7758-103">В этом примере показано, как реализовать широкое представление, отображающее группы [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемое командлетом `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="a7758-103">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="a7758-104">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a7758-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="a7758-105">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="a7758-105">To load this formatting file</span></span>

1. <span data-ttu-id="a7758-106">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="a7758-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="a7758-107">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="a7758-107">Save the text file.</span></span> <span data-ttu-id="a7758-108">Не забудьте добавить расширение `format.ps1xml` в файл, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="a7758-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="a7758-109">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="a7758-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="a7758-110">Этот файл форматирования определяет отображение объекта, который уже определен файлами форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7758-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="a7758-111">При выполнении командлета необходимо использовать параметр `prependPath`, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="a7758-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a7758-112">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="a7758-112">Demonstrates</span></span>

<span data-ttu-id="a7758-113">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="a7758-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="a7758-114">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="a7758-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="a7758-115">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="a7758-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="a7758-116">Элемент [GroupBy](./groupby-element-for-view-format.md) , определяющий, когда отображается новая группа.</span><span class="sxs-lookup"><span data-stu-id="a7758-116">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="a7758-117">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="a7758-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="a7758-118">Пример</span><span class="sxs-lookup"><span data-stu-id="a7758-118">Example</span></span>

<span data-ttu-id="a7758-119">Следующий XML-код определяет широкое представление, отображающее группы объектов.</span><span class="sxs-lookup"><span data-stu-id="a7758-119">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="a7758-120">Каждая новая группа запускается при изменении значения свойства [System. ServiceProcess. ServiceController. serviceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) .</span><span class="sxs-lookup"><span data-stu-id="a7758-120">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <Label>Service Type</Label>
        <PropertyName>ServiceType</PropertyName>
      </GroupBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="a7758-121">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="a7758-121">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
   Service Type: Win32OwnProcess

Fax                             FCSAM

   Service Type: Win32ShareProcess

fdPHost                         FDResPub
FontCache

   Service Type: Win32OwnProcess

FontCache3.0.0.0                FSysAgent
FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="a7758-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7758-122">See Also</span></span>

[<span data-ttu-id="a7758-123">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="a7758-123">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="a7758-124">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7758-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
