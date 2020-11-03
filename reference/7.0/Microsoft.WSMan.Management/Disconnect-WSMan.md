---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: a754b6530ecd8b3153d82327a246cbb387d53dd5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226081"
---
# <span data-ttu-id="e3589-103">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e3589-103">Disconnect-WSMan</span></span>

## <span data-ttu-id="e3589-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e3589-104">SYNOPSIS</span></span>
<span data-ttu-id="e3589-105">Отключает клиента от службы удаленного управления Windows на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3589-105">Disconnects the client from the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="e3589-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3589-106">SYNTAX</span></span>

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="e3589-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3589-107">DESCRIPTION</span></span>
<span data-ttu-id="e3589-108">Командлет **Disconnect-WSMan** отключает клиента от службы WinRM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3589-108">The **Disconnect-WSMan** cmdlet disconnects the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="e3589-109">Если сеанс WS-Management сохранен в переменной, объект сеанса остается в переменной, но состояние сеанса WS-Management закрывается.</span><span class="sxs-lookup"><span data-stu-id="e3589-109">If you saved the WS-Management session in a variable, the session object remains in the variable, but the state of the WS-Management session is Closed.</span></span>
<span data-ttu-id="e3589-110">Этот командлет можно использовать в контексте поставщика WSMan для отключения клиента от службы удаленного управления Windows на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3589-110">You can use this cmdlet within the context of the WSMan provider to disconnect the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="e3589-111">Однако его также можно использовать для отключения от службы удаленного управления Windows на удаленных компьютерах перед изменением поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="e3589-111">However, you can also use this cmdlet to disconnect from the WinRM service on remote computers before you change to the WSMan provider.</span></span>

<span data-ttu-id="e3589-112">Дополнительные сведения о способах подключения к службе удаленного управления Windows на удаленном компьютере см. в описании Connect-WSMan.</span><span class="sxs-lookup"><span data-stu-id="e3589-112">For more information about how to connect to the WinRM service on a remote computer, see Connect-WSMan.</span></span>

## <span data-ttu-id="e3589-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="e3589-113">EXAMPLES</span></span>

### <span data-ttu-id="e3589-114">Пример 1. Удаление подключения к удаленному компьютеру</span><span class="sxs-lookup"><span data-stu-id="e3589-114">Example 1: Delete a connection to a remote computer</span></span>

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

<span data-ttu-id="e3589-115">Эта команда удаляет подключение к удаленному компьютеру с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="e3589-115">This command deletes the connection to the remote computer named server01.</span></span>

<span data-ttu-id="e3589-116">Этот командлет обычно используется в контексте WSMan поставщика для отключения от удаленного компьютера, в данном случае это компьютер server01.</span><span class="sxs-lookup"><span data-stu-id="e3589-116">This cmdlet is generally used within the context of the WSMan provider to disconnect from a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="e3589-117">Однако можно также использовать **Disconnect-WSMan** для удаления соединений с удаленными компьютерами перед изменением поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="e3589-117">However, you can also use **Disconnect-WSMan** to remove connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="e3589-118">Эти подключения не отображаются в списке ComputerName.</span><span class="sxs-lookup"><span data-stu-id="e3589-118">Those connections do not appear in the ComputerName list.</span></span>

## <span data-ttu-id="e3589-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3589-119">PARAMETERS</span></span>

### <span data-ttu-id="e3589-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e3589-120">-ComputerName</span></span>
<span data-ttu-id="e3589-121">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="e3589-121">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="e3589-122">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="e3589-122">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="e3589-123">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="e3589-123">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="e3589-124">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3589-124">The local computer is the default.</span></span>
<span data-ttu-id="e3589-125">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="e3589-125">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="e3589-126">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="e3589-126">You can pipe a value for this parameter to the cmdlet.</span></span>

<span data-ttu-id="e3589-127">Отключиться от локального узла нельзя.</span><span class="sxs-lookup"><span data-stu-id="e3589-127">You cannot disconnect from the local host.</span></span>
<span data-ttu-id="e3589-128">Это значит, что невозможно отключить подключение по умолчанию к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="e3589-128">That is, you cannot disconnect the default connection to the local computer.</span></span>
<span data-ttu-id="e3589-129">Однако при создании отдельного соединения с локальным компьютером, например с помощью имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="e3589-129">However, if you create a separate connection to the local computer, for example, by using the computer name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3589-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e3589-130">CommonParameters</span></span>
<span data-ttu-id="e3589-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3589-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3589-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3589-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3589-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e3589-133">INPUTS</span></span>

### <span data-ttu-id="e3589-134">Нет</span><span class="sxs-lookup"><span data-stu-id="e3589-134">None</span></span>
<span data-ttu-id="e3589-135">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="e3589-135">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="e3589-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e3589-136">OUTPUTS</span></span>

### <span data-ttu-id="e3589-137">Нет</span><span class="sxs-lookup"><span data-stu-id="e3589-137">None</span></span>
<span data-ttu-id="e3589-138">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e3589-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e3589-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e3589-139">NOTES</span></span>

## <span data-ttu-id="e3589-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e3589-140">RELATED LINKS</span></span>

[<span data-ttu-id="e3589-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e3589-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="e3589-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e3589-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="e3589-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e3589-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="e3589-144">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e3589-144">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="e3589-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e3589-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="e3589-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="e3589-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="e3589-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e3589-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="e3589-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="e3589-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="e3589-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e3589-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="e3589-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e3589-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="e3589-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="e3589-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="e3589-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="e3589-152">Test-WSMan</span></span>](Test-WSMan.md)
