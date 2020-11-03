---
description: Объясняет использование локальных и удаленных переменных в удаленных командах.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: f4477b76dd6ef16ca1c4dea6259c2591f1f0b40d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232641"
---
# <a name="about-remote-variables"></a><span data-ttu-id="11447-104">Сведения об удаленных переменных</span><span class="sxs-lookup"><span data-stu-id="11447-104">About Remote Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="11447-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="11447-105">Short description</span></span>

<span data-ttu-id="11447-106">Объясняет использование локальных и удаленных переменных в удаленных командах.</span><span class="sxs-lookup"><span data-stu-id="11447-106">Explains how to use local and remote variables in remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="11447-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="11447-107">Long description</span></span>

<span data-ttu-id="11447-108">Переменные можно использовать в командах, выполняемых на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="11447-108">You can use variables in commands that you run on remote computers.</span></span> <span data-ttu-id="11447-109">Присвойте значение переменной, а затем используйте переменную вместо значения.</span><span class="sxs-lookup"><span data-stu-id="11447-109">Assign a value to the variable and then use the variable in place of the value.</span></span>

<span data-ttu-id="11447-110">По умолчанию переменные в удаленных командах считаются определенными в сеансе, который выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="11447-110">By default, the variables in remote commands are assumed to be defined in the session that runs the command.</span></span> <span data-ttu-id="11447-111">Переменные, определенные в локальном сеансе, должны быть идентифицированы как локальные переменные в команде.</span><span class="sxs-lookup"><span data-stu-id="11447-111">Variables that are defined in a local session, must be identified as local variables in the command.</span></span>

## <a name="using-remote-variables"></a><span data-ttu-id="11447-112">Использование удаленных переменных</span><span class="sxs-lookup"><span data-stu-id="11447-112">Using remote variables</span></span>

<span data-ttu-id="11447-113">В PowerShell предполагается, что переменные, используемые в удаленных командах, определены в сеансе, в котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="11447-113">PowerShell assumes that the variables used in remote commands are defined in the session in which the command runs.</span></span>

<span data-ttu-id="11447-114">В этом примере `$ps` переменная определена во временном сеансе, в котором `Get-WinEvent` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="11447-114">In this example, the `$ps` variable is defined in the temporary session in which the `Get-WinEvent` command runs.</span></span>

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

<span data-ttu-id="11447-115">При выполнении команды в постоянном сеансе **PSSession** в этом сеансе должна быть определена удаленная переменная.</span><span class="sxs-lookup"><span data-stu-id="11447-115">When the command runs in a persistent session, **PSSession** , the remote variable must be defined in that session.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a><span data-ttu-id="11447-116">Использование локальных переменных</span><span class="sxs-lookup"><span data-stu-id="11447-116">Using local variables</span></span>

<span data-ttu-id="11447-117">Локальные переменные можно использовать в удаленных командах, но переменная должна быть определена в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="11447-117">You can use local variables in remote commands, but the variable must be defined in the local session.</span></span>

<span data-ttu-id="11447-118">Начиная с PowerShell 3,0 можно использовать `Using` Модификатор области для определения локальной переменной в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="11447-118">Beginning in PowerShell 3.0, you can use the `Using` scope modifier to identify a local variable in a remote command.</span></span>

<span data-ttu-id="11447-119">Синтаксис `Using` имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="11447-119">The syntax of `Using` is as follows:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="11447-120">В следующем примере `$ps` переменная создается в локальном сеансе, но используется в сеансе, в котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="11447-120">In the following example, the `$ps` variable is created in the local session, but is used in the session in which the command runs.</span></span> <span data-ttu-id="11447-121">`Using`Модификатор области определяет `$ps` как локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="11447-121">The `Using` scope modifier identifies `$ps` as a local variable.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

<span data-ttu-id="11447-122">`Using`Модификатор области может использоваться в **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="11447-122">The `Using` scope modifier can be used in a **PSSession**.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

<span data-ttu-id="11447-123">Ссылка на переменную, например, `$using:var` расширяется до значения переменной `$var` из контекста вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="11447-123">A variable reference such as `$using:var` expands to the value of variable `$var` from the caller's context.</span></span> <span data-ttu-id="11447-124">Вы не получаете доступ к объекту переменной вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="11447-124">You do not get access to the caller's variable object.</span></span>
<span data-ttu-id="11447-125">`Using`Модификатор области не может использоваться для изменения локальной переменной в **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="11447-125">The `Using` scope modifier cannot be used to modify a local variable within the **PSSession**.</span></span> <span data-ttu-id="11447-126">Например, следующий код не работает:</span><span class="sxs-lookup"><span data-stu-id="11447-126">For example, the following code does not work:</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

<span data-ttu-id="11447-127">Дополнительные сведения о `Using` см. в разделе [about_Scopes](./about_Scopes.md)</span><span class="sxs-lookup"><span data-stu-id="11447-127">For more information about `Using`, see [about_Scopes](./about_Scopes.md)</span></span>

### <a name="using-splatting"></a><span data-ttu-id="11447-128">Использование Сплаттинг</span><span class="sxs-lookup"><span data-stu-id="11447-128">Using splatting</span></span>

<span data-ttu-id="11447-129">Сплаттинг PowerShell передает коллекцию имен и значений параметров в команду.</span><span class="sxs-lookup"><span data-stu-id="11447-129">PowerShell splatting passes a collection of parameter names and values to a command.</span></span> <span data-ttu-id="11447-130">Дополнительные сведения см. в разделе [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="11447-130">For more information, see [about_Splatting](about_Splatting.md).</span></span>

<span data-ttu-id="11447-131">В этом примере переменная Сплаттинг `$Splat` является хэш-таблицей, настроенной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="11447-131">In this example, the splatting variable, `$Splat` is a hash table that is set up on the local computer.</span></span> <span data-ttu-id="11447-132">`Invoke-Command`Подключается к сеансу удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="11447-132">The `Invoke-Command` connects to a remote computer session.</span></span> <span data-ttu-id="11447-133">Блок **ScriptBlock** использует `Using` Модификатор области с `@` символом at () для представления переменной сплаттед.</span><span class="sxs-lookup"><span data-stu-id="11447-133">The **ScriptBlock** uses the `Using` scope modifier with the At (`@`) symbol to represent the splatted variable.</span></span>

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a><span data-ttu-id="11447-134">Другие ситуации, в которых требуется модификатор области using</span><span class="sxs-lookup"><span data-stu-id="11447-134">Other situations where the 'Using' scope modifier is needed</span></span>

<span data-ttu-id="11447-135">Для любого скрипта или команды, выполняемой вне сеанса, необходим `Using` Модификатор области для внедрения значений переменных из области вызывающего сеанса, чтобы код сеанса мог получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="11447-135">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="11447-136">`Using`Модификатор области поддерживается в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="11447-136">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="11447-137">Удаленно выполненные команды, запущенные с `Invoke-Command` использованием параметров **ComputerName** , **HostName** , **сшконнектион** или **Session** (удаленный сеанс)</span><span class="sxs-lookup"><span data-stu-id="11447-137">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="11447-138">Фоновые задания, запущенные с помощью `Start-Job` (вне процесса)</span><span class="sxs-lookup"><span data-stu-id="11447-138">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="11447-139">Задания потоков, запущенные через `Start-ThreadJob` или `ForEach-Object -Parallel` (отдельный сеанс потока)</span><span class="sxs-lookup"><span data-stu-id="11447-139">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="11447-140">В зависимости от контекста значения внедренных переменных — это либо независимые копии данных в области вызывающего объекта, либо ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="11447-140">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="11447-141">В удаленных и необработанных сеансах они всегда являются независимыми копиями.</span><span class="sxs-lookup"><span data-stu-id="11447-141">In remote and out-of-process sessions, they are always independent copies.</span></span> <span data-ttu-id="11447-142">В сеансах потока они передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="11447-142">In thread sessions, they are passed by reference.</span></span>

## <a name="serialization-of-variable-values"></a><span data-ttu-id="11447-143">Сериализация значений переменных</span><span class="sxs-lookup"><span data-stu-id="11447-143">Serialization of variable values</span></span>

<span data-ttu-id="11447-144">Удаленные команды и фоновые задания выполняются вне процесса.</span><span class="sxs-lookup"><span data-stu-id="11447-144">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="11447-145">Необработанные сеансы используют сериализацию и десериализацию на основе XML, чтобы сделать значения переменных доступными через границы процесса.</span><span class="sxs-lookup"><span data-stu-id="11447-145">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="11447-146">Процесс сериализации преобразует объекты в **PSObject** , который содержит исходные свойства объектов, но не его методы.</span><span class="sxs-lookup"><span data-stu-id="11447-146">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="11447-147">Для ограниченного набора типов десериализация восстанавливает объекты обратно в исходный тип.</span><span class="sxs-lookup"><span data-stu-id="11447-147">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="11447-148">Восстановленный объект является копией исходного экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="11447-148">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="11447-149">Он содержит свойства и методы типа.</span><span class="sxs-lookup"><span data-stu-id="11447-149">It has the type properties and methods.</span></span> <span data-ttu-id="11447-150">Для простых типов, таких как **System. Version** , копия является точной.</span><span class="sxs-lookup"><span data-stu-id="11447-150">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="11447-151">Для сложных типов копия — неидеальны.</span><span class="sxs-lookup"><span data-stu-id="11447-151">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="11447-152">Например, rehydratя объектов сертификатов не включает закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="11447-152">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="11447-153">Экземпляры всех остальных типов являются экземплярами **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="11447-153">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="11447-154">Свойство **PSTypeNames** содержит имя исходного типа с префиксом **десериализации** , например **Deserialized.SysTEM. Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="11447-154">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

## <a name="using-local-variables-with-argumentlist-parameter"></a><span data-ttu-id="11447-155">Использование локальных переменных с параметром **ArgumentList**</span><span class="sxs-lookup"><span data-stu-id="11447-155">Using local variables with **ArgumentList** parameter</span></span>

<span data-ttu-id="11447-156">Локальные переменные можно использовать в удаленной команде, определяя параметры для удаленной команды и используя параметр **ArgumentList** `Invoke-Command` командлета, чтобы указать локальную переменную в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="11447-156">You can use local variables in a remote command by defining parameters for the remote command and using the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

- <span data-ttu-id="11447-157">Используйте `param` ключевое слово для определения параметров удаленной команды.</span><span class="sxs-lookup"><span data-stu-id="11447-157">Use the `param` keyword to define parameters for the remote command.</span></span> <span data-ttu-id="11447-158">Имена параметров — это заполнители, которые не обязательно должны совпадать с именем локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="11447-158">The parameter names are placeholders that don't need to match the local variable's name.</span></span>

- <span data-ttu-id="11447-159">Используйте параметры, определенные `param` ключевым словом в команде.</span><span class="sxs-lookup"><span data-stu-id="11447-159">Use the parameters defined by the `param` keyword in the command.</span></span>

- <span data-ttu-id="11447-160">Используйте параметр **ArgumentList** `Invoke-Command` командлета, чтобы указать локальную переменную в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="11447-160">Use the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

<span data-ttu-id="11447-161">Например, следующие команды определяют `$ps` переменную в локальном сеансе и затем используют ее в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="11447-161">For example, the following commands define the `$ps` variable in the local session and then use it in a remote command.</span></span> <span data-ttu-id="11447-162">Команда использует `$log` в качестве значения имени параметра и локальной переменной `$ps` .</span><span class="sxs-lookup"><span data-stu-id="11447-162">The command uses `$log` as the parameter name and the local variable, `$ps`, as its value.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a><span data-ttu-id="11447-163">См. также статью</span><span class="sxs-lookup"><span data-stu-id="11447-163">See also</span></span>

[<span data-ttu-id="11447-164">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="11447-164">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="11447-165">about_Remote</span><span class="sxs-lookup"><span data-stu-id="11447-165">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="11447-166">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="11447-166">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="11447-167">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="11447-167">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="11447-168">about_Variables</span><span class="sxs-lookup"><span data-stu-id="11447-168">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="11447-169">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="11447-169">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="11447-170">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="11447-170">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="11447-171">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="11447-171">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="11447-172">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="11447-172">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)

@Microsoft.PowerShell.Core.ForEach-Object

