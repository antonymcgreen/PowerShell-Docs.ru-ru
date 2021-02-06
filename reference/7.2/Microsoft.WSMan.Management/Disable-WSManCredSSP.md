---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 3260c88d57e98c0072af8621600a02901c561acb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599813"
---
# <span data-ttu-id="2a318-102">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2a318-102">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="2a318-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2a318-103">SYNOPSIS</span></span>
<span data-ttu-id="2a318-104">Отключает проверку подлинности CredSSP на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2a318-104">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="2a318-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2a318-105">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="2a318-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2a318-106">DESCRIPTION</span></span>
<span data-ttu-id="2a318-107">Командлет **Disable-WSManCredSSP** отключает проверку подлинности на уровне поставщика поддержки учетных данных (CredSSP) на клиенте или на компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="2a318-107">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="2a318-108">При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a318-108">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="2a318-109">Используйте этот командлет для отключения CredSSP на клиенте, указав Client в параметре *Role* .</span><span class="sxs-lookup"><span data-stu-id="2a318-109">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="2a318-110">Этот командлет выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2a318-110">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="2a318-111">Отключает CredSSP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="2a318-111">Disables CredSSP on the client.</span></span> <span data-ttu-id="2a318-112">Этот командлет задает для параметра WS-Management **\<localhost|computername\> \клиент\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="2a318-112">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="2a318-113">Удаляет все параметры WSMan/\* из политики Windows CredSSP, **алловфрешкредентиалс** на клиенте.</span><span class="sxs-lookup"><span data-stu-id="2a318-113">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="2a318-114">Используйте этот командлет для отключения CredSSP на сервере путем указания сервера в *роли*.</span><span class="sxs-lookup"><span data-stu-id="2a318-114">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role*.</span></span>
<span data-ttu-id="2a318-115">Этот командлет выполняет следующее действие:</span><span class="sxs-lookup"><span data-stu-id="2a318-115">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="2a318-116">Отключает CredSSP на сервере.</span><span class="sxs-lookup"><span data-stu-id="2a318-116">Disables CredSSP on the server.</span></span> <span data-ttu-id="2a318-117">Этот командлет задает для параметра WS-Management **\<localhost|computername\> \сервице\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="2a318-117">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="2a318-118">Внимание! проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="2a318-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="2a318-119">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="2a318-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="2a318-120">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="2a318-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="2a318-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="2a318-121">EXAMPLES</span></span>

### <span data-ttu-id="2a318-122">Пример 1. Отключение CredSSP на клиенте</span><span class="sxs-lookup"><span data-stu-id="2a318-122">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="2a318-123">Эта команда отключает CredSSP на стороне клиента, что препятствует делегированию на серверы.</span><span class="sxs-lookup"><span data-stu-id="2a318-123">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="2a318-124">Пример 2. Отключение CredSSP на сервере</span><span class="sxs-lookup"><span data-stu-id="2a318-124">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="2a318-125">Эта команда отключает CredSSP на стороне сервера, что препятствует делегированию с клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a318-125">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="2a318-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2a318-126">PARAMETERS</span></span>

### <span data-ttu-id="2a318-127">-Role</span><span class="sxs-lookup"><span data-stu-id="2a318-127">-Role</span></span>
<span data-ttu-id="2a318-128">Указывает, следует ли отключить CredSSP в качестве клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="2a318-128">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="2a318-129">Допустимые значения для этого параметра: Client и Server.</span><span class="sxs-lookup"><span data-stu-id="2a318-129">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="2a318-130">При указании клиента этот командлет выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2a318-130">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="2a318-131">Отключает CredSSP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="2a318-131">Disables CredSSP on the client.</span></span> <span data-ttu-id="2a318-132">Этот командлет задает WS-Management параметру **\<localhost|computername\> \клиент\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="2a318-132">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="2a318-133">Удаляет все параметры WSMan/\* из политики Windows CredSSP, **алловфрешкредентиалс** на клиенте.</span><span class="sxs-lookup"><span data-stu-id="2a318-133">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="2a318-134">При указании Server этот командлет выполняет следующее действие:</span><span class="sxs-lookup"><span data-stu-id="2a318-134">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="2a318-135">Отключает CredSSP на сервере.</span><span class="sxs-lookup"><span data-stu-id="2a318-135">Disables CredSSP on the server.</span></span> <span data-ttu-id="2a318-136">Этот командлет задает для параметра WS-Management **\<localhost|computername\> \сервице\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="2a318-136">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="2a318-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2a318-137">CommonParameters</span></span>
<span data-ttu-id="2a318-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2a318-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a318-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2a318-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2a318-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2a318-140">INPUTS</span></span>

### <span data-ttu-id="2a318-141">None</span><span class="sxs-lookup"><span data-stu-id="2a318-141">None</span></span>
<span data-ttu-id="2a318-142">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="2a318-142">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="2a318-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2a318-143">OUTPUTS</span></span>

### <span data-ttu-id="2a318-144">None</span><span class="sxs-lookup"><span data-stu-id="2a318-144">None</span></span>
<span data-ttu-id="2a318-145">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2a318-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2a318-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2a318-146">NOTES</span></span>

* <span data-ttu-id="2a318-147">Чтобы включить аутентификацию CredSSP, воспользуйтесь командлетом Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="2a318-147">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="2a318-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2a318-148">RELATED LINKS</span></span>

[<span data-ttu-id="2a318-149">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="2a318-149">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="2a318-150">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="2a318-150">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="2a318-151">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2a318-151">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="2a318-152">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2a318-152">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="2a318-153">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a318-153">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="2a318-154">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="2a318-154">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="2a318-155">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a318-155">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="2a318-156">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="2a318-156">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="2a318-157">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a318-157">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="2a318-158">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a318-158">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="2a318-159">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="2a318-159">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="2a318-160">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="2a318-160">Test-WSMan</span></span>](Test-WSMan.md)

