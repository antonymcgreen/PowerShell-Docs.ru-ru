---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: 1b0fbfca365e9cf369decbf4eafc0a8b4e2741bc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229173"
---
# <span data-ttu-id="4885e-103">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-103">Remove-PSSession</span></span>

## <span data-ttu-id="4885e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4885e-104">SYNOPSIS</span></span>
<span data-ttu-id="4885e-105">Закрывает один или несколько сеансов PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="4885e-105">Closes one or more PowerShell sessions (PSSessions).</span></span>

## <span data-ttu-id="4885e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4885e-106">SYNTAX</span></span>

### <span data-ttu-id="4885e-107">Id (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4885e-107">Id (Default)</span></span>

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-108">Сеанс</span><span class="sxs-lookup"><span data-stu-id="4885e-108">Session</span></span>

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-109">ContainerId</span><span class="sxs-lookup"><span data-stu-id="4885e-109">ContainerId</span></span>

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-110">VMId</span><span class="sxs-lookup"><span data-stu-id="4885e-110">VMId</span></span>

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-111">VMName</span><span class="sxs-lookup"><span data-stu-id="4885e-111">VMName</span></span>

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-112">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4885e-112">InstanceId</span></span>

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-113">name</span><span class="sxs-lookup"><span data-stu-id="4885e-113">Name</span></span>

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4885e-114">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="4885e-114">ComputerName</span></span>

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4885e-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4885e-115">DESCRIPTION</span></span>

<span data-ttu-id="4885e-116">Командлет **Remove-PSSession** Закрывает сеансы PowerShell ( **PSSession** ) в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-116">The **Remove-PSSession** cmdlet closes PowerShell sessions ( **PSSessions** ) in the current session.</span></span>
<span data-ttu-id="4885e-117">Он останавливает все команды, запущенные в **PSSession** , завершает **сеанс PSSession** и освобождает ресурсы, которые использовались в **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="4885e-117">It stops any commands that are running in the **PSSessions** , ends the **PSSession** , and releases the resources that the **PSSession** was using.</span></span>
<span data-ttu-id="4885e-118">Если **сеанс PSSession** подключен к удаленному компьютеру, этот командлет также закрывает подключение между локальным и удаленным компьютерами.</span><span class="sxs-lookup"><span data-stu-id="4885e-118">If the **PSSession** is connected to a remote computer, this cmdlet also closes the connection between the local and remote computers.</span></span>

<span data-ttu-id="4885e-119">Чтобы удалить **PSSession** , введите *имя* , *ComputerName* , *идентификатор* или *InstanceId* сеанса.</span><span class="sxs-lookup"><span data-stu-id="4885e-119">To remove a **PSSession** , enter the *Name* , *ComputerName* , *ID* , or *InstanceID* of the session.</span></span>

<span data-ttu-id="4885e-120">Если *сеанс PSSession* сохранен в переменной, то объект сеанса остается в переменной, но состояние *PSSession* закрыто.</span><span class="sxs-lookup"><span data-stu-id="4885e-120">If you have saved the *PSSession* in a variable, the session object remains in the variable, but the state of the *PSSession* is Closed.</span></span>

## <span data-ttu-id="4885e-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="4885e-121">EXAMPLES</span></span>

### <span data-ttu-id="4885e-122">Пример 1. Удаление сеансов с помощью идентификаторов</span><span class="sxs-lookup"><span data-stu-id="4885e-122">Example 1: Remove sessions by using IDs</span></span>

```powershell
Remove-PSSession -Id 1, 2
```

<span data-ttu-id="4885e-123">Эта команда удаляет **PSSession** с идентификаторами 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="4885e-123">This command removes the **PSSessions** that have IDs 1 and 2.</span></span>

### <span data-ttu-id="4885e-124">Пример 2. Удаление всех сеансов в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="4885e-124">Example 2: Remove all the sessions in the current session</span></span>

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

<span data-ttu-id="4885e-125">Эти команды удаляют все **PSSession** в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-125">These commands remove all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="4885e-126">Хотя три формата команд отличаются, они действуют одинаково.</span><span class="sxs-lookup"><span data-stu-id="4885e-126">Although the three command formats look different, they have the same effect.</span></span>

### <span data-ttu-id="4885e-127">Пример 3. закрытие сеансов с помощью имен</span><span class="sxs-lookup"><span data-stu-id="4885e-127">Example 3: Close sessions by using names</span></span>

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

<span data-ttu-id="4885e-128">Эти команды закрывают **PSSession** , подключенные к компьютерам, имена которых начинаются с серв.</span><span class="sxs-lookup"><span data-stu-id="4885e-128">These commands close the **PSSessions** that are connected to computers that have names that begin with Serv.</span></span>

### <span data-ttu-id="4885e-129">Пример 4. закрытие сеансов, подключенных к порту</span><span class="sxs-lookup"><span data-stu-id="4885e-129">Example 4: Close sessions connected to a port</span></span>

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

<span data-ttu-id="4885e-130">Эта команда закрывает **PSSession** , подключенные к порту 90.</span><span class="sxs-lookup"><span data-stu-id="4885e-130">This command closes the **PSSessions** that are connected to port 90.</span></span>
<span data-ttu-id="4885e-131">Этот формат команды можно использовать для идентификации **PSSession** по свойствам, отличным от *ComputerName* , *Name* , *InstanceId* и *ID*.</span><span class="sxs-lookup"><span data-stu-id="4885e-131">You can use this command format to identify **PSSessions** by properties other than *ComputerName* , *Name* , *InstanceID* , and *ID*.</span></span>

### <span data-ttu-id="4885e-132">Пример 5. Закрытие сеанса на основе идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="4885e-132">Example 5: Close a session based on instance ID</span></span>

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

<span data-ttu-id="4885e-133">Эти команды показывают, как закрыть **сеанс PSSession** на основе идентификатора экземпляра или **ремотерунспацеид**.</span><span class="sxs-lookup"><span data-stu-id="4885e-133">These commands show how to close a **PSSession** based on its instance ID, or **RemoteRunspaceID**.</span></span>

<span data-ttu-id="4885e-134">Первая команда использует командлет **Get-PSSession** для получения **PSSession** в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-134">The first command uses the **Get-PSSession** cmdlet to get the **PSSessions** in the current session.</span></span>
<span data-ttu-id="4885e-135">Он использует оператор конвейера (|) для отправки **PSSession** в командлет Format-Table, который форматирует свойства **ComputerName** и **InstanceId** в таблице.</span><span class="sxs-lookup"><span data-stu-id="4885e-135">It uses a pipeline operator (|) to send the **PSSessions** to the Format-Table cmdlet, which formats their **ComputerName** and **InstanceID** properties in a table.</span></span>
<span data-ttu-id="4885e-136">Параметр *AutoSize* сжимает столбцы для вывода.</span><span class="sxs-lookup"><span data-stu-id="4885e-136">The *AutoSize* parameter compresses the columns for display.</span></span>

<span data-ttu-id="4885e-137">На полученном экране можно указать, что **сеанс PSSession** должен быть закрыт, а затем скопировать и вставить *InstanceId* этого **сеанса PSSession** во вторую команду.</span><span class="sxs-lookup"><span data-stu-id="4885e-137">From the resulting display, you can identify the **PSSession** to be closed, and copy and paste the *InstanceID* of that **PSSession** into the second command.</span></span>

<span data-ttu-id="4885e-138">Вторая команда использует командлет **Remove-PSSession** для удаления *сеанса PSSession* с указанным идентификатором экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4885e-138">The second command uses the **Remove-PSSession** cmdlet to remove the *PSSession* with the specified instance ID.</span></span>

### <span data-ttu-id="4885e-139">Пример 6. Создание функции, которая удаляет все сеансы в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="4885e-139">Example 6: Create a function that deletes all sessions in the current session</span></span>

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

<span data-ttu-id="4885e-140">Эта функция удаляет все **PSSession** в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-140">This function deletes all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="4885e-141">После добавления этой функции в профиль PowerShell для удаления всех сеансов введите `EndPSS` .</span><span class="sxs-lookup"><span data-stu-id="4885e-141">After you add this function to your PowerShell profile, to delete all sessions, type `EndPSS`.</span></span>

## <span data-ttu-id="4885e-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4885e-142">PARAMETERS</span></span>

### <span data-ttu-id="4885e-143">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4885e-143">-ComputerName</span></span>

<span data-ttu-id="4885e-144">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="4885e-144">Specifies an array of names of computers.</span></span>
<span data-ttu-id="4885e-145">Этот командлет закрывает **PSSession** , подключенные к указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="4885e-145">This cmdlet closes the **PSSessions** that are connected to the specified computers.</span></span>
<span data-ttu-id="4885e-146">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4885e-146">Wildcard characters are permitted.</span></span>

<span data-ttu-id="4885e-147">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="4885e-147">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span>
<span data-ttu-id="4885e-148">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="4885e-148">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="4885e-149">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="4885e-149">-ContainerId</span></span>

<span data-ttu-id="4885e-150">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4885e-150">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="4885e-151">Этот командлет удаляет сеансы для каждого из указанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4885e-151">This cmdlet removes sessions for each of the specified containers.</span></span> <span data-ttu-id="4885e-152">Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4885e-152">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="4885e-153">Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="4885e-153">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-154">-Id</span><span class="sxs-lookup"><span data-stu-id="4885e-154">-Id</span></span>

<span data-ttu-id="4885e-155">Указывает массив идентификаторов сеансов.</span><span class="sxs-lookup"><span data-stu-id="4885e-155">Specifies an array of IDs of sessions.</span></span>
<span data-ttu-id="4885e-156">Этот командлет закрывает *PSSession* с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="4885e-156">This cmdlet closes the *PSSessions* with the specified IDs.</span></span>
<span data-ttu-id="4885e-157">Введите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range (..), чтобы указать диапазон идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="4885e-157">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="4885e-158">Идентификатор — это целое число, уникально идентифицирующее **сеанс PSSession** в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-158">An ID is an integer that uniquely identifies the **PSSession** in the current session.</span></span>
<span data-ttu-id="4885e-159">Проще запомнить и ввести, чем *InstanceId* , но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-159">It is easier to remember and type than the *InstanceId* , but it is unique only in the current session.</span></span>
<span data-ttu-id="4885e-160">Чтобы найти идентификатор **сеанса PSSession** , выполните командлет Get-PSSession без параметров.</span><span class="sxs-lookup"><span data-stu-id="4885e-160">To find the ID of a **PSSession** , run the Get-PSSession cmdlet without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-161">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="4885e-161">-InstanceId</span></span>

<span data-ttu-id="4885e-162">Указывает массив идентификаторов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4885e-162">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="4885e-163">Этот командлет закрывает **PSSession** с указанными идентификаторами экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4885e-163">This cmdlet closes the **PSSessions** that have the specified instance IDs.</span></span>

<span data-ttu-id="4885e-164">Идентификатор экземпляра — это идентификатор GUID, который однозначно определяет **сеанс PSSession** в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4885e-164">The instance ID is a GUID that uniquely identifies a **PSSession** in the current session.</span></span>
<span data-ttu-id="4885e-165">Идентификатор экземпляра уникален, даже если на одном компьютере выполняется несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="4885e-165">The instance ID is unique, even when you have multiple sessions running on a single computer.</span></span>

<span data-ttu-id="4885e-166">Идентификатор экземпляра хранится в свойстве **InstanceId** объекта, представляющего **сеанс PSSession**.</span><span class="sxs-lookup"><span data-stu-id="4885e-166">The instance ID is stored in the **InstanceID** property of the object that represents a **PSSession**.</span></span>
<span data-ttu-id="4885e-167">Чтобы найти **InstanceId** **PSSession** в текущем сеансе, введите `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .</span><span class="sxs-lookup"><span data-stu-id="4885e-167">To find the **InstanceID** of the **PSSessions** in the current session, type `Get-PSSession | Format-Table Name, ComputerName, InstanceId`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-168">-Name</span><span class="sxs-lookup"><span data-stu-id="4885e-168">-Name</span></span>

<span data-ttu-id="4885e-169">Указывает массив понятных имен сеансов.</span><span class="sxs-lookup"><span data-stu-id="4885e-169">Specifies an array of friendly names of sessions.</span></span>
<span data-ttu-id="4885e-170">Этот командлет закрывает **PSSession** с указанными понятными именами.</span><span class="sxs-lookup"><span data-stu-id="4885e-170">This cmdlet closes the **PSSessions** that have the specified friendly names.</span></span>
<span data-ttu-id="4885e-171">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4885e-171">Wildcard characters are permitted.</span></span>

<span data-ttu-id="4885e-172">Поскольку понятное имя **PSSession** может не быть уникальным, при использовании параметра *Name* рекомендуется также использовать параметр *WhatIf* или *Confirm* в команде **Remove-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="4885e-172">Because the friendly name of a **PSSession** might not be unique, when you use the *Name* parameter, consider also using the *WhatIf* or *Confirm* parameter in the **Remove-PSSession** command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="4885e-173">-Session</span><span class="sxs-lookup"><span data-stu-id="4885e-173">-Session</span></span>

<span data-ttu-id="4885e-174">Указывает объекты сеанса **PSSession** , которые нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="4885e-174">Specifies the session objects of the **PSSessions** to close.</span></span>
<span data-ttu-id="4885e-175">Введите переменную, которая содержит **PSSession** , или команду, которая создает или получает **pssession** , например New-PSSession или **Get-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="4885e-175">Enter a variable that contains the **PSSessions** or a command that creates or gets the **PSSessions** , such as a New-PSSession or **Get-PSSession** command.</span></span>
<span data-ttu-id="4885e-176">Можно также передать один или несколько объектов сеанса в командлет **Remove-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="4885e-176">You can also pipe one or more session objects to **Remove-PSSession**.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-177">— VMId</span><span class="sxs-lookup"><span data-stu-id="4885e-177">-VMId</span></span>

<span data-ttu-id="4885e-178">Указывает массив ИДЕНТИФИКАТОРов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="4885e-178">Specifies an array of ID of virtual machines.</span></span>
<span data-ttu-id="4885e-179">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="4885e-179">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="4885e-180">Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4885e-180">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-181">-VMName</span><span class="sxs-lookup"><span data-stu-id="4885e-181">-VMName</span></span>

<span data-ttu-id="4885e-182">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="4885e-182">Specifies an array of names of virtual machines.</span></span>
<span data-ttu-id="4885e-183">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="4885e-183">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="4885e-184">Чтобы просмотреть доступные виртуальные машины, используйте командлет **Get-VM** .</span><span class="sxs-lookup"><span data-stu-id="4885e-184">To see the virtual machines that are available to you, use the **Get-VM** cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4885e-185">-Confirm</span></span>

<span data-ttu-id="4885e-186">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4885e-186">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4885e-187">-WhatIf</span></span>

<span data-ttu-id="4885e-188">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4885e-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4885e-189">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4885e-189">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4885e-190">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4885e-190">CommonParameters</span></span>

<span data-ttu-id="4885e-191">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4885e-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4885e-192">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4885e-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4885e-193">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4885e-193">INPUTS</span></span>

### <span data-ttu-id="4885e-194">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-194">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="4885e-195">Объект сеанса можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4885e-195">You can pipe a session object to this cmdlet.</span></span>

## <span data-ttu-id="4885e-196">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4885e-196">OUTPUTS</span></span>

### <span data-ttu-id="4885e-197">Нет</span><span class="sxs-lookup"><span data-stu-id="4885e-197">None</span></span>

<span data-ttu-id="4885e-198">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="4885e-198">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="4885e-199">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4885e-199">NOTES</span></span>

* <span data-ttu-id="4885e-200">Параметр *ID* является обязательным.</span><span class="sxs-lookup"><span data-stu-id="4885e-200">The *Id* parameter is mandatory.</span></span> <span data-ttu-id="4885e-201">Чтобы удалить все **PSSession** в текущем сеансе, введите `Get-PSSession | Remove-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4885e-201">To delete all the **PSSessions** in the current session, type `Get-PSSession | Remove-PSSession`.</span></span>
* <span data-ttu-id="4885e-202">**Сеанс PSSession** использует постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4885e-202">A **PSSession** uses a persistent connection to a remote computer.</span></span> <span data-ttu-id="4885e-203">Создайте **сеанс PSSession** для выполнения ряда команд, которые совместно используют данные.</span><span class="sxs-lookup"><span data-stu-id="4885e-203">Create a **PSSession** to run a series of commands that share data.</span></span> <span data-ttu-id="4885e-204">Для получения дополнительных сведений введите `Get-Help about_PSSessions`.</span><span class="sxs-lookup"><span data-stu-id="4885e-204">For more information, type `Get-Help about_PSSessions`.</span></span>
* <span data-ttu-id="4885e-205">**PSSession** относятся к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="4885e-205">**PSSessions** are specific to the current session.</span></span> <span data-ttu-id="4885e-206">После завершения сеанса **PSSession** , созданный в этом сеансе, принудительно закрывается.</span><span class="sxs-lookup"><span data-stu-id="4885e-206">When you end a session, the **PSSessions** that you created in that session are forcibly closed.</span></span>

## <span data-ttu-id="4885e-207">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4885e-207">RELATED LINKS</span></span>

[<span data-ttu-id="4885e-208">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-208">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="4885e-209">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-209">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="4885e-210">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-210">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="4885e-211">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="4885e-211">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="4885e-212">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-212">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="4885e-213">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4885e-213">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="4885e-214">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-214">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="4885e-215">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="4885e-215">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="4885e-216">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="4885e-216">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="4885e-217">about_Remote</span><span class="sxs-lookup"><span data-stu-id="4885e-217">about_Remote</span></span>](About/about_Remote.md)

