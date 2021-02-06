---
description: Описывает политики выполнения PowerShell и способы управления ими.
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 1a2b8458b39233f96d47a52e3fea21b31e9b3c42
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604230"
---
# <a name="about-execution-policies"></a><span data-ttu-id="74c29-103">Общие сведения о политиках выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-103">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="74c29-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="74c29-104">Short Description</span></span>
<span data-ttu-id="74c29-105">Описывает политики выполнения PowerShell и способы управления ими.</span><span class="sxs-lookup"><span data-stu-id="74c29-105">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="74c29-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="74c29-106">Long Description</span></span>

<span data-ttu-id="74c29-107">Политика выполнения PowerShell — это функция безопасности, которая управляет условиями, при которых PowerShell загружает файлы конфигурации и запускает сценарии.</span><span class="sxs-lookup"><span data-stu-id="74c29-107">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="74c29-108">Эта функция помогает предотвратить выполнение вредоносных сценариев.</span><span class="sxs-lookup"><span data-stu-id="74c29-108">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="74c29-109">На компьютере Windows можно задать политику выполнения для локального компьютера, для текущего пользователя или для конкретного сеанса.</span><span class="sxs-lookup"><span data-stu-id="74c29-109">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="74c29-110">Можно также использовать параметр групповая политика, чтобы задать политики выполнения для компьютеров и пользователей.</span><span class="sxs-lookup"><span data-stu-id="74c29-110">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="74c29-111">Политики выполнения для локального компьютера и текущего пользователя хранятся в реестре.</span><span class="sxs-lookup"><span data-stu-id="74c29-111">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="74c29-112">В профиле PowerShell не нужно задавать политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-112">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="74c29-113">Политика выполнения для определенного сеанса сохраняется только в памяти и теряется при закрытии сеанса.</span><span class="sxs-lookup"><span data-stu-id="74c29-113">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="74c29-114">Политика выполнения не является системой безопасности, которая ограничивают действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="74c29-114">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="74c29-115">Например, пользователи могут без труда обходить политику, вводя содержимое скрипта в командной строке, если не удается выполнить сценарий.</span><span class="sxs-lookup"><span data-stu-id="74c29-115">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="74c29-116">Вместо этого политика выполнения помогает пользователям задавать основные правила и запрещает их непреднамеренное нарушение.</span><span class="sxs-lookup"><span data-stu-id="74c29-116">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

<span data-ttu-id="74c29-117">На компьютерах, отличных от Windows, политика выполнения по умолчанию не **ограничена** и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="74c29-117">On non-Windows computers, the default execution policy is **Unrestricted** and cannot be changed.</span></span> <span data-ttu-id="74c29-118">`Set-ExecutionPolicy`Командлет доступен, но PowerShell отображает сообщение консоли, которое не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="74c29-118">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span> <span data-ttu-id="74c29-119">Несмотря `Get-ExecutionPolicy` на то, **что функция** возвращает **неограниченные** на платформах, отличных от Windows, поведение действительно соответствует обходу, поскольку эти платформы не реализуют зоны безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="74c29-119">While `Get-ExecutionPolicy` returns **Unrestricted** on non-Windows platforms, the behavior really matches **Bypass** because those platforms do not implement the Windows Security Zones.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="74c29-120">Политики выполнения PowerShell</span><span class="sxs-lookup"><span data-stu-id="74c29-120">PowerShell execution policies</span></span>

<span data-ttu-id="74c29-121">Принудительное применение этих политик выполняется только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="74c29-121">Enforcement of these policies only occurs on Windows platforms.</span></span> <span data-ttu-id="74c29-122">Ниже перечислены политики выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74c29-122">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="74c29-123">AllSigned</span><span class="sxs-lookup"><span data-stu-id="74c29-123">AllSigned</span></span>

- <span data-ttu-id="74c29-124">Сценарии могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="74c29-124">Scripts can run.</span></span>
- <span data-ttu-id="74c29-125">требует, чтобы все скрипты и файлы конфигурации, включая скрипты, подготовленные на локальном компьютере, были подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="74c29-125">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="74c29-126">Выводит приглашение перед запуском скриптов от издателей, которые еще не классифицированы как доверенные или ненадежные.</span><span class="sxs-lookup"><span data-stu-id="74c29-126">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="74c29-127">Риски, в которых выполняются подписанные, но вредоносные сценарии.</span><span class="sxs-lookup"><span data-stu-id="74c29-127">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="74c29-128">обход проверки.</span><span class="sxs-lookup"><span data-stu-id="74c29-128">Bypass</span></span>

- <span data-ttu-id="74c29-129">ничего не блокируется, и никакие предупреждения и запросы не появляются.</span><span class="sxs-lookup"><span data-stu-id="74c29-129">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="74c29-130">Эта политика выполнения предназначена для конфигураций, в которых сценарий PowerShell встроен в более крупное приложение, или для конфигураций, в которых PowerShell является основой для программы, имеющей собственную модель безопасности.</span><span class="sxs-lookup"><span data-stu-id="74c29-130">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="74c29-131">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="74c29-131">Default</span></span>

- <span data-ttu-id="74c29-132">Задает политику выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="74c29-132">Sets the default execution policy.</span></span>
- <span data-ttu-id="74c29-133">**Ограничено** для клиентов Windows.</span><span class="sxs-lookup"><span data-stu-id="74c29-133">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="74c29-134">**RemoteSigned** для серверов Windows.</span><span class="sxs-lookup"><span data-stu-id="74c29-134">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="74c29-135">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="74c29-135">RemoteSigned</span></span>

- <span data-ttu-id="74c29-136">Политика выполнения по умолчанию для компьютеров Windows Server.</span><span class="sxs-lookup"><span data-stu-id="74c29-136">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="74c29-137">Сценарии могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="74c29-137">Scripts can run.</span></span>
- <span data-ttu-id="74c29-138">Требуется цифровая подпись от доверенного издателя для сценариев и файлов конфигурации, загружаемых из Интернета, которые включают программы электронной почты и мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="74c29-138">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="74c29-139">Не требует цифровых подписей для сценариев, которые записываются на локальном компьютере и не загружаются из Интернета.</span><span class="sxs-lookup"><span data-stu-id="74c29-139">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="74c29-140">Запускает скрипты, скачанные из Интернета и не подписанные, если скрипты разблокированы, например с помощью `Unblock-File` командлета.</span><span class="sxs-lookup"><span data-stu-id="74c29-140">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="74c29-141">Риски запуска неподписанных скриптов из источников, отличных от Интернета, и подписанных сценариев, которые могут быть вредоносными.</span><span class="sxs-lookup"><span data-stu-id="74c29-141">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="74c29-142">С ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="74c29-142">Restricted</span></span>

- <span data-ttu-id="74c29-143">Политика выполнения по умолчанию для клиентских компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="74c29-143">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="74c29-144">Разрешает отдельные команды, но не разрешает сценарии.</span><span class="sxs-lookup"><span data-stu-id="74c29-144">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="74c29-145">Предотвращает запуск всех файлов скриптов, включая файлы форматирования и конфигурации ( `.ps1xml` ), файлы скриптов модуля ( `.psm1` ) и профили PowerShell ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="74c29-145">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="74c29-146">Не определено.</span><span class="sxs-lookup"><span data-stu-id="74c29-146">Undefined</span></span>

- <span data-ttu-id="74c29-147">В текущей области не задана политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-147">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="74c29-148">Если политика выполнения во всех областях не **определена**, действующая политика выполнения **ограничена** для клиентов Windows и **RemoteSigned** для Windows Server.</span><span class="sxs-lookup"><span data-stu-id="74c29-148">If the execution policy in all scopes is **Undefined**, the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="74c29-149">С неограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="74c29-149">Unrestricted</span></span>

- <span data-ttu-id="74c29-150">Политика выполнения по умолчанию для компьютеров, отличных от Windows, и не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="74c29-150">The default execution policy for non-Windows computers and cannot be changed.</span></span>
- <span data-ttu-id="74c29-151">Неподписанные скрипты могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="74c29-151">Unsigned scripts can run.</span></span> <span data-ttu-id="74c29-152">Существует риск запуска вредоносных сценариев.</span><span class="sxs-lookup"><span data-stu-id="74c29-152">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="74c29-153">Предупреждает пользователя перед запуском скриптов и файлов конфигурации, которые не входят в зону местной интрасети.</span><span class="sxs-lookup"><span data-stu-id="74c29-153">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="74c29-154">В системах, которые не отличают пути UNC от Интернет-путей, сценарии, определяемые путем UNC, могут быть запрещены для выполнения с политикой выполнения **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="74c29-154">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="74c29-155">Область политики выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-155">Execution policy scope</span></span>

<span data-ttu-id="74c29-156">Можно задать политику выполнения, действующую только в определенной области.</span><span class="sxs-lookup"><span data-stu-id="74c29-156">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="74c29-157">Допустимые значения для **Scope** : **мачинеполици**, **UserPolicy**, **Process**, **CurrentUser** и **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="74c29-157">The valid values for **Scope** are **MachinePolicy**, **UserPolicy**, **Process**, **CurrentUser**, and **LocalMachine**.</span></span> <span data-ttu-id="74c29-158">**Хранилище LocalMachine** используется по умолчанию при задании политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-158">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="74c29-159">Значения **области** перечислены в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="74c29-159">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="74c29-160">Политика, которая имеет приоритет, вступает в силу в текущем сеансе, даже если более ограничивающая политика была установлена на более низком уровне приоритета.</span><span class="sxs-lookup"><span data-stu-id="74c29-160">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="74c29-161">Дополнительные сведения см. в разделе [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span><span class="sxs-lookup"><span data-stu-id="74c29-161">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="74c29-162">мачинеполици</span><span class="sxs-lookup"><span data-stu-id="74c29-162">MachinePolicy</span></span>

<span data-ttu-id="74c29-163">Задается групповая политика для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="74c29-163">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="74c29-164">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="74c29-164">UserPolicy</span></span>

<span data-ttu-id="74c29-165">Задается групповая политика для текущего пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="74c29-165">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="74c29-166">Процесс</span><span class="sxs-lookup"><span data-stu-id="74c29-166">Process</span></span>

<span data-ttu-id="74c29-167">Область **процесса** влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74c29-167">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="74c29-168">Политика выполнения сохраняется в переменной среды `$env:PSExecutionPolicyPreference` , а не в реестре.</span><span class="sxs-lookup"><span data-stu-id="74c29-168">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="74c29-169">При закрытии сеанса PowerShell переменная и значение удаляются.</span><span class="sxs-lookup"><span data-stu-id="74c29-169">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="74c29-170">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="74c29-170">CurrentUser</span></span>

<span data-ttu-id="74c29-171">политика выполнения распространяется только на текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="74c29-171">The execution policy affects only the current user.</span></span> <span data-ttu-id="74c29-172">Он хранится в подразделе реестра **HKEY_CURRENT_USER** .</span><span class="sxs-lookup"><span data-stu-id="74c29-172">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="74c29-173">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="74c29-173">LocalMachine</span></span>

<span data-ttu-id="74c29-174">Политика выполнения влияет на всех пользователей на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="74c29-174">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="74c29-175">Он хранится в подразделе реестра **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="74c29-175">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="74c29-176">Управление политикой выполнения с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="74c29-176">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="74c29-177">Чтобы получить действующую политику выполнения для текущего сеанса PowerShell, используйте `Get-ExecutionPolicy` командлет.</span><span class="sxs-lookup"><span data-stu-id="74c29-177">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="74c29-178">Следующая команда получает действующую политику выполнения:</span><span class="sxs-lookup"><span data-stu-id="74c29-178">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="74c29-179">Чтобы получить все политики выполнения, влияющие на текущий сеанс, и отобразить их в порядке очередности:</span><span class="sxs-lookup"><span data-stu-id="74c29-179">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="74c29-180">Результат выглядит примерно так, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="74c29-180">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="74c29-181">В этом случае действующая политика выполнения — **RemoteSigned** , так как политика выполнения для текущего пользователя имеет приоритет над политикой выполнения, заданной для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="74c29-181">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="74c29-182">Чтобы получить политику выполнения, заданную для определенной области, используйте параметр **Scope** объекта `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="74c29-182">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="74c29-183">Например, следующая команда возвращает политику выполнения для области **CurrentUser** :</span><span class="sxs-lookup"><span data-stu-id="74c29-183">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="74c29-184">Изменение политики выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-184">Change the execution policy</span></span>

<span data-ttu-id="74c29-185">Чтобы изменить политику выполнения PowerShell на компьютере Windows, используйте `Set-ExecutionPolicy` командлет.</span><span class="sxs-lookup"><span data-stu-id="74c29-185">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="74c29-186">Изменение вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="74c29-186">The change is effective immediately.</span></span> <span data-ttu-id="74c29-187">Вам не нужно перезапускать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74c29-187">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="74c29-188">Если задать политику выполнения для областей **LocalMachine** или **CurrentUser**, это изменение будет сохранено в реестре и останется эффективным, пока вы не измените его.</span><span class="sxs-lookup"><span data-stu-id="74c29-188">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser**, the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="74c29-189">Если задать политику выполнения для области **процесса** , она не будет сохранена в реестре.</span><span class="sxs-lookup"><span data-stu-id="74c29-189">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="74c29-190">Политика выполнения сохраняется до закрытия текущего процесса и любых дочерних процессов.</span><span class="sxs-lookup"><span data-stu-id="74c29-190">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="74c29-191">В Windows Vista и более поздних версиях Windows для выполнения команд, изменяющих политику выполнения для локального компьютера, область **LocalMachine** , запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="74c29-191">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="74c29-192">Чтобы изменить политику выполнения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74c29-192">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="74c29-193">Пример:</span><span class="sxs-lookup"><span data-stu-id="74c29-193">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="74c29-194">Чтобы задать политику выполнения в определенной области, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74c29-194">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="74c29-195">Пример:</span><span class="sxs-lookup"><span data-stu-id="74c29-195">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="74c29-196">Команда для изменения политики выполнения может быть выполнена, но не будет изменена действующая политика выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-196">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="74c29-197">Например, команда, которая задает политику выполнения для локального компьютера, может быть выполнена, но переопределена политикой выполнения для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="74c29-197">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="74c29-198">Удаление политики выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-198">Remove the execution policy</span></span>

<span data-ttu-id="74c29-199">Чтобы удалить политику выполнения для определенной области, задайте для политики выполнения значение **undefine**.</span><span class="sxs-lookup"><span data-stu-id="74c29-199">To remove the execution policy for a particular scope, set the execution policy to **Undefined**.</span></span>

<span data-ttu-id="74c29-200">Например, чтобы удалить политику выполнения для всех пользователей локального компьютера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74c29-200">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="74c29-201">Чтобы удалить политику выполнения для **области**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="74c29-201">To remove the execution policy for a **Scope**:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="74c29-202">Если в какой-либо области не задана политика выполнения, действующая политика выполнения **ограничена**, что является значением по умолчанию для клиентов Windows.</span><span class="sxs-lookup"><span data-stu-id="74c29-202">If no execution policy is set in any scope, the effective execution policy is **Restricted**, which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="74c29-203">Задание другой политики для одного сеанса</span><span class="sxs-lookup"><span data-stu-id="74c29-203">Set a different policy for one session</span></span>

<span data-ttu-id="74c29-204">Чтобы задать политику выполнения для нового сеанса PowerShell, можно использовать параметр **ExecutionPolicy** **pwsh.exe** .</span><span class="sxs-lookup"><span data-stu-id="74c29-204">You can use the **ExecutionPolicy** parameter of **pwsh.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="74c29-205">Политика влияет только на текущий сеанс и дочерние сеансы.</span><span class="sxs-lookup"><span data-stu-id="74c29-205">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="74c29-206">Чтобы задать политику выполнения для нового сеанса, запустите PowerShell из командной строки, например **cmd.exe** или PowerShell, а затем используйте параметр **ExecutionPolicy** из **pwsh.exe** , чтобы задать политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-206">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **pwsh.exe** to set the execution policy.</span></span>

<span data-ttu-id="74c29-207">Пример:</span><span class="sxs-lookup"><span data-stu-id="74c29-207">For example:</span></span>

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="74c29-208">Заданная политика выполнения не хранится в реестре.</span><span class="sxs-lookup"><span data-stu-id="74c29-208">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="74c29-209">Вместо этого он хранится в `$env:PSExecutionPolicyPreference` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="74c29-209">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="74c29-210">Переменная удаляется при закрытии сеанса, в котором задана политика.</span><span class="sxs-lookup"><span data-stu-id="74c29-210">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="74c29-211">Вы не можете изменить политику, изменив значение переменной.</span><span class="sxs-lookup"><span data-stu-id="74c29-211">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="74c29-212">Во время сеанса политика выполнения, заданная для сеанса, имеет приоритет над политикой выполнения, заданной в реестре для локального компьютера или текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="74c29-212">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="74c29-213">Однако он не имеет приоритета над политикой выполнения, заданной с помощью групповая политика.</span><span class="sxs-lookup"><span data-stu-id="74c29-213">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="74c29-214">Использование групповая политика для управления политикой выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-214">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="74c29-215">Для управления политикой выполнения компьютеров предприятия можно использовать параметр групповая политика **включить выполнение скрипта** .</span><span class="sxs-lookup"><span data-stu-id="74c29-215">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="74c29-216">Параметр групповая политика переопределяет политики выполнения, заданные в PowerShell во всех областях.</span><span class="sxs-lookup"><span data-stu-id="74c29-216">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="74c29-217">Включить параметры политики **выполнения сценария** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="74c29-217">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="74c29-218">Если отключить **выполнение скрипта**, скрипты не будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="74c29-218">If you disable **Turn on Script Execution**, scripts do not run.</span></span> <span data-ttu-id="74c29-219">Это эквивалентно **ограниченной** политике выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-219">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="74c29-220">Если включить **выполнение скрипта**, можно выбрать политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-220">If you enable **Turn on Script Execution**, you can select an execution policy.</span></span> <span data-ttu-id="74c29-221">Параметры групповая политика эквивалентны следующим параметрам политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-221">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="74c29-222">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="74c29-222">Group Policy</span></span>                                  | <span data-ttu-id="74c29-223">Политика выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-223">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="74c29-224">Разрешить все скрипты</span><span class="sxs-lookup"><span data-stu-id="74c29-224">Allow all scripts</span></span>                             | <span data-ttu-id="74c29-225">С неограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="74c29-225">Unrestricted</span></span>     |
  | <span data-ttu-id="74c29-226">Разрешить локальные скрипты и удаленные подписанные скрипты</span><span class="sxs-lookup"><span data-stu-id="74c29-226">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="74c29-227">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="74c29-227">RemoteSigned</span></span>     |
  | <span data-ttu-id="74c29-228">Разрешить только подписанные скрипты</span><span class="sxs-lookup"><span data-stu-id="74c29-228">Allow only signed scripts</span></span>                     | <span data-ttu-id="74c29-229">AllSigned</span><span class="sxs-lookup"><span data-stu-id="74c29-229">AllSigned</span></span>        |

- <span data-ttu-id="74c29-230">Если параметр **включить выполнение скрипта** не настроен, он не будет действовать.</span><span class="sxs-lookup"><span data-stu-id="74c29-230">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="74c29-231">Политика выполнения, заданная в PowerShell, вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="74c29-231">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="74c29-232">Файлы Повершеллексекутионполици. adm и Повершеллексекутионполици. ADMX добавляют политику **выполнения сценария включения** в узлы Конфигурация компьютера и Конфигурация пользователя в групповая политика Editor по следующим путям.</span><span class="sxs-lookup"><span data-stu-id="74c29-232">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="74c29-233">Для Windows XP и Windows Server 2003:</span><span class="sxs-lookup"><span data-stu-id="74c29-233">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="74c29-234">Административные шаблоны управления Windows — PowerShell</span><span class="sxs-lookup"><span data-stu-id="74c29-234">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="74c29-235">Для Windows Vista и более поздних версий Windows:</span><span class="sxs-lookup"><span data-stu-id="74c29-235">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="74c29-236">Администрирование Темплатес\классик административные шаблоны </span><span class="sxs-lookup"><span data-stu-id="74c29-236">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="74c29-237">Windows \ PowerShell</span><span class="sxs-lookup"><span data-stu-id="74c29-237">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="74c29-238">Политики, заданные в узле Конфигурация компьютера, имеют приоритет над политиками, заданными в узле Конфигурация пользователя.</span><span class="sxs-lookup"><span data-stu-id="74c29-238">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="74c29-239">Дополнительные сведения см. в статье [О параметрах групповой политики](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="74c29-239">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="74c29-240">Приоритет политики выполнения</span><span class="sxs-lookup"><span data-stu-id="74c29-240">Execution policy precedence</span></span>

<span data-ttu-id="74c29-241">При определении действующей политики выполнения для сеанса PowerShell оценивает политики выполнения в следующем порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="74c29-241">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="74c29-242">Групповая политика: Мачинеполици</span><span class="sxs-lookup"><span data-stu-id="74c29-242">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="74c29-243">Групповая политика: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="74c29-243">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="74c29-244">Политика выполнения: процесс (или `pwsh.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="74c29-244">Execution Policy: Process (or `pwsh.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="74c29-245">Политика выполнения: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="74c29-245">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="74c29-246">Политика выполнения: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="74c29-246">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="74c29-247">Управление подписанными и неподписанными скриптами</span><span class="sxs-lookup"><span data-stu-id="74c29-247">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="74c29-248">В Windows такие программы, как Internet Explorer и Microsoft ребр, добавляют альтернативный поток данных к загруженным файлам.</span><span class="sxs-lookup"><span data-stu-id="74c29-248">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="74c29-249">Этот файл помечается как «поступающий из Интернета».</span><span class="sxs-lookup"><span data-stu-id="74c29-249">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="74c29-250">Если политика выполнения PowerShell — **RemoteSigned**, PowerShell не будет запускать неподписанные сценарии, которые загружаются из Интернета, в том числе программы электронной почты и обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="74c29-250">If your PowerShell execution policy is **RemoteSigned**, PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="74c29-251">Вы можете подписать сценарий или выбрать Запуск неподписанного скрипта без изменения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="74c29-251">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="74c29-252">Начиная с версии PowerShell 3,0 можно использовать параметр **Stream** `Get-Item` командлета для обнаружения заблокированных файлов, так как они были загружены из Интернета.</span><span class="sxs-lookup"><span data-stu-id="74c29-252">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="74c29-253">Используйте `Unblock-File` командлет, чтобы разблокировать скрипты, чтобы их можно было запускать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74c29-253">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="74c29-254">Дополнительные сведения см. в разделе [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)и [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span><span class="sxs-lookup"><span data-stu-id="74c29-254">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="74c29-255">Другие методы загрузки файлов могут не помечать файлы как поступающие из зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="74c29-255">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="74c29-256">Некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="74c29-256">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="74c29-257">Политика выполнения в Windows Server Core и в окне Nano Server</span><span class="sxs-lookup"><span data-stu-id="74c29-257">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="74c29-258">Когда PowerShell 6 запускается на Windows Server Core или Windows Nano Server при определенных условиях, политики выполнения могут завершиться со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="74c29-258">When PowerShell 6 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="74c29-259">PowerShell использует интерфейсы API в оболочке Windows Desktop Shell ( `explorer.exe` ) для проверки зоны файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="74c29-259">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="74c29-260">Оболочка Windows недоступна в Windows Server Core и Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="74c29-260">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="74c29-261">Эту ошибку также можно получить в любой системе Windows, если оболочка Windows для настольных компьютеров недоступна или не отвечает.</span><span class="sxs-lookup"><span data-stu-id="74c29-261">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="74c29-262">Например, во время входа сценарий входа PowerShell может начать выполнение до того, как рабочий стол Windows будет готов, что приведет к сбою.</span><span class="sxs-lookup"><span data-stu-id="74c29-262">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="74c29-263">При использовании политики выполнения **обхода** или **AllSigned** не требуется проверка зоны, которая позволяет избежать проблемы.</span><span class="sxs-lookup"><span data-stu-id="74c29-263">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="74c29-264">См. также:</span><span class="sxs-lookup"><span data-stu-id="74c29-264">See Also</span></span>

[<span data-ttu-id="74c29-265">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="74c29-265">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="74c29-266">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="74c29-266">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="74c29-267">about_Signing</span><span class="sxs-lookup"><span data-stu-id="74c29-267">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="74c29-268">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="74c29-268">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="74c29-269">Get-Item</span><span class="sxs-lookup"><span data-stu-id="74c29-269">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="74c29-270">Справка по консоли Pwsh</span><span class="sxs-lookup"><span data-stu-id="74c29-270">Pwsh Console Help</span></span>](about_pwsh.md)

[<span data-ttu-id="74c29-271">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="74c29-271">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="74c29-272">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="74c29-272">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)

