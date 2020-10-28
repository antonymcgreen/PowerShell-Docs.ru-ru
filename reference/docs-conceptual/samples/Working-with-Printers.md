---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Работа с принтерами
description: В этой статье описывается, как управлять принтерами в Windows с помощью объектов WMI и COM-интерфейсов.
ms.openlocfilehash: 2606753783043eeae8e9d461e56f0901149cb8e3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501088"
---
# <a name="working-with-printers-in-windows"></a><span data-ttu-id="43665-104">Работа с принтерами в Windows</span><span class="sxs-lookup"><span data-stu-id="43665-104">Working with Printers in Windows</span></span>

<span data-ttu-id="43665-105">PowerShell можно использовать для управления принтерами с помощью инструментария WMI и COM-объекта **WScript.Network** с сервера сценариев Windows.</span><span class="sxs-lookup"><span data-stu-id="43665-105">You can use PowerShell to manage printers by using WMI and the **WScript.Network** COM object from WSH.</span></span> <span data-ttu-id="43665-106">Мы будем использовать сочетание обоих средств, чтобы продемонстрировать выполнение конкретных задач.</span><span class="sxs-lookup"><span data-stu-id="43665-106">We will use a mix of both tools to demonstrate specific tasks.</span></span>

## <a name="listing-printer-connections"></a><span data-ttu-id="43665-107">Вывод подключений принтеров</span><span class="sxs-lookup"><span data-stu-id="43665-107">Listing Printer Connections</span></span>

<span data-ttu-id="43665-108">Самый простой способ вывести список принтеров, установленных на компьютере, — использовать класс **Win32_Printer** инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="43665-108">The simplest way to list the printers installed on a computer is to use the WMI **Win32_Printer** class:</span></span>

```powershell
Get-CimInstance -Class Win32_Printer
```

<span data-ttu-id="43665-109">Список принтеров можно также вывести с помощью COM-объекта **WScript.Network** , который обычно используется в сценариях сервера сценариев Windows:</span><span class="sxs-lookup"><span data-stu-id="43665-109">You can also list the printers by using the **WScript.Network** COM object that is typically used in WSH scripts:</span></span>

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

<span data-ttu-id="43665-110">Поскольку эта команда возвращает простую коллекцию строк из имен портов и принтеров без отличительных меток, ее непросто интерпретировать.</span><span class="sxs-lookup"><span data-stu-id="43665-110">Because this command returns a simple string collection of port names and printer device names without any distinguishing labels, it is not easy to interpret.</span></span>

## <a name="adding-a-network-printer"></a><span data-ttu-id="43665-111">Добавление сетевого принтера</span><span class="sxs-lookup"><span data-stu-id="43665-111">Adding a Network Printer</span></span>

<span data-ttu-id="43665-112">Чтобы добавить сетевой принтер, используйте **WScript.Network** :</span><span class="sxs-lookup"><span data-stu-id="43665-112">To add a new network printer, use **WScript.Network** :</span></span>

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a><span data-ttu-id="43665-113">Установка принтера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="43665-113">Setting a Default Printer</span></span>

<span data-ttu-id="43665-114">Чтобы задать принтер по умолчанию с помощью инструментария WMI, найдите принтер в коллекции **Win32_Printer** , а затем вызовите метод **SetDefaultPrinter** .</span><span class="sxs-lookup"><span data-stu-id="43665-114">To use WMI to set the default printer, find the printer in the **Win32_Printer** collection and then invoke the **SetDefaultPrinter** method:</span></span>

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

<span data-ttu-id="43665-115">**WScript.Network** немного проще в использовании, так как содержит метод **SetDefaultPrinter** , который принимает в качестве аргумента только имя принтера:</span><span class="sxs-lookup"><span data-stu-id="43665-115">**WScript.Network** is a little simpler to use, because it has a **SetDefaultPrinter** method that takes only the printer name as an argument:</span></span>

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a><span data-ttu-id="43665-116">Удаление подключения принтера</span><span class="sxs-lookup"><span data-stu-id="43665-116">Removing a Printer Connection</span></span>

<span data-ttu-id="43665-117">Чтобы удалить подключение принтера, используйте метод **WScript.Network RemovePrinterConnection** :</span><span class="sxs-lookup"><span data-stu-id="43665-117">To remove a printer connection, use the **WScript.Network RemovePrinterConnection** method:</span></span>

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
