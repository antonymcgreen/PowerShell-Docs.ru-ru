---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: c34de849d664fe0c0a02b695f0fc72f54cf1ae3d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233078"
---
# <span data-ttu-id="fdc82-103">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fdc82-103">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="fdc82-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fdc82-104">SYNOPSIS</span></span>
<span data-ttu-id="fdc82-105">Отключает проверку подлинности CredSSP на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdc82-105">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="fdc82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdc82-106">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="fdc82-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fdc82-107">DESCRIPTION</span></span>
<span data-ttu-id="fdc82-108">Командлет **Disable-WSManCredSSP** отключает проверку подлинности на уровне поставщика поддержки учетных данных (CredSSP) на клиенте или на компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="fdc82-108">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="fdc82-109">При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="fdc82-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="fdc82-110">Используйте этот командлет для отключения CredSSP на клиенте, указав Client в параметре *Role* .</span><span class="sxs-lookup"><span data-stu-id="fdc82-110">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="fdc82-111">Этот командлет выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fdc82-111">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="fdc82-112">Отключает CredSSP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="fdc82-112">Disables CredSSP on the client.</span></span> <span data-ttu-id="fdc82-113">Этот командлет задает для параметра WS-Management **\<localhost|computername\> \клиент\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="fdc82-113">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="fdc82-114">Удаляет все параметры WSMan/\* из политики Windows CredSSP, **алловфрешкредентиалс** на клиенте.</span><span class="sxs-lookup"><span data-stu-id="fdc82-114">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="fdc82-115">Используйте этот командлет для отключения CredSSP на сервере путем указания сервера в *роли* .</span><span class="sxs-lookup"><span data-stu-id="fdc82-115">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role* .</span></span>
<span data-ttu-id="fdc82-116">Этот командлет выполняет следующее действие:</span><span class="sxs-lookup"><span data-stu-id="fdc82-116">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="fdc82-117">Отключает CredSSP на сервере.</span><span class="sxs-lookup"><span data-stu-id="fdc82-117">Disables CredSSP on the server.</span></span> <span data-ttu-id="fdc82-118">Этот командлет задает для параметра WS-Management **\<localhost|computername\> \сервице\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="fdc82-118">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="fdc82-119">Внимание! проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="fdc82-119">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="fdc82-120">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="fdc82-120">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="fdc82-121">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="fdc82-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="fdc82-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="fdc82-122">EXAMPLES</span></span>

### <span data-ttu-id="fdc82-123">Пример 1. Отключение CredSSP на клиенте</span><span class="sxs-lookup"><span data-stu-id="fdc82-123">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="fdc82-124">Эта команда отключает CredSSP на стороне клиента, что препятствует делегированию на серверы.</span><span class="sxs-lookup"><span data-stu-id="fdc82-124">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="fdc82-125">Пример 2. Отключение CredSSP на сервере</span><span class="sxs-lookup"><span data-stu-id="fdc82-125">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="fdc82-126">Эта команда отключает CredSSP на стороне сервера, что препятствует делегированию с клиентов.</span><span class="sxs-lookup"><span data-stu-id="fdc82-126">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="fdc82-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdc82-127">PARAMETERS</span></span>

### <span data-ttu-id="fdc82-128">-Role</span><span class="sxs-lookup"><span data-stu-id="fdc82-128">-Role</span></span>
<span data-ttu-id="fdc82-129">Указывает, следует ли отключить CredSSP в качестве клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="fdc82-129">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="fdc82-130">Допустимые значения для этого параметра: Client и Server.</span><span class="sxs-lookup"><span data-stu-id="fdc82-130">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="fdc82-131">При указании клиента этот командлет выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fdc82-131">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="fdc82-132">Отключает CredSSP на клиенте.</span><span class="sxs-lookup"><span data-stu-id="fdc82-132">Disables CredSSP on the client.</span></span> <span data-ttu-id="fdc82-133">Этот командлет задает WS-Management параметру **\<localhost|computername\> \клиент\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="fdc82-133">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="fdc82-134">Удаляет все параметры WSMan/\* из политики Windows CredSSP, **алловфрешкредентиалс** на клиенте.</span><span class="sxs-lookup"><span data-stu-id="fdc82-134">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="fdc82-135">При указании Server этот командлет выполняет следующее действие:</span><span class="sxs-lookup"><span data-stu-id="fdc82-135">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="fdc82-136">Отключает CredSSP на сервере.</span><span class="sxs-lookup"><span data-stu-id="fdc82-136">Disables CredSSP on the server.</span></span> <span data-ttu-id="fdc82-137">Этот командлет задает для параметра WS-Management **\<localhost|computername\> \сервице\аус\кредссп** значение false.</span><span class="sxs-lookup"><span data-stu-id="fdc82-137">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="fdc82-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fdc82-138">CommonParameters</span></span>
<span data-ttu-id="fdc82-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fdc82-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fdc82-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fdc82-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fdc82-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fdc82-141">INPUTS</span></span>

### <span data-ttu-id="fdc82-142">Нет</span><span class="sxs-lookup"><span data-stu-id="fdc82-142">None</span></span>
<span data-ttu-id="fdc82-143">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="fdc82-143">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="fdc82-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fdc82-144">OUTPUTS</span></span>

### <span data-ttu-id="fdc82-145">Нет</span><span class="sxs-lookup"><span data-stu-id="fdc82-145">None</span></span>
<span data-ttu-id="fdc82-146">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fdc82-146">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fdc82-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fdc82-147">NOTES</span></span>

* <span data-ttu-id="fdc82-148">Чтобы включить аутентификацию CredSSP, воспользуйтесь командлетом Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="fdc82-148">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="fdc82-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fdc82-149">RELATED LINKS</span></span>

[<span data-ttu-id="fdc82-150">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fdc82-150">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="fdc82-151">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fdc82-151">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="fdc82-152">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fdc82-152">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="fdc82-153">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fdc82-153">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="fdc82-154">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fdc82-154">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="fdc82-155">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="fdc82-155">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="fdc82-156">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fdc82-156">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="fdc82-157">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="fdc82-157">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="fdc82-158">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fdc82-158">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="fdc82-159">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fdc82-159">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="fdc82-160">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="fdc82-160">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="fdc82-161">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="fdc82-161">Test-WSMan</span></span>](Test-WSMan.md)
