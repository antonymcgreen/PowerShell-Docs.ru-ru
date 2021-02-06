---
description: Среда
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Environment Provider
ms.openlocfilehash: f50558ba23d21b5ca145a06086c1c6d9b1fcd3bf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604370"
---
# <a name="environment-provider"></a><span data-ttu-id="5d70e-103">Поставщик среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-103">Environment provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="5d70e-104">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="5d70e-104">Provider name</span></span>
<span data-ttu-id="5d70e-105">Среда</span><span class="sxs-lookup"><span data-stu-id="5d70e-105">Environment</span></span>

## <a name="drives"></a><span data-ttu-id="5d70e-106">Диски</span><span class="sxs-lookup"><span data-stu-id="5d70e-106">Drives</span></span>

`Env:`

## <a name="capabilities"></a><span data-ttu-id="5d70e-107">Характеристики</span><span class="sxs-lookup"><span data-stu-id="5d70e-107">Capabilities</span></span>

<span data-ttu-id="5d70e-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="5d70e-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="5d70e-109">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="5d70e-109">Short description</span></span>

<span data-ttu-id="5d70e-110">Предоставляет доступ к переменным среды Windows.</span><span class="sxs-lookup"><span data-stu-id="5d70e-110">Provides access to the Windows environment variables.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="5d70e-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="5d70e-111">Detailed description</span></span>

<span data-ttu-id="5d70e-112">Поставщик **среды** PowerShell позволяет получать, добавлять, изменять, очищать и удалять переменные среды и значения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d70e-112">The PowerShell **Environment** provider lets you get, add, change, clear, and delete environment variables and values in PowerShell.</span></span>

<span data-ttu-id="5d70e-113">Переменные **среды** — это переменные с динамическим именованием, описывающие среду, в которой выполняются программы.</span><span class="sxs-lookup"><span data-stu-id="5d70e-113">**Environment** variables are dynamically named variables that describe the environment in which your programs run.</span></span> <span data-ttu-id="5d70e-114">Windows и PowerShell используют переменные среды для хранения постоянных данных, влияющих на выполнение системы и процесса.</span><span class="sxs-lookup"><span data-stu-id="5d70e-114">Windows and PowerShell use environment variables to store persistent information that affect system and process execution.</span></span> <span data-ttu-id="5d70e-115">В отличие от переменных PowerShell, переменные среды не подчиняются ограничениям области.</span><span class="sxs-lookup"><span data-stu-id="5d70e-115">Unlike PowerShell variables, environment variables are not subject to scope constraints.</span></span>

<span data-ttu-id="5d70e-116">Диск **среды** — это плоское пространство имен, содержащее переменные среды, относящиеся к сеансу текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d70e-116">The **Environment** drive is a flat namespace containing the environment variables specific to the current user's session.</span></span> <span data-ttu-id="5d70e-117">Переменные среды не имеют дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="5d70e-117">The environment variables have no child items.</span></span>

<span data-ttu-id="5d70e-118">Поставщик **среды** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5d70e-118">The **Environment** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="5d70e-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="5d70e-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="5d70e-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="5d70e-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="5d70e-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="5d70e-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="5d70e-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="5d70e-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="5d70e-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="5d70e-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="5d70e-124">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="5d70e-124">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="5d70e-125">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="5d70e-125">Types exposed by this provider</span></span>

<span data-ttu-id="5d70e-126">Каждая переменная среды является экземпляром класса [System. Collections. DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) .</span><span class="sxs-lookup"><span data-stu-id="5d70e-126">Each environment variable is an instance of the [System.Collections.DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) class.</span></span> <span data-ttu-id="5d70e-127">Имя переменной является ключом словаря.</span><span class="sxs-lookup"><span data-stu-id="5d70e-127">The name of the variable is the dictionary key.</span></span> <span data-ttu-id="5d70e-128">Значение переменной среды является значением словаря.</span><span class="sxs-lookup"><span data-stu-id="5d70e-128">The value of the environment variable is the dictionary value.</span></span>

## <a name="navigating-the-environment-drive"></a><span data-ttu-id="5d70e-129">Навигация по диску среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-129">Navigating the Environment drive</span></span>

<span data-ttu-id="5d70e-130">Поставщик **среды** предоставляет хранилище данных на `Env:` диске.</span><span class="sxs-lookup"><span data-stu-id="5d70e-130">The **Environment** provider exposes its data store in the `Env:` drive.</span></span> <span data-ttu-id="5d70e-131">Чтобы работать с переменными среды, измените расположение на `Env:` диск ( `Set-Location Env:` ) или с другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d70e-131">To work with environment variables, change your location to the `Env:` drive (`Set-Location Env:`), or work from another PowerShell drive.</span></span> <span data-ttu-id="5d70e-132">Чтобы сослаться на переменную среды из другого расположения, используйте `Env:` имя диска в пути.</span><span class="sxs-lookup"><span data-stu-id="5d70e-132">To reference an environment variable from another location, use the `Env:` drive name in the path.</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="5d70e-133">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="5d70e-133">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="5d70e-134">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="5d70e-134">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="5d70e-135">Вы также можете работать с поставщиком **среды** с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d70e-135">You can also work with the **Environment** provider from any other PowerShell drive.</span></span> <span data-ttu-id="5d70e-136">Чтобы сослаться на переменную среды из другого расположения, используйте имя диска `Env:` в пути.</span><span class="sxs-lookup"><span data-stu-id="5d70e-136">To reference an environment variable from another location, use the drive name `Env:` in the path.</span></span>

<span data-ttu-id="5d70e-137">Поставщик **среды** также предоставляет переменные среды с помощью префикса переменной `$env:` .</span><span class="sxs-lookup"><span data-stu-id="5d70e-137">The **Environment** provider also exposes environment variables using a variable prefix of `$env:`.</span></span>  <span data-ttu-id="5d70e-138">Следующая команда просматривает содержимое переменной среды **ProgramFiles** .</span><span class="sxs-lookup"><span data-stu-id="5d70e-138">The following command views the contents of the **ProgramFiles** environment variable.</span></span> <span data-ttu-id="5d70e-139">`$env:`Префикс переменной можно использовать с любого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d70e-139">The `$env:` variable prefix can be used from any PowerShell drive.</span></span>

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

<span data-ttu-id="5d70e-140">Значение переменной среды также можно изменить с помощью `$env:` префикса переменной.</span><span class="sxs-lookup"><span data-stu-id="5d70e-140">You can also change the value of an environment variable using the `$env:` variable prefix.</span></span>  <span data-ttu-id="5d70e-141">Все внесенные изменения относятся только к текущему сеансу PowerShell до тех пор, пока он активен.</span><span class="sxs-lookup"><span data-stu-id="5d70e-141">Any changes made only pertain to the current PowerShell session for as long as it is active.</span></span>

> [!NOTE]
> <span data-ttu-id="5d70e-142">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="5d70e-142">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="5d70e-143">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="5d70e-143">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="5d70e-144">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="5d70e-144">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-environment-variables"></a><span data-ttu-id="5d70e-145">Получение переменных среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-145">Getting environment variables</span></span>

<span data-ttu-id="5d70e-146">Эта команда выводит список всех переменных среды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5d70e-146">This command lists all the environment variables in the current session.</span></span>

```powershell
Get-Item -Path Env:
```

<span data-ttu-id="5d70e-147">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d70e-147">You can use this command from any PowerShell drive.</span></span>

<span data-ttu-id="5d70e-148">Поставщик среды не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="5d70e-148">The Environment provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a><span data-ttu-id="5d70e-149">Получить выбранную переменную среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-149">Get a selected environment variable</span></span>

<span data-ttu-id="5d70e-150">Эта команда возвращает `WINDIR` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="5d70e-150">This command gets the `WINDIR` environment Variable.</span></span>

```powershell
Get-ChildItem -Path Env:windir
```

<span data-ttu-id="5d70e-151">Можно также использовать формат префикса переменной.</span><span class="sxs-lookup"><span data-stu-id="5d70e-151">You can also use the variable prefix format as well.</span></span>

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a><span data-ttu-id="5d70e-152">Создание переменной среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-152">Create an environment variable</span></span>

<span data-ttu-id="5d70e-153">Эта команда создает `USERMODE` переменную среды со значением "без прав администратора".</span><span class="sxs-lookup"><span data-stu-id="5d70e-153">This command creates the `USERMODE` environment variable with a value of "Non-Admin".</span></span> <span data-ttu-id="5d70e-154">`-Path`Значение параметра создает новый элемент на `Env:` диске.</span><span class="sxs-lookup"><span data-stu-id="5d70e-154">The `-Path` parameter value creates the new item in the `Env:` drive.</span></span> <span data-ttu-id="5d70e-155">Новую переменную среды можно использовать только в текущем сеансе PowerShell до тех пор, пока он активен.</span><span class="sxs-lookup"><span data-stu-id="5d70e-155">The new environment variable is only usable in the current PowerShell session for as long as it is active.</span></span>

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a><span data-ttu-id="5d70e-156">Изменение переменной среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-156">Changing an environment variable</span></span>

### <a name="rename-an-environment-variable"></a><span data-ttu-id="5d70e-157">Переименование переменной среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-157">Rename an environment variable</span></span>

<span data-ttu-id="5d70e-158">Эта команда использует `Rename-Item` командлет для изменения имени `USERMODE` переменной среды, созданной в `USERROLE` .</span><span class="sxs-lookup"><span data-stu-id="5d70e-158">This command uses the `Rename-Item` cmdlet to change the name of the `USERMODE` environment variable that you created to `USERROLE`.</span></span> <span data-ttu-id="5d70e-159">Не изменяйте имена переменных среды, используемых системой.</span><span class="sxs-lookup"><span data-stu-id="5d70e-159">Do not change the name of an environment variable that the system uses.</span></span> <span data-ttu-id="5d70e-160">Хотя эти изменения затрагивают только текущий сеанс, они могут привести к некорректному поведению системы или программы.</span><span class="sxs-lookup"><span data-stu-id="5d70e-160">Although these changes affect only the current session, they might cause the system or a program to operate incorrectly.</span></span>

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a><span data-ttu-id="5d70e-161">Изменение переменной среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-161">Change an environment variable</span></span>

<span data-ttu-id="5d70e-162">Эта команда использует `Set-Item` командлет, чтобы изменить значение `USERROLE` переменной среды на "Administrator".</span><span class="sxs-lookup"><span data-stu-id="5d70e-162">This command uses the `Set-Item` cmdlet to change the value of the `USERROLE` environment variable to "Administrator".</span></span>

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a><span data-ttu-id="5d70e-163">Копирование переменной среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-163">Copy an environment variable</span></span>

<span data-ttu-id="5d70e-164">Эта команда копирует значение `USERROLE` переменной среды в `USERROLE2` переменную среды.</span><span class="sxs-lookup"><span data-stu-id="5d70e-164">This command copies the value of the `USERROLE` environment variable to the `USERROLE2` environment Variable.</span></span>

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a><span data-ttu-id="5d70e-165">Удаление переменной среды</span><span class="sxs-lookup"><span data-stu-id="5d70e-165">Remove an environment variable</span></span>

<span data-ttu-id="5d70e-166">Эта команда удаляет `USERROLE2` переменную среды из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5d70e-166">This command deletes the `USERROLE2` environment variable from the current session.</span></span>

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a><span data-ttu-id="5d70e-167">Удаление переменной среды с Clear-Item</span><span class="sxs-lookup"><span data-stu-id="5d70e-167">Remove an environment variable with Clear-Item</span></span>

<span data-ttu-id="5d70e-168">Эта команда удаляет `USERROLE` переменную среды путем очистки ее значения.</span><span class="sxs-lookup"><span data-stu-id="5d70e-168">This command deletes the `USERROLE` environment variable by clearing its value.</span></span>

```powershell
Clear-Item -Path Env:USERROLE
```

## <a name="using-the-pipeline"></a><span data-ttu-id="5d70e-169">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="5d70e-169">Using the pipeline</span></span>

<span data-ttu-id="5d70e-170">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="5d70e-170">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="5d70e-171">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="5d70e-171">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="5d70e-172">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5d70e-172">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="5d70e-173">Получение справки</span><span class="sxs-lookup"><span data-stu-id="5d70e-173">Getting help</span></span>

<span data-ttu-id="5d70e-174">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="5d70e-174">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="5d70e-175">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="5d70e-175">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a><span data-ttu-id="5d70e-176">См. также</span><span class="sxs-lookup"><span data-stu-id="5d70e-176">See also</span></span>

[<span data-ttu-id="5d70e-177">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5d70e-177">about_Providers</span></span>](../About/about_Providers.md)

