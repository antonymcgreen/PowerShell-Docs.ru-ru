---
description: Псевдоним
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Alias Provider
ms.openlocfilehash: 994bd183f047123502f7e152c59b0d8aeb32a1b9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232461"
---
# <a name="alias-provider"></a><span data-ttu-id="08ab2-104">Поставщик псевдонима</span><span class="sxs-lookup"><span data-stu-id="08ab2-104">Alias provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="08ab2-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="08ab2-105">Provider name</span></span>

<span data-ttu-id="08ab2-106">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="08ab2-106">Alias</span></span>

## <a name="drives"></a><span data-ttu-id="08ab2-107">Диски</span><span class="sxs-lookup"><span data-stu-id="08ab2-107">Drives</span></span>

`Alias:`

## <a name="capabilities"></a><span data-ttu-id="08ab2-108">Характеристики</span><span class="sxs-lookup"><span data-stu-id="08ab2-108">Capabilities</span></span>

<span data-ttu-id="08ab2-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="08ab2-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="08ab2-110">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="08ab2-110">Short description</span></span>

<span data-ttu-id="08ab2-111">Предоставляет доступ к псевдонимам PowerShell и значениям, которые они представляют.</span><span class="sxs-lookup"><span data-stu-id="08ab2-111">Provides access to the PowerShell aliases and the values that they represent.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="08ab2-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="08ab2-112">Detailed description</span></span>

<span data-ttu-id="08ab2-113">Поставщик **псевдонимов** PowerShell позволяет получать, добавлять, изменять, очищать и удалять псевдонимы в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08ab2-113">The PowerShell **Alias** provider lets you get, add, change, clear, and delete aliases in PowerShell.</span></span>

<span data-ttu-id="08ab2-114">Псевдоним — это альтернативное имя для командлета, функции, исполняемого файла, включая скрипты.</span><span class="sxs-lookup"><span data-stu-id="08ab2-114">An alias is an alternate name for a cmdlet, function, executable file, including scripts.</span></span> <span data-ttu-id="08ab2-115">PowerShell включает набор встроенных псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="08ab2-115">PowerShell includes a set of built-in aliases.</span></span> <span data-ttu-id="08ab2-116">Вы можете добавить собственные псевдонимы в текущий сеанс и профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08ab2-116">You can add your own aliases to the current session and to your PowerShell profile.</span></span>

<span data-ttu-id="08ab2-117">Диск **псевдонима** является плоским пространством имен, которое содержит только объекты-псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="08ab2-117">The **Alias** drive is a flat namespace that contains only the alias objects.</span></span>
<span data-ttu-id="08ab2-118">У псевдонимов нет дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="08ab2-118">The aliases have no child items.</span></span>

<span data-ttu-id="08ab2-119">Поставщик **псевдонимов** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="08ab2-119">The **Alias** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="08ab2-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="08ab2-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="08ab2-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="08ab2-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="08ab2-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="08ab2-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="08ab2-123">New-Item</span><span class="sxs-lookup"><span data-stu-id="08ab2-123">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="08ab2-124">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="08ab2-124">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="08ab2-125">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="08ab2-125">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="08ab2-126">В PowerShell имеется набор командлетов, предназначенных для просмотра и изменения псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="08ab2-126">PowerShell includes a set of cmdlets that are designed to view and to change aliases.</span></span> <span data-ttu-id="08ab2-127">При использовании командлетов **псевдонимов** не нужно указывать `Alias:` диск в имени.</span><span class="sxs-lookup"><span data-stu-id="08ab2-127">When you use **Alias** cmdlets, you do not need to specify the `Alias:` drive in the name.</span></span> <span data-ttu-id="08ab2-128">В этой статье не рассматривается работа с командлетами **псевдонимов** .</span><span class="sxs-lookup"><span data-stu-id="08ab2-128">This article does not cover working with **Alias** cmdlets.</span></span>

- [<span data-ttu-id="08ab2-129">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="08ab2-129">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="08ab2-130">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="08ab2-130">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="08ab2-131">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="08ab2-131">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="08ab2-132">New-Alias</span><span class="sxs-lookup"><span data-stu-id="08ab2-132">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="08ab2-133">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="08ab2-133">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="08ab2-134">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="08ab2-134">Types exposed by this provider</span></span>

<span data-ttu-id="08ab2-135">Каждый псевдоним является экземпляром класса [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) .</span><span class="sxs-lookup"><span data-stu-id="08ab2-135">Each alias is an instance of the [System.Management.Automation.AliasInfo](/dotnet/api/system.management.automation.aliasinfo) class.</span></span>

## <a name="navigating-the-alias-drive"></a><span data-ttu-id="08ab2-136">Навигация по псевдониму диска</span><span class="sxs-lookup"><span data-stu-id="08ab2-136">Navigating the Alias drive</span></span>

<span data-ttu-id="08ab2-137">Поставщик **псевдонимов** предоставляет хранилище данных на `Alias:` диске.</span><span class="sxs-lookup"><span data-stu-id="08ab2-137">The **Alias** provider exposes its data store in the `Alias:` drive.</span></span> <span data-ttu-id="08ab2-138">Для работы с псевдонимами можно изменить расположение на `Alias:` диск с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="08ab2-138">To work with aliases, you can change your location to the `Alias:` drive by using the following command:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="08ab2-139">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="08ab2-139">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="08ab2-140">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="08ab2-140">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="08ab2-141">Вы также можете работать с поставщиком псевдонимов с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08ab2-141">You can also work with the Alias provider from any other PowerShell drive.</span></span> <span data-ttu-id="08ab2-142">Чтобы сослаться на псевдоним из другого расположения, используйте `Alias:` имя диска в пути.</span><span class="sxs-lookup"><span data-stu-id="08ab2-142">To reference an alias from another location, use the `Alias:` drive name in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="08ab2-143">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="08ab2-143">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="08ab2-144">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="08ab2-144">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="08ab2-145">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="08ab2-145">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

### <a name="displaying-the-contents-of-the-alias-drive"></a><span data-ttu-id="08ab2-146">Отображение содержимого диска Alias:</span><span class="sxs-lookup"><span data-stu-id="08ab2-146">Displaying the Contents of the Alias: drive</span></span>

<span data-ttu-id="08ab2-147">Эта команда возвращает список всех псевдонимов, если текущим расположением является `Alias:` диск.</span><span class="sxs-lookup"><span data-stu-id="08ab2-147">This command gets the list of all the aliases when the current location is the `Alias:` drive.</span></span> <span data-ttu-id="08ab2-148">Он использует подстановочный знак `*` для указания всего содержимого текущего расположения.</span><span class="sxs-lookup"><span data-stu-id="08ab2-148">It uses a wildcard character `*` to indicate all the contents of the current location.</span></span>

```powershell
PS Alias:\> Get-Item -Path *
```

<span data-ttu-id="08ab2-149">На `Alias:` диске точка `.` , которая представляет текущее расположение, и символ-шаблон `*` , который представляет все элементы в текущем расположении, имеют одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="08ab2-149">In the `Alias:` drive, a dot `.`, which represents the current location, and a wildcard character `*`, which represents all items in the current location, have the same effect.</span></span> <span data-ttu-id="08ab2-150">Например, `Get-Item -Path .` или `Get-Item \*` получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="08ab2-150">For example, `Get-Item -Path .` or `Get-Item \*` produce the same result.</span></span>

<span data-ttu-id="08ab2-151">Поставщик псевдонимов не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-151">The Alias provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a><span data-ttu-id="08ab2-152">Получить выбранный псевдоним</span><span class="sxs-lookup"><span data-stu-id="08ab2-152">Get a selected alias</span></span>

<span data-ttu-id="08ab2-153">Эта команда возвращает `ls` псевдоним.</span><span class="sxs-lookup"><span data-stu-id="08ab2-153">This command gets the `ls` alias.</span></span>
<span data-ttu-id="08ab2-154">Так как он содержит путь, его можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08ab2-154">Because it includes the path, you can use it in any PowerShell drive.</span></span>

```powershell
Get-Item -Path Alias:ls
```

<span data-ttu-id="08ab2-155">Если вы используете `Alias:` диск, можно опустить имя диска из пути.</span><span class="sxs-lookup"><span data-stu-id="08ab2-155">If you are in the `Alias:` drive, you can omit the drive name from the path.</span></span>

<span data-ttu-id="08ab2-156">Можно также получить определение псевдонима путем добавления префикса к поставщику в виде символа доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="08ab2-156">You can also retrieve the definition for an alias by prefixing the provider path with the dollar sign (`$`).</span></span>

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a><span data-ttu-id="08ab2-157">Получение всех псевдонимов для конкретного командлета</span><span class="sxs-lookup"><span data-stu-id="08ab2-157">Get all aliases for a specific cmdlet</span></span>

<span data-ttu-id="08ab2-158">Эта команда возвращает список псевдонимов, связанных с `Get-ChildItem` командлетом.</span><span class="sxs-lookup"><span data-stu-id="08ab2-158">This command gets a list of the aliases that are associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="08ab2-159">В нем используется свойство **definition** , в котором хранится имя командлета.</span><span class="sxs-lookup"><span data-stu-id="08ab2-159">It uses the **Definition** property, which stores the cmdlet name.</span></span>

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a><span data-ttu-id="08ab2-160">Создание псевдонимов</span><span class="sxs-lookup"><span data-stu-id="08ab2-160">Creating aliases</span></span>

### <a name="create-an-alias-from-the-alias-drive"></a><span data-ttu-id="08ab2-161">Создание псевдонима из диска Alias:</span><span class="sxs-lookup"><span data-stu-id="08ab2-161">Create an alias from the Alias: drive</span></span>

<span data-ttu-id="08ab2-162">Эта команда создает `serv` псевдоним для `Get-Service` командлета.</span><span class="sxs-lookup"><span data-stu-id="08ab2-162">This command creates the `serv` alias for the `Get-Service` cmdlet.</span></span> <span data-ttu-id="08ab2-163">Поскольку текущее расположение находится на `Alias:` диске, `-Path` параметр не требуется.</span><span class="sxs-lookup"><span data-stu-id="08ab2-163">Because the current location is in the `Alias:` drive, the `-Path` parameter is not needed.</span></span>

<span data-ttu-id="08ab2-164">Эта команда также использует `-Options` динамический параметр для задания параметра **AllScope** в псевдониме.</span><span class="sxs-lookup"><span data-stu-id="08ab2-164">This command also uses the `-Options` dynamic parameter to set the **AllScope** option on the alias.</span></span> <span data-ttu-id="08ab2-165">`-Options`Параметр доступен в `New-Item` командлете, только если находится на `Alias:` диске.</span><span class="sxs-lookup"><span data-stu-id="08ab2-165">The `-Options` parameter is available in the `New-Item` cmdlet only when you are in the `Alias:` drive.</span></span> <span data-ttu-id="08ab2-166">Точка ( `.` ) указывает текущий каталог, который является диском псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="08ab2-166">The dot (`.`) indicates the current directory, which is the alias drive.</span></span>

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a><span data-ttu-id="08ab2-167">Создание псевдонима с абсолютным путем</span><span class="sxs-lookup"><span data-stu-id="08ab2-167">Create an alias with an absolute path</span></span>

<span data-ttu-id="08ab2-168">Псевдоним может быть создан для любого элемента, который вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="08ab2-168">You can create an alias for any item that invokes a command.</span></span>
<span data-ttu-id="08ab2-169">Эта команда создает `np` псевдоним для `Notepad.exe` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-169">This command creates the `np` alias for `Notepad.exe`.</span></span>

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a><span data-ttu-id="08ab2-170">Создание псевдонима для новой функции</span><span class="sxs-lookup"><span data-stu-id="08ab2-170">Create an alias to a new function</span></span>

<span data-ttu-id="08ab2-171">Псевдоним может быть создан для любой функции.</span><span class="sxs-lookup"><span data-stu-id="08ab2-171">You can create an alias for any function.</span></span> <span data-ttu-id="08ab2-172">Эта возможность позволяет создать псевдоним, включающий как командлет, так и его параметры.</span><span class="sxs-lookup"><span data-stu-id="08ab2-172">You can use this feature to create an alias that includes both a cmdlet and its parameters.</span></span>

<span data-ttu-id="08ab2-173">Первая команда создает `CD32` функцию, которая изменяет текущий каталог на `System32` каталог.</span><span class="sxs-lookup"><span data-stu-id="08ab2-173">The first command creates the `CD32` function, which changes the current directory to the `System32` directory.</span></span> <span data-ttu-id="08ab2-174">Вторая команда создает `go` псевдоним для `CD32` функции.</span><span class="sxs-lookup"><span data-stu-id="08ab2-174">The second command creates the `go` alias for the `CD32` function.</span></span>

<span data-ttu-id="08ab2-175">После завершения команды можно использовать `CD32` или `go` для вызова функции.</span><span class="sxs-lookup"><span data-stu-id="08ab2-175">When the command is complete, you can use either `CD32` or `go` to invoke the function.</span></span>

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a><span data-ttu-id="08ab2-176">Изменение псевдонимов</span><span class="sxs-lookup"><span data-stu-id="08ab2-176">Changing aliases</span></span>

### <a name="change-the-options-of-an-alias"></a><span data-ttu-id="08ab2-177">Изменение параметров псевдонима</span><span class="sxs-lookup"><span data-stu-id="08ab2-177">Change the options of an alias</span></span>

<span data-ttu-id="08ab2-178">`Set-Item` `-Options` Для изменения значения свойства псевдонима можно использовать командлет с динамическим параметром `-Options` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-178">You can use the `Set-Item` cmdlet with the `-Options` dynamic parameter to change the value of the `-Options` property of an alias.</span></span>

<span data-ttu-id="08ab2-179">Эта команда задает параметры **AllScope** и **ReadOnly** для `dir` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="08ab2-179">This command sets the **AllScope** and **ReadOnly** options for the `dir` alias.</span></span> <span data-ttu-id="08ab2-180">Команда использует `-Options` динамический параметр `Set-Item` командлета.</span><span class="sxs-lookup"><span data-stu-id="08ab2-180">The command uses the `-Options` dynamic parameter of the `Set-Item` cmdlet.</span></span> <span data-ttu-id="08ab2-181">`-Options`Параметр доступен в, `Set-Item` если он используется с **псевдонимом** или поставщиком **функций** .</span><span class="sxs-lookup"><span data-stu-id="08ab2-181">The `-Options` parameter is available in `Set-Item` when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a><span data-ttu-id="08ab2-182">Изменение команды, на которую ссылается псевдоним</span><span class="sxs-lookup"><span data-stu-id="08ab2-182">Change an aliases referenced command</span></span>

<span data-ttu-id="08ab2-183">Эта команда использует `Set-Item` командлет для изменения `gp` псевдонима, чтобы он предменял `Get-Process` командлет, а не `Get-ItemProperty` командлет.</span><span class="sxs-lookup"><span data-stu-id="08ab2-183">This command uses the `Set-Item` cmdlet to change the `gp` alias so that it represents the `Get-Process` cmdlet instead of the `Get-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="08ab2-184">`-Force`Параметр является обязательным, так как для свойства **Options** `gp` псевдонима задано значение `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-184">The `-Force` parameter is required because the value of the **Options** property of the `gp` alias is set to `ReadOnly`.</span></span> <span data-ttu-id="08ab2-185">Поскольку команда отправляется с `Alias:` диска, диск не указывается в пути.</span><span class="sxs-lookup"><span data-stu-id="08ab2-185">Because the command is submitted from within the `Alias:` drive, the drive is not specified in the path.</span></span>

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

<span data-ttu-id="08ab2-186">Это изменение затрагивает четыре свойства, которые определяют связь между псевдонимом и командой.</span><span class="sxs-lookup"><span data-stu-id="08ab2-186">The change affects the four properties that define the association between the alias and the command.</span></span> <span data-ttu-id="08ab2-187">Чтобы просмотреть результат изменения, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="08ab2-187">To view the effect of the change, type the following command:</span></span>

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a><span data-ttu-id="08ab2-188">Переименование псевдонима</span><span class="sxs-lookup"><span data-stu-id="08ab2-188">Rename an alias</span></span>

<span data-ttu-id="08ab2-189">Эта команда использует `Rename-Item` командлет, чтобы изменить `popd` псевдоним на `pop` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-189">This command uses the `Rename-Item` cmdlet to change the `popd` alias to `pop`.</span></span>

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a><span data-ttu-id="08ab2-190">Копирование псевдонима</span><span class="sxs-lookup"><span data-stu-id="08ab2-190">Copying an alias</span></span>

<span data-ttu-id="08ab2-191">Эта команда копирует `pushd` псевдоним, чтобы `push` для командлета был создан новый псевдоним `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-191">This command copies the `pushd` alias so that a new `push` alias is created for the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="08ab2-192">При создании нового псевдонима его свойство **Description** имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="08ab2-192">When the new alias is created, its **Description** property has a null value.</span></span>
<span data-ttu-id="08ab2-193">И свойство **параметра** имеет значение `None` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-193">And, its **Option** property has a value of `None`.</span></span> <span data-ttu-id="08ab2-194">Если команда выполняется из `Alias:` диска, имя диска можно опустить в значении `-Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="08ab2-194">If the command is issued from within the `Alias:` drive, you can omit the drive name from the value of the `-Path` parameter.</span></span>

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a><span data-ttu-id="08ab2-195">Удаление псевдонима</span><span class="sxs-lookup"><span data-stu-id="08ab2-195">Deleting an alias</span></span>

<span data-ttu-id="08ab2-196">Эта команда удаляет `serv` псевдоним из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="08ab2-196">This command deletes the `serv` alias from the current session.</span></span>
<span data-ttu-id="08ab2-197">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08ab2-197">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Item -Path Alias:serv
```

<span data-ttu-id="08ab2-198">Эта команда удаляет псевдонимы, начинающиеся со знака "s".</span><span class="sxs-lookup"><span data-stu-id="08ab2-198">This command deletes aliases that begin with "s".</span></span>
<span data-ttu-id="08ab2-199">Она не удаляет псевдонимы, доступные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="08ab2-199">It does not delete read-only aliases.</span></span>

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a><span data-ttu-id="08ab2-200">Удалить псевдонимы только для чтения</span><span class="sxs-lookup"><span data-stu-id="08ab2-200">Delete read-only aliases</span></span>

<span data-ttu-id="08ab2-201">Эта команда удаляет все псевдонимы из текущего сеанса, за исключением тех, `Constant` для которых задано значение свойства **Options** .</span><span class="sxs-lookup"><span data-stu-id="08ab2-201">This command deletes all aliases from the current session, except those with a value of `Constant` for their **Options** property.</span></span> <span data-ttu-id="08ab2-202">`-Force`Параметр позволяет команде удалять псевдонимы, свойство **Options** которых имеет значение `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="08ab2-202">The `-Force` parameter allows the command to delete aliases whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a><span data-ttu-id="08ab2-203">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="08ab2-203">Dynamic parameters</span></span>

<span data-ttu-id="08ab2-204">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="08ab2-204">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="08ab2-205">Параметры [System. Management. Automation. Скопедитемоптионс]</span><span class="sxs-lookup"><span data-stu-id="08ab2-205">Options [System.Management.Automation.ScopedItemOptions]</span></span>

<span data-ttu-id="08ab2-206">Определяет значение свойства **Options** псевдонима.</span><span class="sxs-lookup"><span data-stu-id="08ab2-206">Determines the value of the **Options** property of an alias.</span></span>

- <span data-ttu-id="08ab2-207">**Нет** : нет параметров.</span><span class="sxs-lookup"><span data-stu-id="08ab2-207">**None** : No options.</span></span> <span data-ttu-id="08ab2-208">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08ab2-208">This value is the default.</span></span>
- <span data-ttu-id="08ab2-209">**Константа** : псевдоним не может быть удален, и его свойства нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="08ab2-209">**Constant** :The alias cannot be deleted and its properties cannot be changed.</span></span>
  <span data-ttu-id="08ab2-210">**Константа** доступна только при создании псевдонима.</span><span class="sxs-lookup"><span data-stu-id="08ab2-210">**Constant** is available only when you create an alias.</span></span> <span data-ttu-id="08ab2-211">Нельзя изменить параметр существующего псевдонима на **Постоянный**.</span><span class="sxs-lookup"><span data-stu-id="08ab2-211">You cannot change the option of an existing alias to **Constant**.</span></span>
- <span data-ttu-id="08ab2-212">**Частный** : псевдоним является видимым только в текущей области, а не в дочерних областях.</span><span class="sxs-lookup"><span data-stu-id="08ab2-212">**Private** :The alias is visible only in the current scope, not in the child  scopes.</span></span>
- <span data-ttu-id="08ab2-213">**ReadOnly** : свойства псевдонима не могут быть изменены, за исключением использования `-Force` параметра.</span><span class="sxs-lookup"><span data-stu-id="08ab2-213">**ReadOnly** :The properties of the alias cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="08ab2-214">`Remove-Item`Для удаления псевдонима можно использовать.</span><span class="sxs-lookup"><span data-stu-id="08ab2-214">You can use `Remove-Item` to delete the alias.</span></span>
- <span data-ttu-id="08ab2-215">**AllScope** : Псевдоним копируется во все новые создаваемые области.</span><span class="sxs-lookup"><span data-stu-id="08ab2-215">**AllScope** :The alias is copied to any new scopes that are created.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="08ab2-216">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="08ab2-216">Cmdlets supported</span></span>

- [<span data-ttu-id="08ab2-217">New-Item</span><span class="sxs-lookup"><span data-stu-id="08ab2-217">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="08ab2-218">Set-Item</span><span class="sxs-lookup"><span data-stu-id="08ab2-218">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="08ab2-219">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="08ab2-219">Using the pipeline</span></span>

<span data-ttu-id="08ab2-220">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="08ab2-220">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="08ab2-221">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="08ab2-221">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="08ab2-222">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="08ab2-222">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="08ab2-223">Получение справки</span><span class="sxs-lookup"><span data-stu-id="08ab2-223">Getting help</span></span>

<span data-ttu-id="08ab2-224">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="08ab2-224">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="08ab2-225">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="08ab2-225">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a><span data-ttu-id="08ab2-226">См. также статью</span><span class="sxs-lookup"><span data-stu-id="08ab2-226">See also</span></span>

[<span data-ttu-id="08ab2-227">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="08ab2-227">about_Aliases</span></span>](../About/about_Aliases.md)

[<span data-ttu-id="08ab2-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="08ab2-228">about_Providers</span></span>](../About/about_Providers.md)
