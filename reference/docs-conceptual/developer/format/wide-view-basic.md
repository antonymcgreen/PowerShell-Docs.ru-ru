---
ms.date: 09/13/2016
ms.topic: reference
title: Широкое представление (базовое)
description: Широкое представление (базовое)
ms.openlocfilehash: bfc647da9b78fcd22aac83cf330e466b6759471c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667697"
---
# <a name="wide-view-basic"></a><span data-ttu-id="29b1b-103">Широкое представление (базовое)</span><span class="sxs-lookup"><span data-stu-id="29b1b-103">Wide View (Basic)</span></span>

<span data-ttu-id="29b1b-104">В этом примере показано, как реализовать базовое представление, которое отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты, возвращаемые `Get-Service` командлетом.</span><span class="sxs-lookup"><span data-stu-id="29b1b-104">This example shows how to implement a basic wide view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="29b1b-105">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="29b1b-105">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="29b1b-106">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="29b1b-106">To load this formatting file</span></span>

1. <span data-ttu-id="29b1b-107">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="29b1b-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="29b1b-108">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="29b1b-108">Save the text file.</span></span> <span data-ttu-id="29b1b-109">Не забудьте добавить `format.ps1xml` расширение в файл, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="29b1b-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="29b1b-110">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="29b1b-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="29b1b-111">Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29b1b-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="29b1b-112">Этот параметр необходимо использовать `prependPath` при выполнении командлета, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="29b1b-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="29b1b-113">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="29b1b-113">Demonstrates</span></span>

<span data-ttu-id="29b1b-114">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="29b1b-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="29b1b-115">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="29b1b-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="29b1b-116">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="29b1b-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="29b1b-117">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="29b1b-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="29b1b-118">Пример</span><span class="sxs-lookup"><span data-stu-id="29b1b-118">Example</span></span>

<span data-ttu-id="29b1b-119">Следующий XML-код определяет расширенное представление, которое отображает значение свойства [System. ServiceProcess. ServiceController. ServiceName](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) .</span><span class="sxs-lookup"><span data-stu-id="29b1b-119">The following XML defines a wide view that displays the value of the [System.Serviceprocess.Servicecontroller.Servicename](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) property.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
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

<span data-ttu-id="29b1b-120">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="29b1b-120">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="29b1b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="29b1b-121">See Also</span></span>

[<span data-ttu-id="29b1b-122">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="29b1b-122">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="29b1b-123">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="29b1b-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
