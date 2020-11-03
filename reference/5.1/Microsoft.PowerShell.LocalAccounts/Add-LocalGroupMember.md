---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226629"
---
# <span data-ttu-id="e3c87-103">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e3c87-103">Add-LocalGroupMember</span></span>

## <span data-ttu-id="e3c87-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e3c87-104">SYNOPSIS</span></span>
<span data-ttu-id="e3c87-105">Добавляет элементы в локальную группу.</span><span class="sxs-lookup"><span data-stu-id="e3c87-105">Adds members to a local group.</span></span>

## <span data-ttu-id="e3c87-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3c87-106">SYNTAX</span></span>

### <span data-ttu-id="e3c87-107">Group</span><span class="sxs-lookup"><span data-stu-id="e3c87-107">Group</span></span>

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="e3c87-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e3c87-108">Default</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e3c87-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e3c87-109">SecurityIdentifier</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e3c87-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3c87-110">DESCRIPTION</span></span>

<span data-ttu-id="e3c87-111">`Add-LocalGroupMember`Командлет добавляет пользователей или группы в локальную группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="e3c87-111">The `Add-LocalGroupMember` cmdlet adds users or groups to a local security group.</span></span> <span data-ttu-id="e3c87-112">Все права и разрешения, присвоенные группе, действительны для всех членов данной группы.</span><span class="sxs-lookup"><span data-stu-id="e3c87-112">All the rights and permissions that are assigned to a group are assigned to all members of that group.</span></span>

<span data-ttu-id="e3c87-113">Члены группы "Администраторы" на локальном компьютере имеют разрешения полного доступа на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3c87-113">Members of the Administrators group on a local computer have Full Control permissions on that computer.</span></span> <span data-ttu-id="e3c87-114">Ограничьте число пользователей в группе "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="e3c87-114">Limit the number of users in the Administrators group.</span></span>

<span data-ttu-id="e3c87-115">Если компьютер подключен к домену, в локальную группу можно добавлять учетные записи пользователей, компьютеров и групп из этого домена и из доверенных доменов.</span><span class="sxs-lookup"><span data-stu-id="e3c87-115">If the computer is joined to a domain, you can add user accounts, computer accounts, and group accounts from that domain and from trusted domains to a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="e3c87-116">Если компьютер присоединен к домену и вы пытаетесь добавить локального пользователя с тем же именем, что и член домена, он добавляет член домена.</span><span class="sxs-lookup"><span data-stu-id="e3c87-116">If the computer is joined to a domain and you try to add a local user that has the same name as a member of the domain it adds the domain member.</span></span>

## <span data-ttu-id="e3c87-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="e3c87-117">EXAMPLES</span></span>

### <span data-ttu-id="e3c87-118">Пример 1. Добавление членов в группу "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="e3c87-118">Example 1: Add members to the Administrators group</span></span>

<span data-ttu-id="e3c87-119">Эта команда добавляет несколько членов в локальную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="e3c87-119">This command adds several members to the local Administrators group.</span></span> <span data-ttu-id="e3c87-120">Новые члены включают учетную запись локального пользователя, учетная запись Майкрософт, учетную запись Azure Active Directory и группу домена.</span><span class="sxs-lookup"><span data-stu-id="e3c87-120">The new members include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span> <span data-ttu-id="e3c87-121">В этом примере используется значение заполнителя для имени пользователя учетной записи в Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e3c87-121">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## <span data-ttu-id="e3c87-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3c87-122">PARAMETERS</span></span>

### <span data-ttu-id="e3c87-123">-Group</span><span class="sxs-lookup"><span data-stu-id="e3c87-123">-Group</span></span>

<span data-ttu-id="e3c87-124">Указывает группу безопасности, в которую этот командлет добавляет члены.</span><span class="sxs-lookup"><span data-stu-id="e3c87-124">Specifies the security group to which this cmdlet adds members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3c87-125">-Member</span><span class="sxs-lookup"><span data-stu-id="e3c87-125">-Member</span></span>

<span data-ttu-id="e3c87-126">Указывает массив пользователей или групп, которые этот командлет добавляет в группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="e3c87-126">Specifies an array of users or groups that this cmdlet adds to a security group.</span></span> <span data-ttu-id="e3c87-127">Можно указать пользователей или группы по имени, ИДЕНТИФИКАТОРу безопасности (SID) или объектам **локалпринЦипал** .</span><span class="sxs-lookup"><span data-stu-id="e3c87-127">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e3c87-128">-Name</span><span class="sxs-lookup"><span data-stu-id="e3c87-128">-Name</span></span>

<span data-ttu-id="e3c87-129">Указывает имя группы безопасности, в которую этот командлет добавляет члены.</span><span class="sxs-lookup"><span data-stu-id="e3c87-129">Specifies the name of the security group to which this cmdlet adds members.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3c87-130">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="e3c87-130">-SID</span></span>

<span data-ttu-id="e3c87-131">Указывает идентификатор безопасности группы безопасности, в которую этот командлет добавляет члены.</span><span class="sxs-lookup"><span data-stu-id="e3c87-131">Specifies the security ID of the security group to which this cmdlet adds members.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3c87-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e3c87-132">-Confirm</span></span>

<span data-ttu-id="e3c87-133">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e3c87-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e3c87-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e3c87-134">-WhatIf</span></span>

<span data-ttu-id="e3c87-135">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e3c87-135">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e3c87-136">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e3c87-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e3c87-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e3c87-137">CommonParameters</span></span>

<span data-ttu-id="e3c87-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3c87-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3c87-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3c87-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3c87-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e3c87-140">INPUTS</span></span>

### <span data-ttu-id="e3c87-141">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e3c87-141">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="e3c87-142">Этому командлету можно передать по конвейеру локальный субъект, строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="e3c87-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="e3c87-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e3c87-143">OUTPUTS</span></span>

### <span data-ttu-id="e3c87-144">Нет</span><span class="sxs-lookup"><span data-stu-id="e3c87-144">None</span></span>

<span data-ttu-id="e3c87-145">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e3c87-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e3c87-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e3c87-146">NOTES</span></span>

<span data-ttu-id="e3c87-147">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="e3c87-147">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

<span data-ttu-id="e3c87-148">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="e3c87-148">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="e3c87-149">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="e3c87-149">The possible sources are as follows:</span></span>

- <span data-ttu-id="e3c87-150">Локальная</span><span class="sxs-lookup"><span data-stu-id="e3c87-150">Local</span></span>
- <span data-ttu-id="e3c87-151">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3c87-151">Active Directory</span></span>
- <span data-ttu-id="e3c87-152">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3c87-152">Azure Active Directory group</span></span>
- <span data-ttu-id="e3c87-153">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e3c87-153">Microsoft Account</span></span>

<span data-ttu-id="e3c87-154">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="e3c87-154">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="e3c87-155">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="e3c87-155">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="e3c87-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e3c87-156">RELATED LINKS</span></span>

[<span data-ttu-id="e3c87-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e3c87-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="e3c87-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e3c87-158">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="e3c87-159">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e3c87-159">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
