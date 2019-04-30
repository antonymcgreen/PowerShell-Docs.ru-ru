---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Использование переменных для хранения объектов
ms.assetid: b1688d73-c173-491e-9ba6-6d0c1cc852de
ms.openlocfilehash: d166ec58dc658c1b134030c9a9592249ee40d4f5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086550"
---
# <a name="using-variables-to-store-objects"></a><span data-ttu-id="8328a-103">Использование переменных для хранения объектов</span><span class="sxs-lookup"><span data-stu-id="8328a-103">Using variables to store objects</span></span>

<span data-ttu-id="8328a-104">PowerShell работает с объектами.</span><span class="sxs-lookup"><span data-stu-id="8328a-104">PowerShell works with objects.</span></span> <span data-ttu-id="8328a-105">PowerShell позволяет создавать именованные объекты, которые называются переменными.</span><span class="sxs-lookup"><span data-stu-id="8328a-105">PowerShell lets you create named objects known as variables.</span></span>
<span data-ttu-id="8328a-106">Имена переменных могут включать символ подчеркивания и любые буквенно-цифровые символы.</span><span class="sxs-lookup"><span data-stu-id="8328a-106">Variable names can include the underscore character and any alphanumeric characters.</span></span> <span data-ttu-id="8328a-107">В PowerShell перед именем переменной всегда используется символ \$.</span><span class="sxs-lookup"><span data-stu-id="8328a-107">When used in PowerShell, a variable is always specified using the \$ character followed by variable name.</span></span>

## <a name="creating-a-variable"></a><span data-ttu-id="8328a-108">Создание переменной</span><span class="sxs-lookup"><span data-stu-id="8328a-108">Creating a variable</span></span>

<span data-ttu-id="8328a-109">Чтобы создать переменную, можно ввести для нее допустимое имя:</span><span class="sxs-lookup"><span data-stu-id="8328a-109">You can create a variable by typing a valid variable name:</span></span>

```
PS> $loc
PS>
```

<span data-ttu-id="8328a-110">Этот пример не возвращает результаты, так как для переменной `$loc` не задано значение.</span><span class="sxs-lookup"><span data-stu-id="8328a-110">This example returns no result because `$loc` doesn't have a value.</span></span> <span data-ttu-id="8328a-111">Создать переменную и присвоить ей значение можно в одном шаге.</span><span class="sxs-lookup"><span data-stu-id="8328a-111">You can create a variable and assign it a value in the same step.</span></span> <span data-ttu-id="8328a-112">PowerShell создает переменную, только если она не существует.</span><span class="sxs-lookup"><span data-stu-id="8328a-112">PowerShell only creates the variable if it doesn't exist.</span></span>
<span data-ttu-id="8328a-113">В противном случае используется существующая переменная, для которой задается нужное значение.</span><span class="sxs-lookup"><span data-stu-id="8328a-113">Otherwise, it assigns the specified value to the existing variable.</span></span> <span data-ttu-id="8328a-114">В следующем примере в переменной `$loc` хранятся сведения о текущем расположении:</span><span class="sxs-lookup"><span data-stu-id="8328a-114">The following example stores the current location in the variable `$loc`:</span></span>

```powershell
$loc = Get-Location
```

<span data-ttu-id="8328a-115">В PowerShell не отображаются выходные данные при вводе этой команды.</span><span class="sxs-lookup"><span data-stu-id="8328a-115">PowerShell displays no output when you type this command.</span></span> <span data-ttu-id="8328a-116">PowerShell отправляет выходные данные команды Get-Location в переменную `$loc`.</span><span class="sxs-lookup"><span data-stu-id="8328a-116">PowerShell sends the output of 'Get-Location' to `$loc`.</span></span> <span data-ttu-id="8328a-117">В PowerShell данные, которые не были назначены или перенаправлены, выводятся на экран.</span><span class="sxs-lookup"><span data-stu-id="8328a-117">In PowerShell, data that isn't assigned or redirected is sent to the screen.</span></span> <span data-ttu-id="8328a-118">Ввод переменной `$loc` показывает текущее расположение:</span><span class="sxs-lookup"><span data-stu-id="8328a-118">Typing `$loc` shows your current location:</span></span>

```
PS> $loc

Path
----
C:\temp
```

<span data-ttu-id="8328a-119">Команду `Get-Member` можно использовать для отображения сведений о содержимом переменных.</span><span class="sxs-lookup"><span data-stu-id="8328a-119">You can use `Get-Member` to display information about the contents of variables.</span></span> <span data-ttu-id="8328a-120">Команда `Get-Member` показывает, что `$loc` — это объект **PathInfo**, так же как и выходные данные команды `Get-Location`:</span><span class="sxs-lookup"><span data-stu-id="8328a-120">`Get-Member` shows you that `$loc` is a **PathInfo** object, just like the output from `Get-Location`:</span></span>

```powershell
PS> $loc | Get-Member -MemberType Property

   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   System.String Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {...
ProviderPath Property   System.String ProviderPath {get;}
```

## <a name="manipulating-variables"></a><span data-ttu-id="8328a-121">Работа с переменными</span><span class="sxs-lookup"><span data-stu-id="8328a-121">Manipulating variables</span></span>

<span data-ttu-id="8328a-122">PowerShell предоставляет несколько команд для работы с переменными.</span><span class="sxs-lookup"><span data-stu-id="8328a-122">PowerShell provides several commands to manipulate variables.</span></span> <span data-ttu-id="8328a-123">Полный список в удобочитаемой форме можно получить, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="8328a-123">You can see a complete listing in a readable form by typing:</span></span>

```powershell
Get-Command -Noun Variable | Format-Table -Property Name,Definition -AutoSize -Wrap
```

<span data-ttu-id="8328a-124">PowerShell также создает несколько системных переменных.</span><span class="sxs-lookup"><span data-stu-id="8328a-124">PowerShell also creates several system-defined variables.</span></span> <span data-ttu-id="8328a-125">Можно использовать командлет `Remove-Variable`, чтобы удалить из текущего сеанса все переменные, которыми PowerShell не управляет.</span><span class="sxs-lookup"><span data-stu-id="8328a-125">You can use the `Remove-Variable` cmdlet to remove variables, which are not controlled by PowerShell, from the current session.</span></span> <span data-ttu-id="8328a-126">Введите следующую команду для очистки всех переменных:</span><span class="sxs-lookup"><span data-stu-id="8328a-126">Type the following command to clear all variables:</span></span>

```powershell
Remove-Variable -Name * -Force -ErrorAction SilentlyContinue
```

<span data-ttu-id="8328a-127">После выполнения предыдущей команды командлет `Get-Variable` отображает системные переменные PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8328a-127">After running the previous command, the `Get-Variable` cmdlet shows the PowerShell system variables.</span></span>

<span data-ttu-id="8328a-128">PowerShell также создает диск переменных.</span><span class="sxs-lookup"><span data-stu-id="8328a-128">PowerShell also creates a variable drive.</span></span> <span data-ttu-id="8328a-129">Чтобы отобразить все переменные PowerShell с помощью диска переменных, используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="8328a-129">Use the following example to display all PowerShell variables using the variable drive:</span></span>

```powershell
Get-ChildItem variable:
```

## <a name="using-cmdexe-variables"></a><span data-ttu-id="8328a-130">Использование переменных cmd.exe</span><span class="sxs-lookup"><span data-stu-id="8328a-130">Using cmd.exe variables</span></span>

<span data-ttu-id="8328a-131">PowerShell может использовать одни и те же переменные среды, доступные для любого процесса Windows, в том числе для **cmd.exe**.</span><span class="sxs-lookup"><span data-stu-id="8328a-131">PowerShell can use the same environment variables available to any Windows process, including **cmd.exe**.</span></span> <span data-ttu-id="8328a-132">Эти переменные предоставляются с помощью диска с именем `env:`.</span><span class="sxs-lookup"><span data-stu-id="8328a-132">These variables are exposed through a drive named `env:`.</span></span> <span data-ttu-id="8328a-133">Чтобы просмотреть эти переменные, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8328a-133">You can view these variables by typing the following command:</span></span>

```powershell
Get-ChildItem env:
```

<span data-ttu-id="8328a-134">Стандартные командлеты `*-Variable` не предназначены для работы с переменными среды.</span><span class="sxs-lookup"><span data-stu-id="8328a-134">The standard `*-Variable` cmdlets aren't designed to work with environment variables.</span></span> <span data-ttu-id="8328a-135">Доступ к переменным среды осуществляется с помощью префикса диска `env:`.</span><span class="sxs-lookup"><span data-stu-id="8328a-135">Environment variables are accessed using the `env:` drive prefix.</span></span> <span data-ttu-id="8328a-136">Например, переменная **%SystemRoot%** в командной строке **cmd.exe** содержит имя корневого каталога операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8328a-136">For example, the **%SystemRoot%** variable in **cmd.exe** contains the operating system's root directory name.</span></span> <span data-ttu-id="8328a-137">В PowerShell используйте `$env:SystemRoot` для доступа к этому же значению.</span><span class="sxs-lookup"><span data-stu-id="8328a-137">In PowerShell, you use `$env:SystemRoot` to access the same value.</span></span>

```
PS> $env:SystemRoot
C:\WINDOWS
```

<span data-ttu-id="8328a-138">В PowerShell также можно создавать и изменять переменные среды.</span><span class="sxs-lookup"><span data-stu-id="8328a-138">You can also create and modify environment variables from within PowerShell.</span></span> <span data-ttu-id="8328a-139">Переменные среды в PowerShell соответствуют тем же правилам для переменных среды, которые используются в других частях операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8328a-139">Environment variables in PowerShell follow the same rules for environment variables used elsewhere in the operating system.</span></span> <span data-ttu-id="8328a-140">В следующем примере создается переменная среды:</span><span class="sxs-lookup"><span data-stu-id="8328a-140">The following example creates a new environment variable:</span></span>

```powershell
$env:LIB_PATH='/usr/local/lib'
```

<span data-ttu-id="8328a-141">В именах переменных среды принято использовать прописные буквы, хоть это и не требуется.</span><span class="sxs-lookup"><span data-stu-id="8328a-141">Though not required, is it common for environment variable names to use all uppercase letters.</span></span>
