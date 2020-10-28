---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Выбор частей объектов (Select-Object)
description: Командлет `Select-Object` позволяет создавать пользовательские объекты PowerShell со свойствами, выбранными из объектов в конвейере.
ms.openlocfilehash: 92635ac54ea1469739bcb228c5e9a0a8dbfc648b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501037"
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="f8305-104">Выбор частей объектов (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="f8305-104">Selecting Parts of Objects (Select-Object)</span></span>

<span data-ttu-id="f8305-105">Командлет `Select-Object` позволяет создавать новые пользовательские объекты PowerShell со свойствами, выбранными из объектов, которые используются для их создания.</span><span class="sxs-lookup"><span data-stu-id="f8305-105">You can use the `Select-Object` cmdlet to create new, custom PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="f8305-106">Введите следующую команду, чтобы создать объект, который содержит только свойства **Name** и **FreeSpace** класса WMI **Win32_LogicalDisk** :</span><span class="sxs-lookup"><span data-stu-id="f8305-106">Type the following command to create a new object that includes only the **Name** and **FreeSpace** properties of the **Win32_LogicalDisk** WMI class:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

<span data-ttu-id="f8305-107">С помощью `Select-Object` можно создавать вычисляемые свойства.</span><span class="sxs-lookup"><span data-stu-id="f8305-107">With `Select-Object` you can create calculated properties.</span></span> <span data-ttu-id="f8305-108">Таким образом, можно отобразить значение **FreeSpace** в гигабайтах, а не в байтах.</span><span class="sxs-lookup"><span data-stu-id="f8305-108">So you can display **FreeSpace** in gigabytes rather than bytes.</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  Select-Object -Property Name, @{
    label='FreeSpace'
    expression={($_.FreeSpace/1GB).ToString('F2')}
  }
```

```Output
Name    FreeSpace
----    ---------
C:      47.18
```
