---
description: Описывает сеансы PowerShell (PSSession) и объясняет, как установить постоянное подключение к удаленному компьютеру.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: 2be48b458ec156852be59d9079e8bbf50af9b499
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231685"
---
# <a name="about-pssessions"></a><span data-ttu-id="cd6aa-104">О PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-104">About PSSessions</span></span>

## <a name="short-description"></a><span data-ttu-id="cd6aa-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="cd6aa-105">Short Description</span></span>
<span data-ttu-id="cd6aa-106">Описывает сеансы PowerShell (PSSession) и объясняет, как установить постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-106">Describes PowerShell sessions (PSSessions) and explains how to establish a persistent connection to a remote computer.</span></span>

## <a name="long-description"></a><span data-ttu-id="cd6aa-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="cd6aa-107">Long Description</span></span>

<span data-ttu-id="cd6aa-108">Для выполнения команд PowerShell на удаленном компьютере можно использовать параметр **ComputerName** командлета или создать сеанс PowerShell (PSSession) и выполнить команды в PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-108">To run PowerShell commands on a remote computer, you can use the **ComputerName** parameter of a cmdlet, or you can create a PowerShell session (PSSession) and run commands in the PSSession.</span></span>

<span data-ttu-id="cd6aa-109">При создании сеанса PSSession PowerShell устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-109">When you create a PSSession, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="cd6aa-110">Используйте PSSession для выполнения серии связанных команд на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-110">Use a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="cd6aa-111">Команды, выполняемые в одном сеансе PSSession, могут совместно использовать данные, такие как значения переменных, псевдонимов и функций.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-111">Commands that run in the same PSSession can share data, such as the values of variables, aliases, and functions.</span></span>

<span data-ttu-id="cd6aa-112">Можно также создать сеанс PSSession на локальном компьютере и выполнить в нем команды.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-112">You can also create a PSSession on the local computer and run commands in it.</span></span>
<span data-ttu-id="cd6aa-113">Локальный сеанс PSSession использует инфраструктуру удаленного взаимодействия PowerShell для создания и обслуживания PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-113">A local PSSession uses the PowerShell remoting infrastructure to create and maintain the PSSession.</span></span>

<span data-ttu-id="cd6aa-114">Начиная с Windows PowerShell 3,0, PSSession не зависят от сеансов, в которых они созданы.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-114">Beginning in Windows PowerShell 3.0, PSSessions are independent of the sessions in which they are created.</span></span> <span data-ttu-id="cd6aa-115">Активные PSSession хранятся на удаленном компьютере (или на удаленном компьютере или на стороне сервера).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-115">Active PSSessions are maintained on the remote computer (or the computer at the remote end or "server-side" of the connection).</span></span> <span data-ttu-id="cd6aa-116">В результате вы можете отключиться от сеанса PSSession и повторно подключиться к нему позже с того же компьютера или с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-116">As a result, you can disconnect from the PSSession and reconnect to it at a later time from the same computer or from a different computer.</span></span>

<span data-ttu-id="cd6aa-117">В этом разделе объясняется, как создавать, использовать, получать и удалять PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-117">This topic explains how to create, use, get, and delete PSSessions.</span></span> <span data-ttu-id="cd6aa-118">Дополнительные сведения см. в разделе [about_PSSession_Details](about_PSSession_Details.md).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-118">For more advanced information, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

<span data-ttu-id="cd6aa-119">Примечание. PSSession использует инфраструктуру удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-119">Note: PSSessions use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="cd6aa-120">Чтобы использовать PSSession, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-120">To use PSSessions, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="cd6aa-121">Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-121">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

<span data-ttu-id="cd6aa-122">В Windows Vista и более поздних версиях Windows для создания сеанса PSSession на локальном компьютере необходимо запустить PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="cd6aa-122">In Windows Vista and later versions of Windows, to create a PSSession on a local computer, you must start PowerShell with the "Run as administrator" option.</span></span>

## <a name="what-is-a-session"></a><span data-ttu-id="cd6aa-123">Что такое сеанс?</span><span class="sxs-lookup"><span data-stu-id="cd6aa-123">What Is a Session?</span></span>

<span data-ttu-id="cd6aa-124">Сеанс — это среда, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-124">A session is an environment in which PowerShell runs.</span></span>

<span data-ttu-id="cd6aa-125">Каждый раз при запуске PowerShell создается сеанс, а в сеансе можно выполнять команды.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-125">Each time you start PowerShell, a session is created for you, and you can run commands in the session.</span></span> <span data-ttu-id="cd6aa-126">Можно также добавлять элементы в сеанс, например модули и оснастки, а также создавать элементы, такие как переменные, функции и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-126">You can also add items to your session, such as modules and snap-ins, and you can create items, such as variables, functions, and aliases.</span></span> <span data-ttu-id="cd6aa-127">Эти элементы существуют только в сеансе и удаляются по окончании сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-127">These items exist only in the session and are deleted when the session ends.</span></span>

<span data-ttu-id="cd6aa-128">Кроме того, можно создавать управляемые пользователем сеансы, известные как "сеансы PowerShell" или "PSSession" на локальном компьютере или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-128">You can also create user-managed sessions, known as " PowerShell sessions" or "PSSessions," on the local computer or on a remote computer.</span></span> <span data-ttu-id="cd6aa-129">Как и сеанс по умолчанию, можно выполнять команды в PSSession, а также добавлять и создавать элементы.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-129">Like the default session, you can run commands in a PSSession and add and create items.</span></span> <span data-ttu-id="cd6aa-130">Однако в отличие от сеанса, который запускается автоматически, вы можете управлять создаваемыми PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-130">However, unlike the session that starts automatically, you can control the PSSessions that you create.</span></span> <span data-ttu-id="cd6aa-131">Вы можете получать, создавать, настраивать и удалять их, отключать и повторно подключаться к ним, а также выполнять несколько команд в одном сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-131">You can get, create, configure, and remove them, disconnect and reconnect to them, and run multiple commands in the same PSSession.</span></span> <span data-ttu-id="cd6aa-132">Сеанс PSSession остается доступным до тех пор, пока вы не удалите его или не истечет время ожидания.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-132">The PSSession remains available until you delete it or it times out.</span></span>

<span data-ttu-id="cd6aa-133">Как правило, сеанс PSSession создается для выполнения последовательности связанных команд на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-133">Typically, you create a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="cd6aa-134">При создании PSSession на удаленном компьютере PowerShell устанавливает постоянное подключение к удаленному компьютеру для поддержки сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-134">When you create a PSSession on a remote computer, PowerShell establishes a persistent connection to the remote computer to support the session.</span></span>

<span data-ttu-id="cd6aa-135">Если вы используете параметр **ComputerName** `Invoke-Command` командлета или для запуска `Enter-PSSession` удаленного сеанса, PowerShell создает временный сеанс на удаленном компьютере и закрывает сеанс, как только команда завершится, либо сразу же после завершения интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-135">If you use the **ComputerName** parameter of the `Invoke-Command` or `Enter-PSSession` cmdlet to run a remote command or to start an interactive session, PowerShell creates a temporary session on the remote computer and closes the session as soon as the command is complete or as soon as the interactive session ends.</span></span> <span data-ttu-id="cd6aa-136">Вы не можете управлять этими временными сеансами, и их нельзя использовать для нескольких команд или единого интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-136">You cannot control these temporary sessions, and you cannot use them for more than a single command or a single interactive session.</span></span>

<span data-ttu-id="cd6aa-137">В PowerShell "текущий сеанс" — это сеанс, в котором вы работаете.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-137">In PowerShell, the "current session" is the session that you are working in.</span></span> <span data-ttu-id="cd6aa-138">"Текущий сеанс" может ссылаться на любой сеанс, включая временный сеанс или PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-138">The "current session" can refer to any session, including a temporary session or a PSSession.</span></span>

## <a name="why-use-a-pssession"></a><span data-ttu-id="cd6aa-139">Зачем использовать PSSession?</span><span class="sxs-lookup"><span data-stu-id="cd6aa-139">Why Use a PSSession?</span></span>

<span data-ttu-id="cd6aa-140">Используйте сеанс PSSession, если требуется постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-140">Use a PSSession when you need a persistent connection to a remote computer.</span></span>
<span data-ttu-id="cd6aa-141">С помощью PSSession можно выполнять ряд команд, которые совместно используют данные, такие как значения переменных, содержимое функции или определение псевдонима.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-141">With a PSSession, you can run a series of commands that share data, such as the value of variables, the contents of a function, or the definition of an alias.</span></span>

<span data-ttu-id="cd6aa-142">Удаленные команды можно выполнять без создания сеанса PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-142">You can run remote commands without creating a PSSession.</span></span> <span data-ttu-id="cd6aa-143">Используйте параметр **ComputerName** командлетов с удаленным включением для выполнения одной команды или ряда несвязанных команд на одном или нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-143">Use the **ComputerName** parameter of remote-enabled cmdlets to run a single command or a series of unrelated commands on one or many computers.</span></span>

<span data-ttu-id="cd6aa-144">При использовании параметра **ComputerName** в `Invoke-Command` или `Enter-PSSession` PowerShell устанавливает временное подключение к удаленному компьютеру, а затем закрывает подключение сразу после завершения команды.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-144">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection to the remote computer and then closes the connection as soon as the command is complete.</span></span> <span data-ttu-id="cd6aa-145">При закрытии соединения все создаваемые элементы данных теряются.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-145">Any data elements that you create are lost when the connection is closed.</span></span>

<span data-ttu-id="cd6aa-146">Другие командлеты, имеющие параметр **ComputerName** , например `Get-Eventlog` и `Get-WmiObject` , используют разные технологии удаленного взаимодействия для сбора данных.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-146">Other cmdlets that have a **ComputerName** parameter, such as `Get-Eventlog` and `Get-WmiObject`, use different remoting technologies to gather data.</span></span> <span data-ttu-id="cd6aa-147">Нет — создать постоянное подключение, например PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-147">None create a persistent connection like a PSSession.</span></span>

## <a name="how-to-create-a-pssession"></a><span data-ttu-id="cd6aa-148">Создание сеанса PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-148">How to Create a PSSession</span></span>

<span data-ttu-id="cd6aa-149">Чтобы создать сеанс PSSession, используйте `New-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-149">To create a PSSession, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="cd6aa-150">Чтобы создать сеанс PSSession на удаленном компьютере, используйте параметр **ComputerName** `New-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-150">To create the PSSession on a remote computer, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="cd6aa-151">Например, следующая команда создает новый сеанс PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-151">For example, the following command creates a new PSSession on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

<span data-ttu-id="cd6aa-152">При отправке команды `New-PSSession` создает сеанс PSSession и возвращает объект, представляющий сеанс PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-152">When you submit the command, `New-PSSession` creates the PSSession and returns an object that represents the PSSession.</span></span> <span data-ttu-id="cd6aa-153">Объект можно сохранить в переменной при создании сеанса PSSession или с помощью `Get-PSSession` команды, чтобы получить сеанс PSSession позднее.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-153">You can save the object in a variable when you create the PSSession, or you can use a `Get-PSSession` command to get the PSSession at a later time.</span></span>

<span data-ttu-id="cd6aa-154">Например, следующая команда создает новый сеанс PSSession на компьютере Server01 и сохраняет полученный объект в переменной $ps.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-154">For example, the following command creates a new PSSession on the Server01 computer and saves the resulting object in the $ps variable.</span></span>

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a><span data-ttu-id="cd6aa-155">Создание PSSession на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="cd6aa-155">How to Create PSSessions on Multiple Computers</span></span>

<span data-ttu-id="cd6aa-156">Чтобы создать PSSession на нескольких компьютерах, используйте параметр **ComputerName** `New-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-156">To create PSSessions on multiple computers, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="cd6aa-157">Введите имена удаленных компьютеров в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-157">Type the names of the remote computers in a comma-separated list.</span></span>

<span data-ttu-id="cd6aa-158">Например, чтобы создать PSSession на компьютерах Server01, Server02 и Server03, введите:</span><span class="sxs-lookup"><span data-stu-id="cd6aa-158">For example, to create PSSessions on the Server01, Server02, and Server03 computers, type:</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="cd6aa-159">`New-PSSession` создает один сеанс PSSession на каждом из удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-159">`New-PSSession` creates one PSSession on each of the remote computers.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="cd6aa-160">Как получить PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-160">How to Get PSSessions</span></span>

<span data-ttu-id="cd6aa-161">Чтобы получить PSSession, созданные в текущем сеансе, используйте `Get-PSSession` командлет без параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="cd6aa-161">To get the PSSessions that were created in your current session, use the `Get-PSSession` cmdlet without the **ComputerName** parameter.</span></span> <span data-ttu-id="cd6aa-162">`Get-PSSession` возвращает тот же тип объекта, который `New-PSSession` возвращает.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-162">`Get-PSSession` returns the same type of object that `New-PSSession` returns.</span></span>

<span data-ttu-id="cd6aa-163">Следующая команда получает все PSSession, созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-163">The following command gets all the PSSessions that were created in the current session.</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="cd6aa-164">По умолчанию в PSSession отображается их идентификатор и отображаемое имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-164">The default display of the PSSessions shows their ID and a default display name.</span></span> <span data-ttu-id="cd6aa-165">При создании сеанса можно назначить альтернативное отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-165">You can assign an alternate display name when you create the session.</span></span>

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

<span data-ttu-id="cd6aa-166">Можно также сохранить PSSession в переменной.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-166">You can also save the PSSessions in a variable.</span></span> <span data-ttu-id="cd6aa-167">Следующая команда получает PSSession и сохраняет их в \$ переменной ps123.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-167">The following command gets the PSSessions and saves them in the \$ps123 variable.</span></span>

```powershell
$ps123 = Get-PSSession
```

<span data-ttu-id="cd6aa-168">При использовании командлетов PSSession можно ссылаться на сеанс PSSession по его ИДЕНТИФИКАТОРу, по имени или ИДЕНТИФИКАТОРу экземпляра (идентификатор GUID).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-168">When using the PSSession cmdlets, you can refer to a PSSession by its ID, by its name, or by its instance ID (a GUID).</span></span> <span data-ttu-id="cd6aa-169">Следующая команда получает сеанс PSSession по его ИДЕНТИФИКАТОРу и сохраняет его в \$ переменной ps01.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-169">The following command gets a PSSession by its ID and saves it in the \$ps01 variable.</span></span>

```powershell
$ps01 = Get-PSSession -Id 1
```

<span data-ttu-id="cd6aa-170">Начиная с Windows PowerShell 3,0, PSSession хранятся на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-170">Beginning in Windows PowerShell 3.0, PSSessions are maintained on the remote computer.</span></span> <span data-ttu-id="cd6aa-171">Чтобы получить PSSession, созданные на определенных удаленных компьютерах, используйте параметр **ComputerName** `Get-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-171">To get PSSessions that you created on particular remote computers, use the **ComputerName** parameter of the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="cd6aa-172">Следующая команда получает PSSession, созданный на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-172">The following command gets the PSSessions that you created on the Server01 remote computer.</span></span> <span data-ttu-id="cd6aa-173">Сюда входят PSSession, созданные в текущем сеансе и в других сеансах на локальном компьютере или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-173">This includes PSSessions created in the current session and in other sessions on the local computer or other computers.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

<span data-ttu-id="cd6aa-174">В Windows PowerShell 2,0 `Get-PSSession` возвращает только PSSession, созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-174">In Windows PowerShell 2.0, `Get-PSSession` gets only the PSSessions that were created in the current session.</span></span> <span data-ttu-id="cd6aa-175">Он не получает PSSession, которые были созданы в других сеансах или на других компьютерах, даже если сеансы подключены к и работают с командами на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-175">It does not get PSSessions that were created in other sessions or on other computers, even if the sessions are connected to and are running commands on the local computer.</span></span>

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="cd6aa-176">Выполнение команд в PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-176">How to Run Commands in a PSSession</span></span>

<span data-ttu-id="cd6aa-177">Чтобы выполнить команду в одном или нескольких PSSession, используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-177">To run a command in one or more PSSessions, use the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="cd6aa-178">Используйте параметр Session, чтобы указать PSSession и параметр **ScriptBlock** для указания команды.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-178">Use the Session parameter to specify the PSSessions and the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="cd6aa-179">Например, чтобы выполнить `Get-ChildItem` команду ("Dir") в каждой из трех PSSession, сохраненных в переменной $ps 123, введите:</span><span class="sxs-lookup"><span data-stu-id="cd6aa-179">For example, to run a `Get-ChildItem` ("dir") command in each of the three PSSessions saved in the $ps123 variable, type:</span></span>

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a><span data-ttu-id="cd6aa-180">Удаление PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-180">How to Delete PSSessions</span></span>

<span data-ttu-id="cd6aa-181">По завершении работы с PSSession используйте `Remove-PSSession` командлет, чтобы удалить PSSession и освободить используемые им ресурсы.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-181">When you are finished with the PSSession, use the `Remove-PSSession` cmdlet to delete the PSSession and to release the resources that it was using.</span></span>

```powershell
Remove-PSSession -Session $ps
```

<span data-ttu-id="cd6aa-182">or</span><span class="sxs-lookup"><span data-stu-id="cd6aa-182">or</span></span>

```powershell
Remove-PSSession -Id 1
```

<span data-ttu-id="cd6aa-183">Чтобы удалить сеанс PSSession с удаленного компьютера, используйте параметр **ComputerName** `Remove-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-183">To remove a PSSession from a remote computer, use the **ComputerName** parameter of the `Remove-PSSession` cmdlet.</span></span>

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

<span data-ttu-id="cd6aa-184">Если не удалить PSSession, то сеанс PSSession остается доступным для использования до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-184">If you do not delete the PSSession, the PSSession remains available for use until it times out.</span></span>

<span data-ttu-id="cd6aa-185">Можно также использовать параметр **IdleTimeout** `New-PSSessionOption` командлета, чтобы установить срок действия для неактивного сеанса PSSession.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-185">You can also use the **IdleTimeout** parameter of the `New-PSSessionOption` cmdlet to set an expiration time for an idle PSSession.</span></span> <span data-ttu-id="cd6aa-186">Дополнительные сведения см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-186">For more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="the-pssession-cmdlets"></a><span data-ttu-id="cd6aa-187">Командлеты PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-187">The PSSession Cmdlets</span></span>

<span data-ttu-id="cd6aa-188">Чтобы получить список командлетов PSSession, введите:</span><span class="sxs-lookup"><span data-stu-id="cd6aa-188">For a list of PSSession cmdlets, type:</span></span>

```powershell
Get-Help *-PSSession
```

- <span data-ttu-id="cd6aa-189">Connect-PSSession: подключает сеанс PSSession к текущему сеансу</span><span class="sxs-lookup"><span data-stu-id="cd6aa-189">Connect-PSSession: Connects a PSSession to the current session</span></span>
- <span data-ttu-id="cd6aa-190">Disconnect-PSSession: отключает сеанс PSSession от текущего сеанса</span><span class="sxs-lookup"><span data-stu-id="cd6aa-190">Disconnect-PSSession: Disconnects a PSSession from the current session</span></span>
- <span data-ttu-id="cd6aa-191">Enter-PSSession: запускает интерактивный сеанс</span><span class="sxs-lookup"><span data-stu-id="cd6aa-191">Enter-PSSession: Starts an interactive session</span></span>
- <span data-ttu-id="cd6aa-192">Exit-PSSession: завершает интерактивный сеанс</span><span class="sxs-lookup"><span data-stu-id="cd6aa-192">Exit-PSSession: Ends an interactive session</span></span>
- <span data-ttu-id="cd6aa-193">Get-PSSession: получает PSSession в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="cd6aa-193">Get-PSSession: Gets the PSSessions in the current session</span></span>
- <span data-ttu-id="cd6aa-194">New-PSSession: создает новый сеанс PSSession на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-194">New-PSSession: Creates a new PSSession on a local or remote computer</span></span>
- <span data-ttu-id="cd6aa-195">Receive-PSSession: получение результатов команд, которые выполнялись в отключенном сеансе</span><span class="sxs-lookup"><span data-stu-id="cd6aa-195">Receive-PSSession: Gets the results of commands that ran in a disconnected session</span></span>
- <span data-ttu-id="cd6aa-196">Remove-PSSession: удаляет PSSession в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="cd6aa-196">Remove-PSSession: Deletes the PSSessions in the current session</span></span>

## <a name="for-more-information"></a><span data-ttu-id="cd6aa-197">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="cd6aa-197">For More Information</span></span>

<span data-ttu-id="cd6aa-198">Дополнительные сведения о PSSession см. в разделе [about_PSSession_Details](about_PSSession_Details.md).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-198">For more information about PSSessions, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd6aa-199">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd6aa-199">See Also</span></span>

[<span data-ttu-id="cd6aa-200">about_Remote</span><span class="sxs-lookup"><span data-stu-id="cd6aa-200">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="cd6aa-201">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="cd6aa-201">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="cd6aa-202">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="cd6aa-202">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="cd6aa-203">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-203">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="cd6aa-204">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-204">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="cd6aa-205">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-205">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="cd6aa-206">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="cd6aa-206">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[<span data-ttu-id="cd6aa-207">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-207">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="cd6aa-208">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cd6aa-208">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="cd6aa-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-209">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="cd6aa-210">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="cd6aa-210">Remove-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSession)

