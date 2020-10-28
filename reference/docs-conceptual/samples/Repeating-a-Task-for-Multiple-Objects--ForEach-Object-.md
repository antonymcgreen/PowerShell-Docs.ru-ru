---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Повторение задачи для нескольких объектов (ForEach-Object)
description: Объект ForEach-Object позволяет повторять набор команд для каждого объекта, передаваемого по конвейеру.
ms.openlocfilehash: 7353be833dc8bf77dd18b7fc45bdd97e092ff6ef
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499963"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="92674-104">Повторение задачи для нескольких объектов (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="92674-104">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>

<span data-ttu-id="92674-105">Командлет `ForEach-Object` использует блоки сценариев и дескриптор `$_` текущего объекта конвейера, чтобы вы могли выполнить команду для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="92674-105">The `ForEach-Object` cmdlet uses script blocks and the `$_` descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="92674-106">Это можно использовать для выполнения некоторых сложных задач.</span><span class="sxs-lookup"><span data-stu-id="92674-106">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="92674-107">Одним из случаев, где это может пригодиться, является обработка данных, делающая их более полезными.</span><span class="sxs-lookup"><span data-stu-id="92674-107">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="92674-108">Например, класс **Win32_LogicalDisk** из инструментария WMI можно использовать для возврата сведений о свободном пространстве на каждом локальном диске.</span><span class="sxs-lookup"><span data-stu-id="92674-108">For example, the **Win32_LogicalDisk** class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="92674-109">Данные возвращаются в виде байтов, что затрудняет их восприятие:</span><span class="sxs-lookup"><span data-stu-id="92674-109">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

<span data-ttu-id="92674-110">Значение **FreeSpace** можно преобразовать в мегабайты, разделив каждое значение на 1 МБ.</span><span class="sxs-lookup"><span data-stu-id="92674-110">We can convert the **FreeSpace** value to megabytes by dividing each value by 1MB.</span></span> <span data-ttu-id="92674-111">Это можно сделать в блоке сценария `ForEach-Object`, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="92674-111">You can do that in a `ForEach-Object` script block by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

<span data-ttu-id="92674-112">К сожалению, в результате получаются данные без соответствующей метки.</span><span class="sxs-lookup"><span data-stu-id="92674-112">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="92674-113">Так как свойства инструментария WMI, такие как это, доступны только для чтения, непосредственное преобразование **FreeSpace** невозможно.</span><span class="sxs-lookup"><span data-stu-id="92674-113">Because WMI properties such as this are read-only, you cannot directly convert **FreeSpace** .</span></span> <span data-ttu-id="92674-114">Если ввести следующее:</span><span class="sxs-lookup"><span data-stu-id="92674-114">If you type this:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

<span data-ttu-id="92674-115">Отображается сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="92674-115">You get an error message:</span></span>

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

<span data-ttu-id="92674-116">Вы можете реорганизовать данные с помощью некоторых усовершенствованных методик, однако проще создать объект с помощью `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="92674-116">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using `Select-Object`.</span></span>
