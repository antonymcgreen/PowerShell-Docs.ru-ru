---
title: Расширенное представление (Basic) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9abb63b8-6d02-4e24-9c0e-2d15a04e9051
caps.latest.revision: 8
ms.openlocfilehash: 7a36f548a3eccdf2c9cad04a8bfe28bf4e8d6dfd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367943"
---
# <a name="wide-view-basic"></a><span data-ttu-id="fcb9c-102">Широкое представление (базовое)</span><span class="sxs-lookup"><span data-stu-id="fcb9c-102">Wide View (Basic)</span></span>

<span data-ttu-id="fcb9c-103">В этом примере показано, как реализовать базовое представление, которое отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемое командлетом `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-103">This example shows how to implement a basic wide view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="fcb9c-104">Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="fcb9c-104">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="fcb9c-105">Загрузка этого файла форматирования</span><span class="sxs-lookup"><span data-stu-id="fcb9c-105">To load this formatting file</span></span>

1. <span data-ttu-id="fcb9c-106">Скопируйте XML-код из раздела "пример" этого раздела в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-106">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="fcb9c-107">Сохраните текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-107">Save the text file.</span></span> <span data-ttu-id="fcb9c-108">Не забудьте добавить расширение `format.ps1xml` в файл, чтобы обозначить его как файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-108">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="fcb9c-109">Откройте Windows PowerShell и выполните следующую команду, чтобы загрузить файл форматирования в текущий сеанс: `Update-formatdata -prependpath PathToFormattingFile`.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-109">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="fcb9c-110">Этот файл форматирования определяет отображение объекта, который уже определен файлом форматирования Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-110">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="fcb9c-111">При выполнении командлета необходимо использовать параметр `prependPath`, и этот файл форматирования нельзя загрузить как модуль.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-111">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="fcb9c-112">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="fcb9c-112">Demonstrates</span></span>

<span data-ttu-id="fcb9c-113">В этом файле форматирования показаны следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="fcb9c-113">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="fcb9c-114">Элемент [Name](./name-element-for-view-format.md) для представления.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-114">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="fcb9c-115">Элемент [виевселектедби](./viewselectedby-element-format.md) , который определяет, какие объекты отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-115">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="fcb9c-116">Элемент [видеитем](./wideitem-element-for-widecontrol-format.md) , определяющий свойство, отображаемое представлением.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-116">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="fcb9c-117">Пример</span><span class="sxs-lookup"><span data-stu-id="fcb9c-117">Example</span></span>

<span data-ttu-id="fcb9c-118">Следующий XML-код определяет расширенное представление, которое отображает значение свойства [System. ServiceProcess. ServiceController. ServiceName](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) .</span><span class="sxs-lookup"><span data-stu-id="fcb9c-118">The following XML defines a wide view that displays the value of the [System.Serviceprocess.Servicecontroller.Servicename](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) property.</span></span>

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

<span data-ttu-id="fcb9c-119">В следующем примере показано, как Windows PowerShell отображает [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) объекты после загрузки этого файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="fcb9c-119">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="fcb9c-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcb9c-120">See Also</span></span>

[<span data-ttu-id="fcb9c-121">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="fcb9c-121">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="fcb9c-122">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcb9c-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
