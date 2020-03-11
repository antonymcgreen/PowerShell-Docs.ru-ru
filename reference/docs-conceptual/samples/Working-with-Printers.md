---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Работа с принтерами
ms.openlocfilehash: 1d6b9a57ec61f06af694757dc8017d50b4dd40fe
ms.sourcegitcommit: 1fa89ab20d14a61f139f1394c45aaedd5a7c5438
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2020
ms.locfileid: "78935214"
---
# <a name="working-with-printers-in-windows"></a>Работа с принтерами в Windows

PowerShell можно использовать для управления принтерами с помощью инструментария WMI и COM-объекта **WScript.Network** с сервера сценариев Windows. Мы будем использовать сочетание обоих средств, чтобы продемонстрировать выполнение конкретных задач.

## <a name="listing-printer-connections"></a>Вывод подключений принтеров

Самый простой способ вывести список принтеров, установленных на компьютере, — использовать класс **Win32_Printer** инструментария WMI.

```powershell
Get-CimInstance -Class Win32_Printer
```

Список принтеров можно также вывести с помощью COM-объекта **WScript.Network**, который обычно используется в сценариях сервера сценариев Windows:

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

Поскольку эта команда возвращает простую коллекцию строк из имен портов и принтеров без отличительных меток, ее непросто интерпретировать.

## <a name="adding-a-network-printer"></a>Добавление сетевого принтера

Чтобы добавить сетевой принтер, используйте **WScript.Network**:

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a>Установка принтера по умолчанию

Чтобы задать принтер по умолчанию с помощью инструментария WMI, найдите принтер в коллекции **Win32_Printer**, а затем вызовите метод **SetDefaultPrinter**.

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

**WScript.Network** немного проще в использовании, так как содержит метод **SetDefaultPrinter**, который принимает в качестве аргумента только имя принтера:

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a>Удаление подключения принтера

Чтобы удалить подключение принтера, используйте метод **WScript.Network RemovePrinterConnection**:

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
