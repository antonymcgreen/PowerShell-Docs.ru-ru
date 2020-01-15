---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Повторение задачи для нескольких объектов (ForEach-Object)
ms.openlocfilehash: bf89070fd9b006fa9b0b262ab63ffadd81072ecc
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736885"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a>Повторение задачи для нескольких объектов (ForEach-Object)

Командлет `ForEach-Object` использует блоки сценариев и дескриптор `$_` текущего объекта конвейера, чтобы вы могли выполнить команду для каждого объекта в конвейере. Это можно использовать для выполнения некоторых сложных задач.

Одним из случаев, где это может пригодиться, является обработка данных, делающая их более полезными. Например, класс **Win32_LogicalDisk** из инструментария WMI можно использовать для возврата сведений о свободном пространстве на каждом локальном диске. Данные возвращаются в виде байтов, что затрудняет их восприятие:

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

Значение **FreeSpace** можно преобразовать в мегабайты, разделив каждое значение на 1 МБ. Это можно сделать в блоке сценария `ForEach-Object`, введя следующее:

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

К сожалению, в результате получаются данные без соответствующей метки. Так как свойства инструментария WMI, такие как это, доступны только для чтения, непосредственное преобразование **FreeSpace** невозможно. Если ввести следующее:

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

Отображается сообщение об ошибке:

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

Вы можете реорганизовать данные с помощью некоторых усовершенствованных методик, однако проще создать объект с помощью `Select-Object`.
