---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: 0b4ec4902df2b2e93def549586e3f6cde70fadee
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229857"
---
# <span data-ttu-id="b112d-103">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b112d-103">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="b112d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b112d-104">SYNOPSIS</span></span>
<span data-ttu-id="b112d-105">Включает проверку подлинности на компьютере с помощью поставщика поддержки безопасности учетных данных (CredSSP).</span><span class="sxs-lookup"><span data-stu-id="b112d-105">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="b112d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b112d-106">SYNTAX</span></span>

### <span data-ttu-id="b112d-107">Все</span><span class="sxs-lookup"><span data-stu-id="b112d-107">All</span></span>

```
Enable-WSManCredSSP [-Role] <String> [[-DelegateComputer] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="b112d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b112d-108">DESCRIPTION</span></span>

<span data-ttu-id="b112d-109">`Enable-WSManCredSSP`Командлет включает проверку подлинности CredSSP на клиенте или на компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="b112d-109">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="b112d-110">При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b112d-110">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="b112d-111">Этот тип проверки подлинности предназначен для команд, которые создают удаленный сеанс из другого удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="b112d-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="b112d-112">Например, если вы хотите запустить фоновое задание на удаленном компьютере, используйте такой тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b112d-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="b112d-113">`Enable-WSManCredSSP` может включить CredSSP на **клиенте** или на **сервере**.</span><span class="sxs-lookup"><span data-stu-id="b112d-113">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server**.</span></span> <span data-ttu-id="b112d-114">Чтобы включить CredSSP на клиенте, укажите **Client** в параметре **Role** .</span><span class="sxs-lookup"><span data-stu-id="b112d-114">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="b112d-115">Клиенты делегируют явные учетные данные серверу при достижении проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="b112d-115">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="b112d-116">Чтобы включить CredSSP на сервере, укажите **Server** в параметре **Role** .</span><span class="sxs-lookup"><span data-stu-id="b112d-116">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="b112d-117">Сервер выступает в качестве делегата для клиентов.</span><span class="sxs-lookup"><span data-stu-id="b112d-117">A server acts as a delegate for clients.</span></span> <span data-ttu-id="b112d-118">Дополнительные сведения см. в статье **Role** в разделе Parameters.</span><span class="sxs-lookup"><span data-stu-id="b112d-118">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="b112d-119">Проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b112d-119">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="b112d-120">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="b112d-120">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="b112d-121">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="b112d-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="b112d-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="b112d-122">EXAMPLES</span></span>

### <span data-ttu-id="b112d-123">Пример 1. делегирование учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="b112d-123">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="b112d-124">Этот пример позволяет делегировать учетные данные клиента компьютеру с помощью полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="b112d-124">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

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

### <span data-ttu-id="b112d-125">Пример 2. делегирование учетных данных клиента на все компьютеры в домене</span><span class="sxs-lookup"><span data-stu-id="b112d-125">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="b112d-126">Этот пример позволяет делегировать учетные данные клиента всем компьютерам в домене **Fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="b112d-126">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="b112d-127">`*`Подстановочный знак звездочки () задает все компьютеры.</span><span class="sxs-lookup"><span data-stu-id="b112d-127">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="b112d-128">Использование подстановочных знаков с параметром **DelegateComputer** может включить CredSSP на большем число компьютеров, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="b112d-128">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

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

### <span data-ttu-id="b112d-129">Пример 3. делегирование учетных данных клиента нескольким компьютерам</span><span class="sxs-lookup"><span data-stu-id="b112d-129">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="b112d-130">Этот пример позволяет делегировать учетные данные клиента нескольким компьютерам.</span><span class="sxs-lookup"><span data-stu-id="b112d-130">This example allows the client credentials to be delegated to multiple computers.</span></span>

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

<span data-ttu-id="b112d-131">`$servers`Переменная содержит список имен серверов.</span><span class="sxs-lookup"><span data-stu-id="b112d-131">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="b112d-132">`Enable-WSManCredSSP` использует параметр **Role** для указания роли **клиента** .</span><span class="sxs-lookup"><span data-stu-id="b112d-132">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="b112d-133">**DelegateComputer** получает имена компьютеров из `$servers` переменной.</span><span class="sxs-lookup"><span data-stu-id="b112d-133">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="b112d-134">Пример 4. разрешение компьютеру действовать в качестве делегата</span><span class="sxs-lookup"><span data-stu-id="b112d-134">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="b112d-135">Этот пример позволяет компьютеру действовать в качестве делегата для другого.</span><span class="sxs-lookup"><span data-stu-id="b112d-135">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="b112d-136">`Enable-WSManCredSSP`Командлет, показанный в предыдущих примерах, включает только проверку подлинности CredSSP на клиенте и указывает удаленные компьютеры, которые могут действовать от его имени.</span><span class="sxs-lookup"><span data-stu-id="b112d-136">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="b112d-137">Чтобы удаленный компьютер действовал в качестве делегата для клиента, элемент CredSSP в узле **службы** WSMan должен иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="b112d-137">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="b112d-138">В этом примере для элемента CredSSP в узле **службы** WSMan задается значение true.</span><span class="sxs-lookup"><span data-stu-id="b112d-138">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="b112d-139">Пример 5. разрешение компьютеру действовать в качестве делегата с помощью Set-Item</span><span class="sxs-lookup"><span data-stu-id="b112d-139">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="b112d-140">Этот пример позволяет компьютеру действовать в качестве делегата для другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="b112d-140">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="b112d-141">`Enable-WSManCredSSP`Команды, показанные в предыдущих примерах, включают проверку подлинности CredSSP только на клиентском компьютере и указывают удаленные компьютеры, которые могут действовать от имени клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="b112d-141">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="b112d-142">Чтобы удаленный компьютер выступал в качестве делегата для клиентского компьютера, для элемента CredSSP в каталоге Service WSMan следует установить значение true.</span><span class="sxs-lookup"><span data-stu-id="b112d-142">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="b112d-143">`Connect-WSMan` создает подключение к удаленному компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="b112d-143">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="b112d-144">`Set-Item` использует параметр **path** для указания расположения поставщика **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="b112d-144">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="b112d-145">Параметр **value** устанавливает для параметра **службы** значение true.</span><span class="sxs-lookup"><span data-stu-id="b112d-145">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="b112d-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b112d-146">PARAMETERS</span></span>

### <span data-ttu-id="b112d-147">-DelegateComputer</span><span class="sxs-lookup"><span data-stu-id="b112d-147">-DelegateComputer</span></span>

<span data-ttu-id="b112d-148">Указывает серверы, на которые делегируются учетные данные клиента.</span><span class="sxs-lookup"><span data-stu-id="b112d-148">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="b112d-149">Рекомендуется использовать полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="b112d-149">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="b112d-150">Подстановочные знаки принимаются, но могут включать CredSSP на большем количество компьютеров, чем требуется.</span><span class="sxs-lookup"><span data-stu-id="b112d-150">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="b112d-151">Если параметр **Role** имеет значение **Client** , необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b112d-151">If the **Role** parameter is **Client** , you must specify this parameter.</span></span> <span data-ttu-id="b112d-152">Если **Role** — **Server** , не указывайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b112d-152">If **Role** is **Server** , don't specify this parameter.</span></span>

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

### <span data-ttu-id="b112d-153">-Force</span><span class="sxs-lookup"><span data-stu-id="b112d-153">-Force</span></span>

<span data-ttu-id="b112d-154">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="b112d-154">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b112d-155">-Role</span><span class="sxs-lookup"><span data-stu-id="b112d-155">-Role</span></span>

<span data-ttu-id="b112d-156">Указывает, следует ли включить CredSSP в качестве клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="b112d-156">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="b112d-157">Допустимые значения для этого параметра: **Client** и **Server**.</span><span class="sxs-lookup"><span data-stu-id="b112d-157">The acceptable values for this parameter are: **Client** and **Server**.</span></span>

<span data-ttu-id="b112d-158">При указании **клиента** выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b112d-158">If you specify **Client** , the following actions are performed.</span></span> <span data-ttu-id="b112d-159">Эти параметры позволяют клиенту делегировать явные учетные данные на сервер при выполнении аутентификации сервера.</span><span class="sxs-lookup"><span data-stu-id="b112d-159">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="b112d-160">Включает CredSSP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="b112d-160">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="b112d-161">Задает для параметра WS-Management значение `\<localhost|computername\>\Client\Auth\CredSSP` true.</span><span class="sxs-lookup"><span data-stu-id="b112d-161">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="b112d-162">Задает для политики Windows CredSSP **AllowFreshCredentials** , алловфрешкредентиалс **WSMan/Delegate** на клиенте.</span><span class="sxs-lookup"><span data-stu-id="b112d-162">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="b112d-163">Если указан параметр **Server** , выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b112d-163">If you specify **Server** , the following actions are performed.</span></span> <span data-ttu-id="b112d-164">Этот параметр политики позволяет серверу выступать в качестве делегата для клиентов.</span><span class="sxs-lookup"><span data-stu-id="b112d-164">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="b112d-165">Включает CredSSP на сервере.</span><span class="sxs-lookup"><span data-stu-id="b112d-165">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="b112d-166">Задает для параметра WS-Management значение `\<localhost|computername\>\Service\Auth\CredSSP` true.</span><span class="sxs-lookup"><span data-stu-id="b112d-166">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

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

### <span data-ttu-id="b112d-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b112d-167">CommonParameters</span></span>

<span data-ttu-id="b112d-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b112d-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b112d-169">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b112d-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b112d-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b112d-170">INPUTS</span></span>

### <span data-ttu-id="b112d-171">Нет</span><span class="sxs-lookup"><span data-stu-id="b112d-171">None</span></span>

<span data-ttu-id="b112d-172">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="b112d-172">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="b112d-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b112d-173">OUTPUTS</span></span>

### <span data-ttu-id="b112d-174">System.Xml.XmlElement</span><span class="sxs-lookup"><span data-stu-id="b112d-174">System.Xml.XmlElement</span></span>

<span data-ttu-id="b112d-175">Если проверка подлинности CredSSP успешно включена, этот командлет создает объект **XmlElement** .</span><span class="sxs-lookup"><span data-stu-id="b112d-175">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="b112d-176">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b112d-176">NOTES</span></span>

<span data-ttu-id="b112d-177">Чтобы отключить проверку подлинности CredSSP, используйте `Disable-WSManCredSSP` командлет.</span><span class="sxs-lookup"><span data-stu-id="b112d-177">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="b112d-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b112d-178">RELATED LINKS</span></span>

[<span data-ttu-id="b112d-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b112d-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b112d-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b112d-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="b112d-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b112d-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b112d-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b112d-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b112d-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b112d-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="b112d-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b112d-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="b112d-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b112d-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="b112d-186">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b112d-186">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="b112d-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b112d-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="b112d-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b112d-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b112d-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b112d-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b112d-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b112d-190">Test-WSMan</span></span>](Test-WSMan.md)
