---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228002"
---
# <span data-ttu-id="ffc27-103">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="ffc27-103">Remove-LocalGroup</span></span>

## <span data-ttu-id="ffc27-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ffc27-104">SYNOPSIS</span></span>
<span data-ttu-id="ffc27-105">Удаляет локальные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ffc27-105">Deletes local security groups.</span></span>

## <span data-ttu-id="ffc27-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ffc27-106">SYNTAX</span></span>

### <span data-ttu-id="ffc27-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="ffc27-107">InputObject</span></span>

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ffc27-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="ffc27-108">Default</span></span>

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ffc27-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ffc27-109">SecurityIdentifier</span></span>

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ffc27-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ffc27-110">DESCRIPTION</span></span>
<span data-ttu-id="ffc27-111">Командлет **Remove-LocalGroup** Удаляет локальные группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ffc27-111">The **Remove-LocalGroup** cmdlet deletes local security groups.</span></span>
<span data-ttu-id="ffc27-112">Этот командлет удаляет только локальную группу.</span><span class="sxs-lookup"><span data-stu-id="ffc27-112">This cmdlet deletes only a local group.</span></span>
<span data-ttu-id="ffc27-113">Она не удаляет учетные записи пользователей, учетные записи компьютеров или группы, принадлежащие к этой группе.</span><span class="sxs-lookup"><span data-stu-id="ffc27-113">It does not delete the user accounts, computer accounts, or group accounts that belong to that group.</span></span>
<span data-ttu-id="ffc27-114">Невозможно восстановить удаленную группу.</span><span class="sxs-lookup"><span data-stu-id="ffc27-114">You cannot recover a deleted group.</span></span>

<span data-ttu-id="ffc27-115">Если удалить группу, а затем создать другую группу с тем же именем группы, необходимо задать новые разрешения для новой группы.</span><span class="sxs-lookup"><span data-stu-id="ffc27-115">If you delete a group and then create another group that has the same group name, you must set new permissions for the new group.</span></span>
<span data-ttu-id="ffc27-116">Новая группа не наследует разрешения, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="ffc27-116">The new group does not inherit the permissions that were assigned to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="ffc27-117">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="ffc27-117">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="ffc27-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="ffc27-118">EXAMPLES</span></span>

### <span data-ttu-id="ffc27-119">Пример 1. Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="ffc27-119">Example 1: Delete a security group</span></span>

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="ffc27-120">Эта команда удаляет группу с именем SecurityGroup04.</span><span class="sxs-lookup"><span data-stu-id="ffc27-120">This command deletes the group named SecurityGroup04.</span></span>

## <span data-ttu-id="ffc27-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ffc27-121">PARAMETERS</span></span>

### <span data-ttu-id="ffc27-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ffc27-122">-InputObject</span></span>
<span data-ttu-id="ffc27-123">Указывает массив групп безопасности, которые удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ffc27-123">Specifies an array of security groups that this cmdlet deletes.</span></span>
<span data-ttu-id="ffc27-124">Чтобы получить группы, используйте командлет Get-LocalGroup.</span><span class="sxs-lookup"><span data-stu-id="ffc27-124">To obtain groups, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ffc27-125">-Name</span><span class="sxs-lookup"><span data-stu-id="ffc27-125">-Name</span></span>
<span data-ttu-id="ffc27-126">Указывает массив имен групп безопасности, которые удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ffc27-126">Specifies an array of names of the security groups that this cmdlet deletes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ffc27-127">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="ffc27-127">-SID</span></span>
<span data-ttu-id="ffc27-128">Указывает массив идентификаторов безопасности (SID) групп безопасности, которые удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ffc27-128">Specifies an array of security IDs (SIDs) of security groups that this cmdlet deletes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ffc27-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ffc27-129">-Confirm</span></span>
<span data-ttu-id="ffc27-130">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc27-130">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ffc27-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ffc27-131">-WhatIf</span></span>
<span data-ttu-id="ffc27-132">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc27-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ffc27-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ffc27-133">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ffc27-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ffc27-134">CommonParameters</span></span>
<span data-ttu-id="ffc27-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ffc27-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ffc27-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ffc27-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ffc27-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ffc27-137">INPUTS</span></span>

### <span data-ttu-id="ffc27-138">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ffc27-138">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="ffc27-139">Этому командлету можно передать по конвейеру группу безопасности, строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="ffc27-139">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="ffc27-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ffc27-140">OUTPUTS</span></span>

### <span data-ttu-id="ffc27-141">Нет</span><span class="sxs-lookup"><span data-stu-id="ffc27-141">None</span></span>
<span data-ttu-id="ffc27-142">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ffc27-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ffc27-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ffc27-143">NOTES</span></span>

* <span data-ttu-id="ffc27-144">Этот командлет не может удалить следующие группы по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ffc27-144">This cmdlet cannot delete the following default groups:</span></span>

- <span data-ttu-id="ffc27-145">Администраторы</span><span class="sxs-lookup"><span data-stu-id="ffc27-145">Administrators</span></span>
- <span data-ttu-id="ffc27-146">Операторы архива</span><span class="sxs-lookup"><span data-stu-id="ffc27-146">Backup Operators</span></span>
- <span data-ttu-id="ffc27-147">Криптографические операторы</span><span class="sxs-lookup"><span data-stu-id="ffc27-147">Cryptographic Operators</span></span>
- <span data-ttu-id="ffc27-148">Пользователи DCOM</span><span class="sxs-lookup"><span data-stu-id="ffc27-148">Distributed COM Users</span></span>
- <span data-ttu-id="ffc27-149">Читатели журнала событий</span><span class="sxs-lookup"><span data-stu-id="ffc27-149">Event Log Readers</span></span>
- <span data-ttu-id="ffc27-150">Гости</span><span class="sxs-lookup"><span data-stu-id="ffc27-150">Guests</span></span>
- <span data-ttu-id="ffc27-151">Администраторы Hyper-V</span><span class="sxs-lookup"><span data-stu-id="ffc27-151">Hyper-V Administrators</span></span>
- <span data-ttu-id="ffc27-152">IIS_IUSRS</span><span class="sxs-lookup"><span data-stu-id="ffc27-152">IIS_IUSRS</span></span>
- <span data-ttu-id="ffc27-153">Операторы настройки сети</span><span class="sxs-lookup"><span data-stu-id="ffc27-153">Network Configuration Operators</span></span>
- <span data-ttu-id="ffc27-154">Пользователи журнала производительности</span><span class="sxs-lookup"><span data-stu-id="ffc27-154">Performance Log Users</span></span>
- <span data-ttu-id="ffc27-155">пользователи системного монитора.</span><span class="sxs-lookup"><span data-stu-id="ffc27-155">Performance Monitor Users</span></span>
- <span data-ttu-id="ffc27-156">Опытные пользователи</span><span class="sxs-lookup"><span data-stu-id="ffc27-156">Power Users</span></span>
- <span data-ttu-id="ffc27-157">Пользователи удаленного рабочего стола</span><span class="sxs-lookup"><span data-stu-id="ffc27-157">Remote Desktop Users</span></span>
- <span data-ttu-id="ffc27-158">пользователи удаленного управления;</span><span class="sxs-lookup"><span data-stu-id="ffc27-158">Remote Management Users</span></span>
- <span data-ttu-id="ffc27-159">Репликатор</span><span class="sxs-lookup"><span data-stu-id="ffc27-159">Replicator</span></span>
- <span data-ttu-id="ffc27-160">Пользователи</span><span class="sxs-lookup"><span data-stu-id="ffc27-160">Users</span></span>
- <span data-ttu-id="ffc27-161">WinRMRemoteWMIUsers__</span><span class="sxs-lookup"><span data-stu-id="ffc27-161">WinRMRemoteWMIUsers__</span></span>

* <span data-ttu-id="ffc27-162">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="ffc27-162">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="ffc27-163">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="ffc27-163">The possible sources are as follows:</span></span>

- <span data-ttu-id="ffc27-164">Локальная</span><span class="sxs-lookup"><span data-stu-id="ffc27-164">Local</span></span>
- <span data-ttu-id="ffc27-165">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ffc27-165">Active Directory</span></span>
- <span data-ttu-id="ffc27-166">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ffc27-166">Azure Active Directory group</span></span>
- <span data-ttu-id="ffc27-167">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ffc27-167">Microsoft Account</span></span>

<span data-ttu-id="ffc27-168">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="ffc27-168">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="ffc27-169">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="ffc27-169">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="ffc27-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ffc27-170">RELATED LINKS</span></span>

[<span data-ttu-id="ffc27-171">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="ffc27-171">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="ffc27-172">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="ffc27-172">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="ffc27-173">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="ffc27-173">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="ffc27-174">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="ffc27-174">Set-LocalGroup</span></span>](Set-LocalGroup.md)
