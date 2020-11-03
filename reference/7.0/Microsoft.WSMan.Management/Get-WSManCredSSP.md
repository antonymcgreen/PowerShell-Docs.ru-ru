---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: fa9e2c61654a53e367114ecd347a4eccb3b542c1
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209334"
---
# <span data-ttu-id="69328-103">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="69328-103">Get-WSManCredSSP</span></span>

## <span data-ttu-id="69328-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="69328-104">SYNOPSIS</span></span>
<span data-ttu-id="69328-105">Получает конфигурацию CredSSP для клиента.</span><span class="sxs-lookup"><span data-stu-id="69328-105">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="69328-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="69328-106">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="69328-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="69328-107">DESCRIPTION</span></span>
<span data-ttu-id="69328-108">Командлет **Get-WSManCredSSP** возвращает конфигурацию клиента и сервера, связанную с поставщиком поддержки безопасности учетных данных.</span><span class="sxs-lookup"><span data-stu-id="69328-108">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="69328-109">В выходных данных указано, включена ли аутентификация CredSSP,</span><span class="sxs-lookup"><span data-stu-id="69328-109">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="69328-110">Этот командлет также отображает сведения о конфигурации для политики **Алловфрешкредентиалс** CredSSP.</span><span class="sxs-lookup"><span data-stu-id="69328-110">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="69328-111">При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="69328-111">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="69328-112">Этот тип проверки подлинности предназначен для команд, которые создают удаленный сеанс из другого удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="69328-112">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="69328-113">Например, если вы хотите запустить фоновое задание на удаленном компьютере, используйте такой тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="69328-113">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="69328-114">Командлет выполняет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="69328-114">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="69328-115">Возвращает параметр WS-Management CredSSP на клиенте ( **\<localhost|computername\> \клиент\аус\кредссп** ).</span><span class="sxs-lookup"><span data-stu-id="69328-115">Gets the WS-Management CredSSP setting on the client ( **\<localhost|computername\>\Client\Auth\CredSSP** ).</span></span>
- <span data-ttu-id="69328-116">Получает параметр политики CredSSP Windows **алловфрешкредентиалс** .</span><span class="sxs-lookup"><span data-stu-id="69328-116">Gets the Windows CredSSP policy setting **AllowFreshCredentials** .</span></span>
- <span data-ttu-id="69328-117">Возвращает параметр WS-Management CredSSP на сервере ( **\<localhost|computername\> \сервице\аус\кредссп** ).</span><span class="sxs-lookup"><span data-stu-id="69328-117">Gets the WS-Management CredSSP setting on the server ( **\<localhost|computername\>\Service\Auth\CredSSP** ).</span></span>

<span data-ttu-id="69328-118">Внимание! проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="69328-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="69328-119">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="69328-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="69328-120">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="69328-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="69328-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="69328-121">EXAMPLES</span></span>

### <span data-ttu-id="69328-122">Пример 1. Отображение конфигурации CredSSP</span><span class="sxs-lookup"><span data-stu-id="69328-122">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="69328-123">Эта команда отображает сведения о конфигурации CredSSP как для клиента, так и для сервера.</span><span class="sxs-lookup"><span data-stu-id="69328-123">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="69328-124">В выходных данных указано, настроен ли этот компьютер для CredSSP.</span><span class="sxs-lookup"><span data-stu-id="69328-124">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="69328-125">Если компьютер настроен для CredSSP, выходные данные имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="69328-125">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="69328-126">Если компьютер не настроен для CredSSP, выходные данные имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="69328-126">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="69328-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="69328-127">PARAMETERS</span></span>

### <span data-ttu-id="69328-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="69328-128">CommonParameters</span></span>
<span data-ttu-id="69328-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="69328-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="69328-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="69328-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="69328-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="69328-131">INPUTS</span></span>

### <span data-ttu-id="69328-132">Нет</span><span class="sxs-lookup"><span data-stu-id="69328-132">None</span></span>
<span data-ttu-id="69328-133">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="69328-133">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="69328-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="69328-134">OUTPUTS</span></span>

### <span data-ttu-id="69328-135">Нет</span><span class="sxs-lookup"><span data-stu-id="69328-135">None</span></span>
<span data-ttu-id="69328-136">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="69328-136">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="69328-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="69328-137">NOTES</span></span>

* <span data-ttu-id="69328-138">Чтобы отключить аутентификацию CredSSP, воспользуйтесь командлетом Disable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="69328-138">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="69328-139">Чтобы включить аутентификацию CredSSP, воспользуйтесь командлетом Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="69328-139">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="69328-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="69328-140">RELATED LINKS</span></span>

[<span data-ttu-id="69328-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="69328-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="69328-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="69328-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="69328-143">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="69328-143">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="69328-144">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="69328-144">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="69328-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69328-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="69328-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="69328-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="69328-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69328-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="69328-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="69328-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="69328-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69328-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="69328-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69328-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="69328-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="69328-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="69328-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="69328-152">Test-WSMan</span></span>](Test-WSMan.md)
