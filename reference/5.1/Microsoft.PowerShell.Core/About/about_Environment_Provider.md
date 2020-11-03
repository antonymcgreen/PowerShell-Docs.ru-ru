---
description: Среда
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Environment Provider
ms.openlocfilehash: afa9f17333e09f31b130e24d9ede289f9621faf8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232425"
---
# <a name="environment-provider"></a><span data-ttu-id="aaa23-104">Поставщик среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-104">Environment provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="aaa23-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="aaa23-105">Provider name</span></span>

<span data-ttu-id="aaa23-106">Среда</span><span class="sxs-lookup"><span data-stu-id="aaa23-106">Environment</span></span>

## <a name="drives"></a><span data-ttu-id="aaa23-107">Диски</span><span class="sxs-lookup"><span data-stu-id="aaa23-107">Drives</span></span>

`Env:`

## <a name="capabilities"></a><span data-ttu-id="aaa23-108">Характеристики</span><span class="sxs-lookup"><span data-stu-id="aaa23-108">Capabilities</span></span>

<span data-ttu-id="aaa23-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="aaa23-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="aaa23-110">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="aaa23-110">Short description</span></span>

<span data-ttu-id="aaa23-111">Предоставляет доступ к переменным среды Windows.</span><span class="sxs-lookup"><span data-stu-id="aaa23-111">Provides access to the Windows environment variables.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="aaa23-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="aaa23-112">Detailed description</span></span>

<span data-ttu-id="aaa23-113">Поставщик **среды** PowerShell позволяет получать, добавлять, изменять, очищать и удалять переменные среды и значения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaa23-113">The PowerShell **Environment** provider lets you get, add, change, clear, and delete environment variables and values in PowerShell.</span></span>

<span data-ttu-id="aaa23-114">Переменные **среды** — это переменные с динамическим именованием, описывающие среду, в которой выполняются программы.</span><span class="sxs-lookup"><span data-stu-id="aaa23-114">**Environment** variables are dynamically named variables that describe the environment in which your programs run.</span></span> <span data-ttu-id="aaa23-115">Windows и PowerShell используют переменные среды для хранения постоянных данных, влияющих на выполнение системы и процесса.</span><span class="sxs-lookup"><span data-stu-id="aaa23-115">Windows and PowerShell use environment variables to store persistent information that affect system and process execution.</span></span> <span data-ttu-id="aaa23-116">В отличие от переменных PowerShell, переменные среды не подчиняются ограничениям области.</span><span class="sxs-lookup"><span data-stu-id="aaa23-116">Unlike PowerShell variables, environment variables are not subject to scope constraints.</span></span>

<span data-ttu-id="aaa23-117">Диск **среды** — это плоское пространство имен, содержащее переменные среды, относящиеся к сеансу текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="aaa23-117">The **Environment** drive is a flat namespace containing the environment variables specific to the current user's session.</span></span> <span data-ttu-id="aaa23-118">Переменные среды не имеют дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="aaa23-118">The environment variables have no child items.</span></span>

<span data-ttu-id="aaa23-119">Поставщик **среды** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="aaa23-119">The **Environment** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="aaa23-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="aaa23-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="aaa23-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="aaa23-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="aaa23-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="aaa23-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="aaa23-123">New-Item</span><span class="sxs-lookup"><span data-stu-id="aaa23-123">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="aaa23-124">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="aaa23-124">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="aaa23-125">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="aaa23-125">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="aaa23-126">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="aaa23-126">Types exposed by this provider</span></span>

<span data-ttu-id="aaa23-127">Каждая переменная среды является экземпляром класса [System. Collections. DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) .</span><span class="sxs-lookup"><span data-stu-id="aaa23-127">Each environment variable is an instance of the [System.Collections.DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) class.</span></span> <span data-ttu-id="aaa23-128">Имя переменной является ключом словаря.</span><span class="sxs-lookup"><span data-stu-id="aaa23-128">The name of the variable is the dictionary key.</span></span> <span data-ttu-id="aaa23-129">Значение переменной среды является значением словаря.</span><span class="sxs-lookup"><span data-stu-id="aaa23-129">The value of the environment variable is the dictionary value.</span></span>

## <a name="navigating-the-environment-drive"></a><span data-ttu-id="aaa23-130">Навигация по диску среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-130">Navigating the Environment drive</span></span>

<span data-ttu-id="aaa23-131">Поставщик **среды** предоставляет хранилище данных на `Env:` диске.</span><span class="sxs-lookup"><span data-stu-id="aaa23-131">The **Environment** provider exposes its data store in the `Env:` drive.</span></span> <span data-ttu-id="aaa23-132">Чтобы работать с переменными среды, измените расположение на `Env:` диск ( `Set-Location Env:` ) или с другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaa23-132">To work with environment variables, change your location to the `Env:` drive (`Set-Location Env:`), or work from another PowerShell drive.</span></span> <span data-ttu-id="aaa23-133">Чтобы сослаться на переменную среды из другого расположения, используйте `Env:` имя диска в пути.</span><span class="sxs-lookup"><span data-stu-id="aaa23-133">To reference an environment variable from another location, use the `Env:` drive name in the path.</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="aaa23-134">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="aaa23-134">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="aaa23-135">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="aaa23-135">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="aaa23-136">Вы также можете работать с поставщиком **среды** с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaa23-136">You can also work with the **Environment** provider from any other PowerShell drive.</span></span> <span data-ttu-id="aaa23-137">Чтобы сослаться на переменную среды из другого расположения, используйте имя диска `Env:` в пути.</span><span class="sxs-lookup"><span data-stu-id="aaa23-137">To reference an environment variable from another location, use the drive name `Env:` in the path.</span></span>

<span data-ttu-id="aaa23-138">Поставщик **среды** также предоставляет переменные среды с помощью префикса переменной `$env:` .</span><span class="sxs-lookup"><span data-stu-id="aaa23-138">The **Environment** provider also exposes environment variables using a variable prefix of `$env:`.</span></span>  <span data-ttu-id="aaa23-139">Следующая команда просматривает содержимое переменной среды **ProgramFiles** .</span><span class="sxs-lookup"><span data-stu-id="aaa23-139">The following command views the contents of the **ProgramFiles** environment variable.</span></span> <span data-ttu-id="aaa23-140">`$env:`Префикс переменной можно использовать с любого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaa23-140">The `$env:` variable prefix can be used from any PowerShell drive.</span></span>

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

<span data-ttu-id="aaa23-141">Значение переменной среды также можно изменить с помощью `$env:` префикса переменной.</span><span class="sxs-lookup"><span data-stu-id="aaa23-141">You can also change the value of an environment variable using the `$env:` variable prefix.</span></span>  <span data-ttu-id="aaa23-142">Все внесенные изменения относятся только к текущему сеансу PowerShell до тех пор, пока он активен.</span><span class="sxs-lookup"><span data-stu-id="aaa23-142">Any changes made only pertain to the current PowerShell session for as long as it is active.</span></span>

> [!NOTE]
> <span data-ttu-id="aaa23-143">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="aaa23-143">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="aaa23-144">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="aaa23-144">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="aaa23-145">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="aaa23-145">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-environment-variables"></a><span data-ttu-id="aaa23-146">Получение переменных среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-146">Getting environment variables</span></span>

<span data-ttu-id="aaa23-147">Эта команда выводит список всех переменных среды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="aaa23-147">This command lists all the environment variables in the current session.</span></span>

```powershell
Get-Item -Path Env:
```

<span data-ttu-id="aaa23-148">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaa23-148">You can use this command from any PowerShell drive.</span></span>

<span data-ttu-id="aaa23-149">Поставщик среды не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="aaa23-149">The Environment provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a><span data-ttu-id="aaa23-150">Получить выбранную переменную среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-150">Get a selected environment variable</span></span>

<span data-ttu-id="aaa23-151">Эта команда возвращает `WINDIR` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="aaa23-151">This command gets the `WINDIR` environment Variable.</span></span>

```powershell
Get-ChildItem -Path Env:windir
```

<span data-ttu-id="aaa23-152">Можно также использовать формат префикса переменной.</span><span class="sxs-lookup"><span data-stu-id="aaa23-152">You can also use the variable prefix format as well.</span></span>

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a><span data-ttu-id="aaa23-153">Создание переменной среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-153">Create an environment variable</span></span>

<span data-ttu-id="aaa23-154">Эта команда создает `USERMODE` переменную среды со значением "без прав администратора".</span><span class="sxs-lookup"><span data-stu-id="aaa23-154">This command creates the `USERMODE` environment variable with a value of "Non-Admin".</span></span> <span data-ttu-id="aaa23-155">`-Path`Значение параметра создает новый элемент на `Env:` диске.</span><span class="sxs-lookup"><span data-stu-id="aaa23-155">The `-Path` parameter value creates the new item in the `Env:` drive.</span></span> <span data-ttu-id="aaa23-156">Новую переменную среды можно использовать только в текущем сеансе PowerShell до тех пор, пока он активен.</span><span class="sxs-lookup"><span data-stu-id="aaa23-156">The new environment variable is only usable in the current PowerShell session for as long as it is active.</span></span>

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a><span data-ttu-id="aaa23-157">Изменение переменной среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-157">Changing an environment variable</span></span>

### <a name="rename-an-environment-variable"></a><span data-ttu-id="aaa23-158">Переименование переменной среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-158">Rename an environment variable</span></span>

<span data-ttu-id="aaa23-159">Эта команда использует `Rename-Item` командлет для изменения имени `USERMODE` переменной среды, созданной в `USERROLE` .</span><span class="sxs-lookup"><span data-stu-id="aaa23-159">This command uses the `Rename-Item` cmdlet to change the name of the `USERMODE` environment variable that you created to `USERROLE`.</span></span> <span data-ttu-id="aaa23-160">Не изменяйте имена переменных среды, используемых системой.</span><span class="sxs-lookup"><span data-stu-id="aaa23-160">Do not change the name of an environment variable that the system uses.</span></span> <span data-ttu-id="aaa23-161">Хотя эти изменения затрагивают только текущий сеанс, они могут привести к некорректному поведению системы или программы.</span><span class="sxs-lookup"><span data-stu-id="aaa23-161">Although these changes affect only the current session, they might cause the system or a program to operate incorrectly.</span></span>

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a><span data-ttu-id="aaa23-162">Изменение переменной среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-162">Change an environment variable</span></span>

<span data-ttu-id="aaa23-163">Эта команда использует `Set-Item` командлет, чтобы изменить значение `USERROLE` переменной среды на "Administrator".</span><span class="sxs-lookup"><span data-stu-id="aaa23-163">This command uses the `Set-Item` cmdlet to change the value of the `USERROLE` environment variable to "Administrator".</span></span>

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a><span data-ttu-id="aaa23-164">Копирование переменной среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-164">Copy an environment variable</span></span>

<span data-ttu-id="aaa23-165">Эта команда копирует значение `USERROLE` переменной среды в `USERROLE2` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="aaa23-165">This command copies the value of the `USERROLE` environment variable to the `USERROLE2` environment Variable.</span></span>

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a><span data-ttu-id="aaa23-166">Удаление переменной среды</span><span class="sxs-lookup"><span data-stu-id="aaa23-166">Remove an environment variable</span></span>

<span data-ttu-id="aaa23-167">Эта команда удаляет `USERROLE2` переменную среды из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="aaa23-167">This command deletes the `USERROLE2` environment variable from the current session.</span></span>

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a><span data-ttu-id="aaa23-168">Удаление переменной среды с Clear-Item</span><span class="sxs-lookup"><span data-stu-id="aaa23-168">Remove an environment variable with Clear-Item</span></span>

<span data-ttu-id="aaa23-169">Эта команда удаляет `USERROLE` переменную среды путем очистки ее значения.</span><span class="sxs-lookup"><span data-stu-id="aaa23-169">This command deletes the `USERROLE` environment variable by clearing its value.</span></span>

```powershell
Clear-Item -Path Env:USERROLE
```

## <a name="using-the-pipeline"></a><span data-ttu-id="aaa23-170">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="aaa23-170">Using the pipeline</span></span>

<span data-ttu-id="aaa23-171">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="aaa23-171">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="aaa23-172">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="aaa23-172">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="aaa23-173">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="aaa23-173">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="aaa23-174">Получение справки</span><span class="sxs-lookup"><span data-stu-id="aaa23-174">Getting help</span></span>

<span data-ttu-id="aaa23-175">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="aaa23-175">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="aaa23-176">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="aaa23-176">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a><span data-ttu-id="aaa23-177">См. также статью</span><span class="sxs-lookup"><span data-stu-id="aaa23-177">See also</span></span>

[<span data-ttu-id="aaa23-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="aaa23-178">about_Providers</span></span>](../About/about_Providers.md)
