---
title: Широкое представление (GroupBy) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39388197-4ff9-4889-aa32-526011afa1f6
caps.latest.revision: 6
ms.openlocfilehash: e95ec550a7815a76a8bd7f9526dfa405a9644360
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083660"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="38c75-102">Широкое представление (с группировкой)</span><span class="sxs-lookup"><span data-stu-id="38c75-102">Wide View (GroupBy)</span></span>

<span data-ttu-id="38c75-103">В этом примере показано, как реализовать широкое представление, отображаются группы [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объектов, возвращенных `Get-Service` командлета.</span><span class="sxs-lookup"><span data-stu-id="38c75-103">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="38c75-104">Дополнительные сведения о компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="38c75-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="38c75-105">Для загрузки этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="38c75-105">To load this formatting file</span></span>

1. <span data-ttu-id="38c75-106">Скопируйте XML-код из примера в разделе этой статьи, в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="38c75-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="38c75-107">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="38c75-107">Save the text file.</span></span> <span data-ttu-id="38c75-108">Не забудьте добавить `format.ps1xml` расширения в файл, чтобы он определялся как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="38c75-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="38c75-109">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущем сеансе: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="38c75-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="38c75-110">Этот файл форматирования определяют способ отображения объекта, который уже определен файлов форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38c75-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="38c75-111">Необходимо использовать `prependPath` параметра при выполнении командлета, а не удается загрузить это форматирование файла как модуль.</span><span class="sxs-lookup"><span data-stu-id="38c75-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="38c75-112">Демонстрирует</span><span class="sxs-lookup"><span data-stu-id="38c75-112">Demonstrates</span></span>

<span data-ttu-id="38c75-113">Этот файл форматирования показаны следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="38c75-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="38c75-114">[Имя](./name-element-for-view-format.md) элемент для представления.</span><span class="sxs-lookup"><span data-stu-id="38c75-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="38c75-115">[ViewSelectedBy](./viewselectedby-element-format.md) элемент, который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="38c75-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="38c75-116">[GroupBy](./groupby-element-for-view-format.md) элемент, который определяет, при отображении новой группы.</span><span class="sxs-lookup"><span data-stu-id="38c75-116">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="38c75-117">[WideItem](./wideitem-element-for-widecontrol-format.md) элемент, который определяет, какое свойство отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="38c75-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="38c75-118">Пример</span><span class="sxs-lookup"><span data-stu-id="38c75-118">Example</span></span>

<span data-ttu-id="38c75-119">Следующий код XML определяет широкое представление, в которой отображаются группы объектов.</span><span class="sxs-lookup"><span data-stu-id="38c75-119">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="38c75-120">Каждой новой группы запускается при значение [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="38c75-120">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

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

<span data-ttu-id="38c75-121">В следующем примере показано, как Windows PowerShell отображает [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объектов после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="38c75-121">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="38c75-122">См. также</span><span class="sxs-lookup"><span data-stu-id="38c75-122">See Also</span></span>

[<span data-ttu-id="38c75-123">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="38c75-123">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="38c75-124">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="38c75-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
