---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: 9830d1feb31e9cca735a7ac8d2ed9d2ec50380b5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605029"
---
# <span data-ttu-id="47e50-102">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="47e50-102">Get-WSManCredSSP</span></span>

## <span data-ttu-id="47e50-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="47e50-103">SYNOPSIS</span></span>
<span data-ttu-id="47e50-104">Получает конфигурацию CredSSP для клиента.</span><span class="sxs-lookup"><span data-stu-id="47e50-104">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="47e50-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47e50-105">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="47e50-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47e50-106">DESCRIPTION</span></span>
<span data-ttu-id="47e50-107">Командлет **Get-WSManCredSSP** возвращает конфигурацию клиента и сервера, связанную с поставщиком поддержки безопасности учетных данных.</span><span class="sxs-lookup"><span data-stu-id="47e50-107">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="47e50-108">В выходных данных указано, включена ли аутентификация CredSSP,</span><span class="sxs-lookup"><span data-stu-id="47e50-108">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="47e50-109">Этот командлет также отображает сведения о конфигурации для политики **Алловфрешкредентиалс** CredSSP.</span><span class="sxs-lookup"><span data-stu-id="47e50-109">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="47e50-110">При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="47e50-110">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="47e50-111">Этот тип проверки подлинности предназначен для команд, которые создают удаленный сеанс из другого удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="47e50-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="47e50-112">Например, если вы хотите запустить фоновое задание на удаленном компьютере, используйте такой тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="47e50-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="47e50-113">Командлет выполняет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="47e50-113">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="47e50-114">Возвращает параметр WS-Management CredSSP на клиенте (**\<localhost|computername\> \клиент\аус\кредссп**).</span><span class="sxs-lookup"><span data-stu-id="47e50-114">Gets the WS-Management CredSSP setting on the client (**\<localhost|computername\>\Client\Auth\CredSSP**).</span></span>
- <span data-ttu-id="47e50-115">Получает параметр политики CredSSP Windows **алловфрешкредентиалс**.</span><span class="sxs-lookup"><span data-stu-id="47e50-115">Gets the Windows CredSSP policy setting **AllowFreshCredentials**.</span></span>
- <span data-ttu-id="47e50-116">Возвращает параметр WS-Management CredSSP на сервере (**\<localhost|computername\> \сервице\аус\кредссп**).</span><span class="sxs-lookup"><span data-stu-id="47e50-116">Gets the WS-Management CredSSP setting on the server (**\<localhost|computername\>\Service\Auth\CredSSP**).</span></span>

<span data-ttu-id="47e50-117">Внимание! проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="47e50-117">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="47e50-118">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="47e50-118">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="47e50-119">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="47e50-119">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="47e50-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="47e50-120">EXAMPLES</span></span>

### <span data-ttu-id="47e50-121">Пример 1. Отображение конфигурации CredSSP</span><span class="sxs-lookup"><span data-stu-id="47e50-121">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="47e50-122">Эта команда отображает сведения о конфигурации CredSSP как для клиента, так и для сервера.</span><span class="sxs-lookup"><span data-stu-id="47e50-122">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="47e50-123">В выходных данных указано, настроен ли этот компьютер для CredSSP.</span><span class="sxs-lookup"><span data-stu-id="47e50-123">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="47e50-124">Если компьютер настроен для CredSSP, выходные данные имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="47e50-124">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="47e50-125">Если компьютер не настроен для CredSSP, выходные данные имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="47e50-125">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="47e50-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47e50-126">PARAMETERS</span></span>

### <span data-ttu-id="47e50-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="47e50-127">CommonParameters</span></span>
<span data-ttu-id="47e50-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47e50-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47e50-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47e50-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47e50-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="47e50-130">INPUTS</span></span>

### <span data-ttu-id="47e50-131">None</span><span class="sxs-lookup"><span data-stu-id="47e50-131">None</span></span>
<span data-ttu-id="47e50-132">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="47e50-132">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="47e50-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="47e50-133">OUTPUTS</span></span>

### <span data-ttu-id="47e50-134">None</span><span class="sxs-lookup"><span data-stu-id="47e50-134">None</span></span>
<span data-ttu-id="47e50-135">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="47e50-135">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="47e50-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="47e50-136">NOTES</span></span>

* <span data-ttu-id="47e50-137">Чтобы отключить аутентификацию CredSSP, воспользуйтесь командлетом Disable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="47e50-137">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="47e50-138">Чтобы включить аутентификацию CredSSP, воспользуйтесь командлетом Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="47e50-138">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="47e50-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="47e50-139">RELATED LINKS</span></span>

[<span data-ttu-id="47e50-140">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="47e50-140">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="47e50-141">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="47e50-141">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="47e50-142">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="47e50-142">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="47e50-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="47e50-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="47e50-144">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="47e50-144">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="47e50-145">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="47e50-145">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="47e50-146">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="47e50-146">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="47e50-147">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="47e50-147">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="47e50-148">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="47e50-148">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="47e50-149">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="47e50-149">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="47e50-150">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="47e50-150">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="47e50-151">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="47e50-151">Test-WSMan</span></span>](Test-WSMan.md)

