---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: bacafee683fa47d7be331b4e44d2ab75be5bdb23
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604487"
---
# <span data-ttu-id="f4647-102">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="f4647-102">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="f4647-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f4647-103">SYNOPSIS</span></span>
<span data-ttu-id="f4647-104">Включает проверку подлинности на компьютере с помощью поставщика поддержки безопасности учетных данных (CredSSP).</span><span class="sxs-lookup"><span data-stu-id="f4647-104">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="f4647-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4647-105">SYNTAX</span></span>

### <span data-ttu-id="f4647-106">Все</span><span class="sxs-lookup"><span data-stu-id="f4647-106">All</span></span>

```
Enable-WSManCredSSP [[-DelegateComputer] <String[]>] [-Force] [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="f4647-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4647-107">DESCRIPTION</span></span>

<span data-ttu-id="f4647-108">`Enable-WSManCredSSP`Командлет включает проверку подлинности CredSSP на клиенте или на компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="f4647-108">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="f4647-109">При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f4647-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="f4647-110">Этот тип проверки подлинности предназначен для команд, которые создают удаленный сеанс из другого удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f4647-110">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="f4647-111">Например, если вы хотите запустить фоновое задание на удаленном компьютере, используйте такой тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f4647-111">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="f4647-112">`Enable-WSManCredSSP` может включить CredSSP на **клиенте** или на **сервере**.</span><span class="sxs-lookup"><span data-stu-id="f4647-112">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server**.</span></span> <span data-ttu-id="f4647-113">Чтобы включить CredSSP на клиенте, укажите **Client** в параметре **Role** .</span><span class="sxs-lookup"><span data-stu-id="f4647-113">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="f4647-114">Клиенты делегируют явные учетные данные серверу при достижении проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="f4647-114">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="f4647-115">Чтобы включить CredSSP на сервере, укажите **Server** в параметре **Role** .</span><span class="sxs-lookup"><span data-stu-id="f4647-115">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="f4647-116">Сервер выступает в качестве делегата для клиентов.</span><span class="sxs-lookup"><span data-stu-id="f4647-116">A server acts as a delegate for clients.</span></span> <span data-ttu-id="f4647-117">Дополнительные сведения см. в статье **Role** в разделе Parameters.</span><span class="sxs-lookup"><span data-stu-id="f4647-117">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="f4647-118">Проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="f4647-118">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="f4647-119">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="f4647-119">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="f4647-120">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="f4647-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="f4647-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="f4647-121">EXAMPLES</span></span>

### <span data-ttu-id="f4647-122">Пример 1. делегирование учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="f4647-122">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="f4647-123">Этот пример позволяет делегировать учетные данные клиента компьютеру с помощью полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="f4647-123">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="f4647-124">Пример 2. делегирование учетных данных клиента на все компьютеры в домене</span><span class="sxs-lookup"><span data-stu-id="f4647-124">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="f4647-125">Этот пример позволяет делегировать учетные данные клиента всем компьютерам в домене **Fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="f4647-125">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="f4647-126">`*`Подстановочный знак звездочки () задает все компьютеры.</span><span class="sxs-lookup"><span data-stu-id="f4647-126">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="f4647-127">Использование подстановочных знаков с параметром **DelegateComputer** может включить CredSSP на большем число компьютеров, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="f4647-127">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="f4647-128">Пример 3. делегирование учетных данных клиента нескольким компьютерам</span><span class="sxs-lookup"><span data-stu-id="f4647-128">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="f4647-129">Этот пример позволяет делегировать учетные данные клиента нескольким компьютерам.</span><span class="sxs-lookup"><span data-stu-id="f4647-129">This example allows the client credentials to be delegated to multiple computers.</span></span>

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

<span data-ttu-id="f4647-130">`$servers`Переменная содержит список имен серверов.</span><span class="sxs-lookup"><span data-stu-id="f4647-130">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="f4647-131">`Enable-WSManCredSSP` использует параметр **Role** для указания роли **клиента** .</span><span class="sxs-lookup"><span data-stu-id="f4647-131">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="f4647-132">**DelegateComputer** получает имена компьютеров из `$servers` переменной.</span><span class="sxs-lookup"><span data-stu-id="f4647-132">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="f4647-133">Пример 4. разрешение компьютеру действовать в качестве делегата</span><span class="sxs-lookup"><span data-stu-id="f4647-133">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="f4647-134">Этот пример позволяет компьютеру действовать в качестве делегата для другого.</span><span class="sxs-lookup"><span data-stu-id="f4647-134">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="f4647-135">`Enable-WSManCredSSP`Командлет, показанный в предыдущих примерах, включает только проверку подлинности CredSSP на клиенте и указывает удаленные компьютеры, которые могут действовать от его имени.</span><span class="sxs-lookup"><span data-stu-id="f4647-135">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="f4647-136">Чтобы удаленный компьютер действовал в качестве делегата для клиента, элемент CredSSP в узле **службы** WSMan должен иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="f4647-136">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="f4647-137">В этом примере для элемента CredSSP в узле **службы** WSMan задается значение true.</span><span class="sxs-lookup"><span data-stu-id="f4647-137">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="f4647-138">Пример 5. разрешение компьютеру действовать в качестве делегата с помощью Set-Item</span><span class="sxs-lookup"><span data-stu-id="f4647-138">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="f4647-139">Этот пример позволяет компьютеру действовать в качестве делегата для другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="f4647-139">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="f4647-140">`Enable-WSManCredSSP`Команды, показанные в предыдущих примерах, включают проверку подлинности CredSSP только на клиентском компьютере и указывают удаленные компьютеры, которые могут действовать от имени клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="f4647-140">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="f4647-141">Чтобы удаленный компьютер выступал в качестве делегата для клиентского компьютера, для элемента CredSSP в каталоге Service WSMan следует установить значение true.</span><span class="sxs-lookup"><span data-stu-id="f4647-141">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="f4647-142">`Connect-WSMan` создает подключение к удаленному компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="f4647-142">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="f4647-143">`Set-Item` использует параметр **path** для указания расположения поставщика **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="f4647-143">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="f4647-144">Параметр **value** устанавливает для параметра **службы** значение true.</span><span class="sxs-lookup"><span data-stu-id="f4647-144">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="f4647-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4647-145">PARAMETERS</span></span>

### <span data-ttu-id="f4647-146">-DelegateComputer</span><span class="sxs-lookup"><span data-stu-id="f4647-146">-DelegateComputer</span></span>

<span data-ttu-id="f4647-147">Указывает серверы, на которые делегируются учетные данные клиента.</span><span class="sxs-lookup"><span data-stu-id="f4647-147">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="f4647-148">Рекомендуется использовать полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="f4647-148">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="f4647-149">Подстановочные знаки принимаются, но могут включать CredSSP на большем количество компьютеров, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="f4647-149">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="f4647-150">Если параметр **Role** имеет значение **Client**, необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="f4647-150">If the **Role** parameter is **Client**, you must specify this parameter.</span></span> <span data-ttu-id="f4647-151">Если **Role** — **Server**, не указывайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="f4647-151">If **Role** is **Server**, don't specify this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f4647-152">-Force</span><span class="sxs-lookup"><span data-stu-id="f4647-152">-Force</span></span>

<span data-ttu-id="f4647-153">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="f4647-153">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4647-154">-Role</span><span class="sxs-lookup"><span data-stu-id="f4647-154">-Role</span></span>

<span data-ttu-id="f4647-155">Указывает, следует ли включить CredSSP в качестве клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="f4647-155">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="f4647-156">Допустимые значения для этого параметра: **Client** и **Server**.</span><span class="sxs-lookup"><span data-stu-id="f4647-156">The acceptable values for this parameter are: **Client** and **Server**.</span></span>

<span data-ttu-id="f4647-157">При указании **клиента** выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f4647-157">If you specify **Client**, the following actions are performed.</span></span> <span data-ttu-id="f4647-158">Эти параметры позволяют клиенту делегировать явные учетные данные на сервер при выполнении аутентификации сервера.</span><span class="sxs-lookup"><span data-stu-id="f4647-158">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="f4647-159">Включает CredSSP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="f4647-159">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="f4647-160">Задает для параметра WS-Management значение `\<localhost|computername\>\Client\Auth\CredSSP` true.</span><span class="sxs-lookup"><span data-stu-id="f4647-160">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="f4647-161">Задает для политики Windows CredSSP  , алловфрешкредентиалс **WSMan/Delegate** на клиенте.</span><span class="sxs-lookup"><span data-stu-id="f4647-161">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="f4647-162">Если указан параметр **Server**, выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f4647-162">If you specify **Server**, the following actions are performed.</span></span> <span data-ttu-id="f4647-163">Этот параметр политики позволяет серверу выступать в качестве делегата для клиентов.</span><span class="sxs-lookup"><span data-stu-id="f4647-163">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="f4647-164">Включает CredSSP на сервере.</span><span class="sxs-lookup"><span data-stu-id="f4647-164">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="f4647-165">Задает для параметра WS-Management значение `\<localhost|computername\>\Service\Auth\CredSSP` true.</span><span class="sxs-lookup"><span data-stu-id="f4647-165">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4647-166">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f4647-166">CommonParameters</span></span>

<span data-ttu-id="f4647-167">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f4647-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4647-168">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f4647-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4647-169">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f4647-169">INPUTS</span></span>

### <span data-ttu-id="f4647-170">None</span><span class="sxs-lookup"><span data-stu-id="f4647-170">None</span></span>

<span data-ttu-id="f4647-171">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="f4647-171">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="f4647-172">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f4647-172">OUTPUTS</span></span>

### <span data-ttu-id="f4647-173">System.Xml.XmlElement</span><span class="sxs-lookup"><span data-stu-id="f4647-173">System.Xml.XmlElement</span></span>

<span data-ttu-id="f4647-174">Если проверка подлинности CredSSP успешно включена, этот командлет создает объект **XmlElement** .</span><span class="sxs-lookup"><span data-stu-id="f4647-174">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="f4647-175">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f4647-175">NOTES</span></span>

<span data-ttu-id="f4647-176">Чтобы отключить проверку подлинности CredSSP, используйте `Disable-WSManCredSSP` командлет.</span><span class="sxs-lookup"><span data-stu-id="f4647-176">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="f4647-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f4647-177">RELATED LINKS</span></span>

[<span data-ttu-id="f4647-178">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="f4647-178">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="f4647-179">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="f4647-179">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="f4647-180">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="f4647-180">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="f4647-181">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="f4647-181">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="f4647-182">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f4647-182">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="f4647-183">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="f4647-183">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="f4647-184">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f4647-184">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="f4647-185">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="f4647-185">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="f4647-186">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f4647-186">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="f4647-187">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f4647-187">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="f4647-188">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="f4647-188">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="f4647-189">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="f4647-189">Test-WSMan</span></span>](Test-WSMan.md)

