---
description: Описывает политики выполнения PowerShell и способы управления ими.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 6c2d4b784c68649ea88e744a9cf5df6329ac897f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231694"
---
# <a name="about-execution-policies"></a><span data-ttu-id="34dc2-104">Общие сведения о политиках выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-104">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="34dc2-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="34dc2-105">Short Description</span></span>
<span data-ttu-id="34dc2-106">Описывает политики выполнения PowerShell и способы управления ими.</span><span class="sxs-lookup"><span data-stu-id="34dc2-106">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="34dc2-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="34dc2-107">Long Description</span></span>

<span data-ttu-id="34dc2-108">Политика выполнения PowerShell — это функция безопасности, которая управляет условиями, при которых PowerShell загружает файлы конфигурации и запускает сценарии.</span><span class="sxs-lookup"><span data-stu-id="34dc2-108">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="34dc2-109">Эта функция помогает предотвратить выполнение вредоносных сценариев.</span><span class="sxs-lookup"><span data-stu-id="34dc2-109">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="34dc2-110">На компьютере Windows можно задать политику выполнения для локального компьютера, для текущего пользователя или для конкретного сеанса.</span><span class="sxs-lookup"><span data-stu-id="34dc2-110">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="34dc2-111">Можно также использовать параметр групповая политика, чтобы задать политики выполнения для компьютеров и пользователей.</span><span class="sxs-lookup"><span data-stu-id="34dc2-111">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="34dc2-112">Политики выполнения для локального компьютера и текущего пользователя хранятся в реестре.</span><span class="sxs-lookup"><span data-stu-id="34dc2-112">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="34dc2-113">В профиле PowerShell не нужно задавать политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-113">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="34dc2-114">Политика выполнения для определенного сеанса сохраняется только в памяти и теряется при закрытии сеанса.</span><span class="sxs-lookup"><span data-stu-id="34dc2-114">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="34dc2-115">Политика выполнения не является системой безопасности, которая ограничивают действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dc2-115">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="34dc2-116">Например, пользователи могут без труда обходить политику, вводя содержимое скрипта в командной строке, если не удается выполнить сценарий.</span><span class="sxs-lookup"><span data-stu-id="34dc2-116">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="34dc2-117">Вместо этого политика выполнения помогает пользователям задавать основные правила и запрещает их непреднамеренное нарушение.</span><span class="sxs-lookup"><span data-stu-id="34dc2-117">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

<span data-ttu-id="34dc2-118">На компьютерах, отличных от Windows, политика выполнения по умолчанию не **ограничена** и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="34dc2-118">On non-Windows computers, the default execution policy is **Unrestricted** and cannot be changed.</span></span> <span data-ttu-id="34dc2-119">`Set-ExecutionPolicy`Командлет доступен, но PowerShell отображает сообщение консоли, которое не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="34dc2-119">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span> <span data-ttu-id="34dc2-120">Несмотря `Get-ExecutionPolicy` на то, **что функция** возвращает **неограниченные** на платформах, отличных от Windows, поведение действительно соответствует обходу, поскольку эти платформы не реализуют зоны безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="34dc2-120">While `Get-ExecutionPolicy` returns **Unrestricted** on non-Windows platforms, the behavior really matches **Bypass** because those platforms do not implement the Windows Security Zones.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="34dc2-121">Политики выполнения PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dc2-121">PowerShell execution policies</span></span>

<span data-ttu-id="34dc2-122">Принудительное применение этих политик выполняется только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="34dc2-122">Enforcement of these policies only occurs on Windows platforms.</span></span> <span data-ttu-id="34dc2-123">Ниже перечислены политики выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dc2-123">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="34dc2-124">AllSigned</span><span class="sxs-lookup"><span data-stu-id="34dc2-124">AllSigned</span></span>

- <span data-ttu-id="34dc2-125">Сценарии могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="34dc2-125">Scripts can run.</span></span>
- <span data-ttu-id="34dc2-126">требует, чтобы все скрипты и файлы конфигурации, включая скрипты, подготовленные на локальном компьютере, были подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="34dc2-126">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="34dc2-127">Выводит приглашение перед запуском скриптов от издателей, которые еще не классифицированы как доверенные или ненадежные.</span><span class="sxs-lookup"><span data-stu-id="34dc2-127">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="34dc2-128">Риски, в которых выполняются подписанные, но вредоносные сценарии.</span><span class="sxs-lookup"><span data-stu-id="34dc2-128">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="34dc2-129">обход проверки.</span><span class="sxs-lookup"><span data-stu-id="34dc2-129">Bypass</span></span>

- <span data-ttu-id="34dc2-130">ничего не блокируется, и никакие предупреждения и запросы не появляются.</span><span class="sxs-lookup"><span data-stu-id="34dc2-130">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="34dc2-131">Эта политика выполнения предназначена для конфигураций, в которых сценарий PowerShell встроен в более крупное приложение, или для конфигураций, в которых PowerShell является основой для программы, имеющей собственную модель безопасности.</span><span class="sxs-lookup"><span data-stu-id="34dc2-131">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="34dc2-132">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="34dc2-132">Default</span></span>

- <span data-ttu-id="34dc2-133">Задает политику выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34dc2-133">Sets the default execution policy.</span></span>
- <span data-ttu-id="34dc2-134">**Ограничено** для клиентов Windows.</span><span class="sxs-lookup"><span data-stu-id="34dc2-134">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="34dc2-135">**RemoteSigned** для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="34dc2-135">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="34dc2-136">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="34dc2-136">RemoteSigned</span></span>

- <span data-ttu-id="34dc2-137">Политика выполнения по умолчанию для компьютеров Windows Server.</span><span class="sxs-lookup"><span data-stu-id="34dc2-137">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="34dc2-138">Сценарии могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="34dc2-138">Scripts can run.</span></span>
- <span data-ttu-id="34dc2-139">Требуется цифровая подпись от доверенного издателя для сценариев и файлов конфигурации, загружаемых из Интернета, которые включают программы электронной почты и мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-139">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="34dc2-140">Не требует цифровых подписей для сценариев, которые записываются на локальном компьютере и не загружаются из Интернета.</span><span class="sxs-lookup"><span data-stu-id="34dc2-140">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="34dc2-141">Запускает скрипты, скачанные из Интернета и не подписанные, если скрипты разблокированы, например с помощью `Unblock-File` командлета.</span><span class="sxs-lookup"><span data-stu-id="34dc2-141">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="34dc2-142">Риски запуска неподписанных скриптов из источников, отличных от Интернета, и подписанных сценариев, которые могут быть вредоносными.</span><span class="sxs-lookup"><span data-stu-id="34dc2-142">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="34dc2-143">С ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="34dc2-143">Restricted</span></span>

- <span data-ttu-id="34dc2-144">Политика выполнения по умолчанию для клиентских компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="34dc2-144">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="34dc2-145">Разрешает отдельные команды, но не разрешает сценарии.</span><span class="sxs-lookup"><span data-stu-id="34dc2-145">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="34dc2-146">Предотвращает запуск всех файлов скриптов, включая файлы форматирования и конфигурации ( `.ps1xml` ), файлы скриптов модуля ( `.psm1` ) и профили PowerShell ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="34dc2-146">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="34dc2-147">Не определено.</span><span class="sxs-lookup"><span data-stu-id="34dc2-147">Undefined</span></span>

- <span data-ttu-id="34dc2-148">В текущей области не задана политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-148">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="34dc2-149">Если политика выполнения во всех областях не **определена** , действующая политика выполнения **ограничена** для клиентов Windows и **RemoteSigned** для Windows Server.</span><span class="sxs-lookup"><span data-stu-id="34dc2-149">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="34dc2-150">С неограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="34dc2-150">Unrestricted</span></span>

- <span data-ttu-id="34dc2-151">Политика выполнения по умолчанию для компьютеров, отличных от Windows, и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="34dc2-151">The default execution policy for non-Windows computers and cannot be changed.</span></span>
- <span data-ttu-id="34dc2-152">Неподписанные скрипты могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="34dc2-152">Unsigned scripts can run.</span></span> <span data-ttu-id="34dc2-153">Существует риск запуска вредоносных сценариев.</span><span class="sxs-lookup"><span data-stu-id="34dc2-153">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="34dc2-154">Предупреждает пользователя перед запуском скриптов и файлов конфигурации, которые не входят в зону местной интрасети.</span><span class="sxs-lookup"><span data-stu-id="34dc2-154">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="34dc2-155">В системах, которые не отличают пути UNC от Интернет-путей, сценарии, определяемые путем UNC, могут быть запрещены для выполнения с политикой выполнения **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-155">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="34dc2-156">Область политики выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-156">Execution policy scope</span></span>

<span data-ttu-id="34dc2-157">Можно задать политику выполнения, действующую только в определенной области.</span><span class="sxs-lookup"><span data-stu-id="34dc2-157">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="34dc2-158">Допустимые значения для **Scope** : **мачинеполици** , **UserPolicy** , **Process** , **CurrentUser** и **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-158">The valid values for **Scope** are **MachinePolicy** , **UserPolicy** , **Process** , **CurrentUser** , and **LocalMachine** .</span></span> <span data-ttu-id="34dc2-159">**Хранилище LocalMachine** используется по умолчанию при задании политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-159">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="34dc2-160">Значения **области** перечислены в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="34dc2-160">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="34dc2-161">Политика, которая имеет приоритет, вступает в силу в текущем сеансе, даже если более ограничивающая политика была установлена на более низком уровне приоритета.</span><span class="sxs-lookup"><span data-stu-id="34dc2-161">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="34dc2-162">Дополнительные сведения см. в разделе [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span><span class="sxs-lookup"><span data-stu-id="34dc2-162">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="34dc2-163">мачинеполици</span><span class="sxs-lookup"><span data-stu-id="34dc2-163">MachinePolicy</span></span>

<span data-ttu-id="34dc2-164">Задается групповая политика для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="34dc2-164">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="34dc2-165">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="34dc2-165">UserPolicy</span></span>

<span data-ttu-id="34dc2-166">Задается групповая политика для текущего пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="34dc2-166">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="34dc2-167">Процесс</span><span class="sxs-lookup"><span data-stu-id="34dc2-167">Process</span></span>

<span data-ttu-id="34dc2-168">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dc2-168">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="34dc2-169">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` , а не в реестре.</span><span class="sxs-lookup"><span data-stu-id="34dc2-169">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="34dc2-170">При закрытии сеанса PowerShell переменная и значение удаляются.</span><span class="sxs-lookup"><span data-stu-id="34dc2-170">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="34dc2-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="34dc2-171">CurrentUser</span></span>

<span data-ttu-id="34dc2-172">политика выполнения распространяется только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dc2-172">The execution policy affects only the current user.</span></span> <span data-ttu-id="34dc2-173">Он хранится в подразделе реестра **HKEY_CURRENT_USER** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-173">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="34dc2-174">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="34dc2-174">LocalMachine</span></span>

<span data-ttu-id="34dc2-175">Политика выполнения влияет на всех пользователей на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="34dc2-175">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="34dc2-176">Он хранится в подразделе реестра **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-176">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="34dc2-177">Управление политикой выполнения с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dc2-177">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="34dc2-178">Чтобы получить действующую политику выполнения для текущего сеанса PowerShell, используйте `Get-ExecutionPolicy` командлет.</span><span class="sxs-lookup"><span data-stu-id="34dc2-178">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="34dc2-179">Следующая команда получает действующую политику выполнения:</span><span class="sxs-lookup"><span data-stu-id="34dc2-179">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="34dc2-180">Чтобы получить все политики выполнения, влияющие на текущий сеанс, и отобразить их в порядке очередности:</span><span class="sxs-lookup"><span data-stu-id="34dc2-180">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="34dc2-181">Результат выглядит примерно так, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="34dc2-181">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="34dc2-182">В этом случае действующая политика выполнения — **RemoteSigned** , так как политика выполнения для текущего пользователя имеет приоритет над политикой выполнения, заданной для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="34dc2-182">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="34dc2-183">Чтобы получить политику выполнения, заданную для определенной области, используйте параметр **Scope** объекта `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="34dc2-183">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="34dc2-184">Например, следующая команда возвращает политику выполнения для области **CurrentUser** :</span><span class="sxs-lookup"><span data-stu-id="34dc2-184">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="34dc2-185">Изменение политики выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-185">Change the execution policy</span></span>

<span data-ttu-id="34dc2-186">Чтобы изменить политику выполнения PowerShell на компьютере Windows, используйте `Set-ExecutionPolicy` командлет.</span><span class="sxs-lookup"><span data-stu-id="34dc2-186">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="34dc2-187">Изменение вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="34dc2-187">The change is effective immediately.</span></span> <span data-ttu-id="34dc2-188">Вам не нужно перезапускать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dc2-188">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="34dc2-189">Если задать политику выполнения для областей **LocalMachine** или **CurrentUser** , это изменение будет сохранено в реестре и останется эффективным, пока вы не измените его.</span><span class="sxs-lookup"><span data-stu-id="34dc2-189">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser** , the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="34dc2-190">Если задать политику выполнения для области **процесса** , она не будет сохранена в реестре.</span><span class="sxs-lookup"><span data-stu-id="34dc2-190">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="34dc2-191">Политика выполнения сохраняется до закрытия текущего процесса и любых дочерних процессов.</span><span class="sxs-lookup"><span data-stu-id="34dc2-191">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="34dc2-192">В Windows Vista и более поздних версиях Windows для выполнения команд, изменяющих политику выполнения для локального компьютера, область **LocalMachine** , запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-192">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="34dc2-193">Чтобы изменить политику выполнения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34dc2-193">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="34dc2-194">Пример:</span><span class="sxs-lookup"><span data-stu-id="34dc2-194">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="34dc2-195">Чтобы задать политику выполнения в определенной области, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34dc2-195">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="34dc2-196">Пример:</span><span class="sxs-lookup"><span data-stu-id="34dc2-196">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="34dc2-197">Команда для изменения политики выполнения может быть выполнена, но не будет изменена действующая политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-197">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="34dc2-198">Например, команда, которая задает политику выполнения для локального компьютера, может быть выполнена, но переопределена политикой выполнения для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dc2-198">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="34dc2-199">Удаление политики выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-199">Remove the execution policy</span></span>

<span data-ttu-id="34dc2-200">Чтобы удалить политику выполнения для определенной области, задайте для политики выполнения значение **undefine** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-200">To remove the execution policy for a particular scope, set the execution policy to **Undefined** .</span></span>

<span data-ttu-id="34dc2-201">Например, чтобы удалить политику выполнения для всех пользователей локального компьютера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34dc2-201">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="34dc2-202">Чтобы удалить политику выполнения для **области** , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34dc2-202">To remove the execution policy for a **Scope** :</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="34dc2-203">Если в какой-либо области не задана политика выполнения, действующая политика выполнения **ограничена** , что является значением по умолчанию для клиентов Windows.</span><span class="sxs-lookup"><span data-stu-id="34dc2-203">If no execution policy is set in any scope, the effective execution policy is **Restricted** , which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="34dc2-204">Задание другой политики для одного сеанса</span><span class="sxs-lookup"><span data-stu-id="34dc2-204">Set a different policy for one session</span></span>

<span data-ttu-id="34dc2-205">Чтобы задать политику выполнения для нового сеанса PowerShell, можно использовать параметр **ExecutionPolicy** **pwsh.exe** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-205">You can use the **ExecutionPolicy** parameter of **pwsh.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="34dc2-206">Политика влияет только на текущий сеанс и дочерние сеансы.</span><span class="sxs-lookup"><span data-stu-id="34dc2-206">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="34dc2-207">Чтобы задать политику выполнения для нового сеанса, запустите PowerShell из командной строки, например **cmd.exe** или PowerShell, а затем используйте параметр **ExecutionPolicy** из **pwsh.exe** , чтобы задать политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-207">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **pwsh.exe** to set the execution policy.</span></span>

<span data-ttu-id="34dc2-208">Пример:</span><span class="sxs-lookup"><span data-stu-id="34dc2-208">For example:</span></span>

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="34dc2-209">Заданная политика выполнения не хранится в реестре.</span><span class="sxs-lookup"><span data-stu-id="34dc2-209">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="34dc2-210">Вместо этого он хранится в `$env:PSExecutionPolicyPreference` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="34dc2-210">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="34dc2-211">Переменная удаляется при закрытии сеанса, в котором задана политика.</span><span class="sxs-lookup"><span data-stu-id="34dc2-211">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="34dc2-212">Вы не можете изменить политику, изменив значение переменной.</span><span class="sxs-lookup"><span data-stu-id="34dc2-212">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="34dc2-213">Во время сеанса политика выполнения, заданная для сеанса, имеет приоритет над политикой выполнения, заданной в реестре для локального компьютера или текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dc2-213">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="34dc2-214">Однако он не имеет приоритета над политикой выполнения, заданной с помощью групповая политика.</span><span class="sxs-lookup"><span data-stu-id="34dc2-214">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="34dc2-215">Использование групповая политика для управления политикой выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-215">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="34dc2-216">Для управления политикой выполнения компьютеров предприятия можно использовать параметр групповая политика **включить выполнение скрипта** .</span><span class="sxs-lookup"><span data-stu-id="34dc2-216">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="34dc2-217">Параметр групповая политика переопределяет политики выполнения, заданные в PowerShell во всех областях.</span><span class="sxs-lookup"><span data-stu-id="34dc2-217">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="34dc2-218">Включить параметры политики **выполнения сценария** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="34dc2-218">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="34dc2-219">Если отключить **выполнение скрипта** , скрипты не будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="34dc2-219">If you disable **Turn on Script Execution** , scripts do not run.</span></span> <span data-ttu-id="34dc2-220">Это эквивалентно **ограниченной** политике выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-220">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="34dc2-221">Если включить **выполнение скрипта** , можно выбрать политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-221">If you enable **Turn on Script Execution** , you can select an execution policy.</span></span> <span data-ttu-id="34dc2-222">Параметры групповая политика эквивалентны следующим параметрам политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-222">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="34dc2-223">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="34dc2-223">Group Policy</span></span>                                  | <span data-ttu-id="34dc2-224">Политика выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-224">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="34dc2-225">Разрешить все скрипты</span><span class="sxs-lookup"><span data-stu-id="34dc2-225">Allow all scripts</span></span>                             | <span data-ttu-id="34dc2-226">С неограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="34dc2-226">Unrestricted</span></span>     |
  | <span data-ttu-id="34dc2-227">Разрешить локальные скрипты и удаленные подписанные скрипты</span><span class="sxs-lookup"><span data-stu-id="34dc2-227">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="34dc2-228">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="34dc2-228">RemoteSigned</span></span>     |
  | <span data-ttu-id="34dc2-229">Разрешить только подписанные скрипты</span><span class="sxs-lookup"><span data-stu-id="34dc2-229">Allow only signed scripts</span></span>                     | <span data-ttu-id="34dc2-230">AllSigned</span><span class="sxs-lookup"><span data-stu-id="34dc2-230">AllSigned</span></span>        |

- <span data-ttu-id="34dc2-231">Если параметр **включить выполнение скрипта** не настроен, он не будет действовать.</span><span class="sxs-lookup"><span data-stu-id="34dc2-231">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="34dc2-232">Политика выполнения, заданная в PowerShell, вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="34dc2-232">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="34dc2-233">Файлы Повершеллексекутионполици. adm и Повершеллексекутионполици. ADMX добавляют политику **выполнения сценария включения** в узлы Конфигурация компьютера и Конфигурация пользователя в групповая политика Editor по следующим путям.</span><span class="sxs-lookup"><span data-stu-id="34dc2-233">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="34dc2-234">Для Windows XP и Windows Server 2003:</span><span class="sxs-lookup"><span data-stu-id="34dc2-234">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="34dc2-235">Административные шаблоны управления Windows — PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dc2-235">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="34dc2-236">Для Windows Vista и более поздних версий Windows:</span><span class="sxs-lookup"><span data-stu-id="34dc2-236">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="34dc2-237">Администрирование Темплатес\классик административные шаблоны </span><span class="sxs-lookup"><span data-stu-id="34dc2-237">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="34dc2-238">Windows \ PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dc2-238">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="34dc2-239">Политики, заданные в узле Конфигурация компьютера, имеют приоритет над политиками, заданными в узле Конфигурация пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dc2-239">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="34dc2-240">Дополнительные сведения см. в статье [О параметрах групповой политики](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="34dc2-240">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="34dc2-241">Приоритет политики выполнения</span><span class="sxs-lookup"><span data-stu-id="34dc2-241">Execution policy precedence</span></span>

<span data-ttu-id="34dc2-242">При определении действующей политики выполнения для сеанса PowerShell оценивает политики выполнения в следующем порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="34dc2-242">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="34dc2-243">Групповая политика: Мачинеполици</span><span class="sxs-lookup"><span data-stu-id="34dc2-243">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="34dc2-244">Групповая политика: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="34dc2-244">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="34dc2-245">Политика выполнения: процесс (или `pwsh.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="34dc2-245">Execution Policy: Process (or `pwsh.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="34dc2-246">Политика выполнения: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="34dc2-246">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="34dc2-247">Политика выполнения: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="34dc2-247">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="34dc2-248">Управление подписанными и неподписанными скриптами</span><span class="sxs-lookup"><span data-stu-id="34dc2-248">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="34dc2-249">В Windows такие программы, как Internet Explorer и Microsoft ребр, добавляют альтернативный поток данных к загруженным файлам.</span><span class="sxs-lookup"><span data-stu-id="34dc2-249">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="34dc2-250">Этот файл помечается как «поступающий из Интернета».</span><span class="sxs-lookup"><span data-stu-id="34dc2-250">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="34dc2-251">Если политика выполнения PowerShell — **RemoteSigned** , PowerShell не будет запускать неподписанные сценарии, которые загружаются из Интернета, в том числе программы электронной почты и обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="34dc2-251">If your PowerShell execution policy is **RemoteSigned** , PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="34dc2-252">Вы можете подписать сценарий или выбрать Запуск неподписанного скрипта без изменения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="34dc2-252">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="34dc2-253">Начиная с версии PowerShell 3,0 можно использовать параметр **Stream** `Get-Item` командлета для обнаружения заблокированных файлов, так как они были загружены из Интернета.</span><span class="sxs-lookup"><span data-stu-id="34dc2-253">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="34dc2-254">Используйте `Unblock-File` командлет, чтобы разблокировать скрипты, чтобы их можно было запускать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dc2-254">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="34dc2-255">Дополнительные сведения см. в разделе [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)и [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span><span class="sxs-lookup"><span data-stu-id="34dc2-255">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="34dc2-256">Другие методы загрузки файлов могут не помечать файлы как поступающие из зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="34dc2-256">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="34dc2-257">Некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="34dc2-257">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="34dc2-258">Политика выполнения в Windows Server Core и в окне Nano Server</span><span class="sxs-lookup"><span data-stu-id="34dc2-258">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="34dc2-259">Когда PowerShell 6 запускается на Windows Server Core или Windows Nano Server при определенных условиях, политики выполнения могут завершиться со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="34dc2-259">When PowerShell 6 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="34dc2-260">PowerShell использует интерфейсы API в оболочке Windows Desktop Shell ( `explorer.exe` ) для проверки зоны файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="34dc2-260">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="34dc2-261">Оболочка Windows недоступна в Windows Server Core и Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="34dc2-261">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="34dc2-262">Эту ошибку также можно получить в любой системе Windows, если оболочка Windows для настольных компьютеров недоступна или не отвечает.</span><span class="sxs-lookup"><span data-stu-id="34dc2-262">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="34dc2-263">Например, во время входа сценарий входа PowerShell может начать выполнение до того, как рабочий стол Windows будет готов, что приведет к сбою.</span><span class="sxs-lookup"><span data-stu-id="34dc2-263">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="34dc2-264">При использовании политики выполнения **обхода** или **AllSigned** не требуется проверка зоны, которая позволяет избежать проблемы.</span><span class="sxs-lookup"><span data-stu-id="34dc2-264">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="34dc2-265">См. также:</span><span class="sxs-lookup"><span data-stu-id="34dc2-265">See Also</span></span>

[<span data-ttu-id="34dc2-266">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="34dc2-266">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="34dc2-267">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="34dc2-267">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="34dc2-268">about_Signing</span><span class="sxs-lookup"><span data-stu-id="34dc2-268">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="34dc2-269">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="34dc2-269">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="34dc2-270">Get-Item</span><span class="sxs-lookup"><span data-stu-id="34dc2-270">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="34dc2-271">Справка по консоли Pwsh</span><span class="sxs-lookup"><span data-stu-id="34dc2-271">Pwsh Console Help</span></span>](about_pwsh.md)

[<span data-ttu-id="34dc2-272">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="34dc2-272">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="34dc2-273">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="34dc2-273">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)

