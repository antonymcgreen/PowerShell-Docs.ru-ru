---
title: Расширенное представление (GroupBy) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e53714f0b4240b5fe7f62cccda83af1e5badd33c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785002"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="4ffd1-102">Широкое представление (с группировкой)</span><span class="sxs-lookup"><span data-stu-id="4ffd1-102">Wide View (GroupBy)</span></span>

<span data-ttu-id="4ffd1-103">В этом примере показано, как реализовать широкое представление, отображающее группы [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые `Get-Service` командлетом.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-103">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="4ffd1-104">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="4ffd1-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="4ffd1-105">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="4ffd1-105">To load this formatting file</span></span>

1. <span data-ttu-id="4ffd1-106">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="4ffd1-107">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-107">Save the text file.</span></span> <span data-ttu-id="4ffd1-108">Не забудьте добавить `format.ps1xml` расширение в файл, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="4ffd1-109">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="4ffd1-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4ffd1-110">Этот файл форматирования определяет отображение объекта, который уже определен файлами форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="4ffd1-111">Этот параметр необходимо использовать `prependPath` при выполнении командлета, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4ffd1-112">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="4ffd1-112">Demonstrates</span></span>

<span data-ttu-id="4ffd1-113">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="4ffd1-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="4ffd1-114">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="4ffd1-115">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="4ffd1-116">Элемент [GroupBy](./groupby-element-for-view-format.md) , определяющий, когда отображается новая группа.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-116">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="4ffd1-117">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="4ffd1-118">Пример</span><span class="sxs-lookup"><span data-stu-id="4ffd1-118">Example</span></span>

<span data-ttu-id="4ffd1-119">Следующий XML-код определяет широкое представление, отображающее группы объектов.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-119">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="4ffd1-120">Каждая новая группа запускается при изменении значения свойства [System. ServiceProcess. ServiceController. serviceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) .</span><span class="sxs-lookup"><span data-stu-id="4ffd1-120">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

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

<span data-ttu-id="4ffd1-121">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="4ffd1-121">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4ffd1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4ffd1-122">See Also</span></span>

[<span data-ttu-id="4ffd1-123">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="4ffd1-123">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="4ffd1-124">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ffd1-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
