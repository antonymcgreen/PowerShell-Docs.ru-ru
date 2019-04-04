---
ms.date: 08/23/2018
keywords: powershell,командлет
title: Принцип работы конвейеров PowerShell
ms.assetid: 6be50926-7943-4ef7-9499-4490d72a63fb
ms.openlocfilehash: 05ab98b7261f4d41ade1788a924193eccda6318c
ms.sourcegitcommit: f268dce5b5e72be669be0c6634b8db11369bbae2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58623965"
---
# <a name="understanding-pipelines"></a><span data-ttu-id="64bbe-103">Принцип работы конвейеров</span><span class="sxs-lookup"><span data-stu-id="64bbe-103">Understanding pipelines</span></span>

<span data-ttu-id="64bbe-104">Конвейеры представляют собой последовательность соединенных сегментов канала.</span><span class="sxs-lookup"><span data-stu-id="64bbe-104">Pipelines act like a series of connected segments of pipe.</span></span> <span data-ttu-id="64bbe-105">Элементы, перемещающиеся по конвейеру, проходят через каждый сегмент.</span><span class="sxs-lookup"><span data-stu-id="64bbe-105">Items moving along the pipeline pass through each segment.</span></span> <span data-ttu-id="64bbe-106">Для создания конвейера в PowerShell команды соединяются друг с другом с помощью оператора канала |.</span><span class="sxs-lookup"><span data-stu-id="64bbe-106">To create a pipeline in PowerShell, you connect commands together with the pipe operator "|".</span></span> <span data-ttu-id="64bbe-107">Результат каждой команды используется в качестве входных данных для следующей.</span><span class="sxs-lookup"><span data-stu-id="64bbe-107">The output of each command is used as input to the next command.</span></span>

<span data-ttu-id="64bbe-108">Эта нотация конвейера похожа на нотацию, которая используется в других оболочках.</span><span class="sxs-lookup"><span data-stu-id="64bbe-108">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="64bbe-109">На первый взгляд не совсем понятно, чем отличаются конвейеры в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64bbe-109">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="64bbe-110">Хотя вы видите на экране текст, PowerShell передает по конвейеру между командами не текст, а объекты.</span><span class="sxs-lookup"><span data-stu-id="64bbe-110">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

## <a name="the-powershell-pipeline"></a><span data-ttu-id="64bbe-111">Конвейер PowerShell</span><span class="sxs-lookup"><span data-stu-id="64bbe-111">The PowerShell pipeline</span></span>

<span data-ttu-id="64bbe-112">Пожалуй, конвейеры являются наиболее полезной концепцией в интерфейсах командной строки.</span><span class="sxs-lookup"><span data-stu-id="64bbe-112">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="64bbe-113">При правильном использовании конвейеры упрощают как обработку сложных команд, так и отслеживание потока их выполнения.</span><span class="sxs-lookup"><span data-stu-id="64bbe-113">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work for the commands.</span></span> <span data-ttu-id="64bbe-114">Каждая команда в конвейере (которая называется элементом конвейера) обычно поочередно передает свои выходные данные в следующую команду конвейера в виде объектов.</span><span class="sxs-lookup"><span data-stu-id="64bbe-114">Each command in a pipeline (called a pipeline element) passes its output to the next command in the pipeline, item-by-item.</span></span> <span data-ttu-id="64bbe-115">Команды обрабатывают только один объект за раз.</span><span class="sxs-lookup"><span data-stu-id="64bbe-115">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="64bbe-116">Это снижает потребление ресурсов и позволяет сразу же получать выходные данные.</span><span class="sxs-lookup"><span data-stu-id="64bbe-116">The result is reduced resource consumption and the ability to begin getting the output immediately.</span></span>

<span data-ttu-id="64bbe-117">Например, вы можете использовать командлет `Out-Host` для принудительного постраничного отображения выходных данных из другой команды. На экране эти данные будут показаны как обычный текст, разбитый на страницы:</span><span class="sxs-lookup"><span data-stu-id="64bbe-117">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem -Path C:\WINDOWS\System32 | Out-Host -Paging
```

```Output
    Directory: C:\WINDOWS\system32

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/12/2018   2:15 AM                0409
d-----        5/13/2018  11:31 PM                1033
d-----        4/11/2018   4:38 PM                AdvancedInstallers
d-----        5/13/2018  11:13 PM                af-ZA
d-----        5/13/2018  11:13 PM                am-et
d-----        4/11/2018   4:38 PM                AppLocker
d-----        5/13/2018  11:31 PM                appmgmt
d-----        7/11/2018   2:05 AM                appraiser
d---s-        4/12/2018   2:20 AM                AppV
d-----        5/13/2018  11:10 PM                ar-SA
d-----        5/13/2018  11:13 PM                as-IN
d-----        8/14/2018   9:03 PM                az-Latn-AZ
d-----        5/13/2018  11:13 PM                be-BY
d-----        5/13/2018  11:10 PM                BestPractices
d-----        5/13/2018  11:10 PM                bg-BG
d-----        5/13/2018  11:13 PM                bn-BD
d-----        5/13/2018  11:13 PM                bn-IN
d-----        8/14/2018   9:03 PM                Boot
d-----        8/14/2018   9:03 PM                bs-Latn-BA
d-----        4/11/2018   4:38 PM                Bthprops
d-----        4/12/2018   2:19 AM                ca-ES
d-----        8/14/2018   9:03 PM                ca-ES-valencia
d-----        5/13/2018  10:46 PM                CatRoot
d-----        8/23/2018   5:07 PM                catroot2
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="64bbe-118">Разбиение на страницы также снижает потребление ресурсов ЦП, так обработку продолжает командлет `Out-Host`, когда он получает всю страницу для отображения.</span><span class="sxs-lookup"><span data-stu-id="64bbe-118">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="64bbe-119">Командлет, стоящий в конвейере выше, приостанавливает выполнение, пока не будет готова следующая страница выходных данных.</span><span class="sxs-lookup"><span data-stu-id="64bbe-119">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

<span data-ttu-id="64bbe-120">Разницу можно увидеть в диспетчере задач Windows, отслеживая ресурсы ЦП и памяти, используемые PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64bbe-120">You can see the difference Windows Task Manager to monitor CPU and memory used by PowerShell.</span></span> <span data-ttu-id="64bbe-121">Выполните следующую команду: `Get-ChildItem C:\Windows -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="64bbe-121">Run the following command: `Get-ChildItem C:\Windows -Recurse`.</span></span> <span data-ttu-id="64bbe-122">Сравните использование ресурсов ЦП и памяти с помощью этой команды: `Get-ChildItem C:\Windows -Recurse | Out-Host -Paging`.</span><span class="sxs-lookup"><span data-stu-id="64bbe-122">Compare the CPU and memory usage to this command: `Get-ChildItem C:\Windows -Recurse | Out-Host -Paging`.</span></span>

> [!NOTE]
> <span data-ttu-id="64bbe-123">Параметр **Разбиение по страницам** поддерживается не всеми узлами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64bbe-123">The **Paging** parameter is not supported by all PowerShell hosts.</span></span> <span data-ttu-id="64bbe-124">Например, при попытке использовать параметр **Разбиение по страницам** в интегрированной среде скриптов PowerShell, вы увидите следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="64bbe-124">For example, when you try to use the **Paging** parameter in the PowerShell ISE, you see the following error:</span></span>
>
> ```Output
> out-lineoutput : The method or operation is not implemented.
> At line:1 char:1
> + Get-ChildItem C:\Windows -Recurse | Out-Host -Paging
> + ~~~~~~~~~~~~~~~~~~~~~~~~~~~
>     + CategoryInfo          : NotSpecified: (:) [out-lineoutput], NotImplementedException
>     + FullyQualifiedErrorId : System.NotImplementedException,Microsoft.PowerShell.Commands.OutLineOutputCommand
> ```

## <a name="objects-in-the-pipeline"></a><span data-ttu-id="64bbe-125">Объекты в конвейере</span><span class="sxs-lookup"><span data-stu-id="64bbe-125">Objects in the pipeline</span></span>

<span data-ttu-id="64bbe-126">При запуске командлета в PowerShell вы видите выходные данные в виде текста — именно так в окне консоли и должны отображаться объекты.</span><span class="sxs-lookup"><span data-stu-id="64bbe-126">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="64bbe-127">В текстовом представлении могут отображаться не все свойства выводимого объекта.</span><span class="sxs-lookup"><span data-stu-id="64bbe-127">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="64bbe-128">Например, рассмотрим командлет `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="64bbe-128">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="64bbe-129">Если запустить `Get-Location` в корневой папке диска C (ваше текущее расположение), вы увидите следующий результат:</span><span class="sxs-lookup"><span data-stu-id="64bbe-129">If you run `Get-Location` while your current location is the root of the C drive, you see the following output:</span></span>

```
PS> Get-Location

Path
----
C:\
```

<span data-ttu-id="64bbe-130">Эти выходные данные в виде текста содержат сводную информацию, а не полное представление объекта, возвращаемого командлетом `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="64bbe-130">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="64bbe-131">Процесс, который форматирует данные для отображения на экране, добавляет к выходным данным заголовок.</span><span class="sxs-lookup"><span data-stu-id="64bbe-131">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

<span data-ttu-id="64bbe-132">При передаче выходных данных по конвейеру в командлет `Get-Member` вы получите информацию об объекте, возвращаемом командлетом `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="64bbe-132">When you pipe the output to the `Get-Member` cmdlet you get information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="64bbe-133">Командлет `Get-Location` возвращает объект **PathInfo**, который содержит текущий путь и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="64bbe-133">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>
