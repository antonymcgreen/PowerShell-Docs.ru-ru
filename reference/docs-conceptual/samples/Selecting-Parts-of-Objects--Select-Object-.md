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
# <a name="selecting-parts-of-objects-select-object"></a>Выбор частей объектов (Select-Object)

Командлет `Select-Object` позволяет создавать новые пользовательские объекты PowerShell со свойствами, выбранными из объектов, которые используются для их создания. Введите следующую команду, чтобы создать объект, который содержит только свойства **Name** и **FreeSpace** класса WMI **Win32_LogicalDisk** :

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

С помощью `Select-Object` можно создавать вычисляемые свойства. Таким образом, можно отобразить значение **FreeSpace** в гигабайтах, а не в байтах.

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
