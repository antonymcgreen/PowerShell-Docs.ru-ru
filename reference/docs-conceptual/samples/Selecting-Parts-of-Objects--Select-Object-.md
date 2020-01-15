---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Выбор частей объектов (Select-Object)
ms.openlocfilehash: 06b92c7c4c5098c707a7d9f9d9a96e6b6a897f80
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737174"
---
# <a name="selecting-parts-of-objects-select-object"></a>Выбор частей объектов (Select-Object)

Командлет `Select-Object` позволяет создавать новые пользовательские объекты PowerShell со свойствами, выбранными из объектов, которые используются для их создания. Введите следующую команду, чтобы создать объект, который содержит только свойства **Name** и **FreeSpace** класса WMI **Win32_LogicalDisk**:

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
