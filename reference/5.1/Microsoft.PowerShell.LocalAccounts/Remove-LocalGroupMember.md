---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroupMember
ms.openlocfilehash: 6e6264a65c343657c2f2f87384d76cc3f1554d3d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228005"
---
# <span data-ttu-id="54529-103">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="54529-103">Remove-LocalGroupMember</span></span>

## <span data-ttu-id="54529-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="54529-104">SYNOPSIS</span></span>
<span data-ttu-id="54529-105">Удаляет элементы из локальной группы.</span><span class="sxs-lookup"><span data-stu-id="54529-105">Removes members from a local group.</span></span>

## <span data-ttu-id="54529-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54529-106">SYNTAX</span></span>

### <span data-ttu-id="54529-107">Group</span><span class="sxs-lookup"><span data-stu-id="54529-107">Group</span></span>

```
Remove-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="54529-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="54529-108">Default</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="54529-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="54529-109">SecurityIdentifier</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="54529-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54529-110">DESCRIPTION</span></span>
<span data-ttu-id="54529-111">Командлет **Remove-локалграупмембер** удаляет пользователей или группы из локальной группы.</span><span class="sxs-lookup"><span data-stu-id="54529-111">The **Remove-LocalGroupMember** cmdlet removes users or groups from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="54529-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="54529-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="54529-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="54529-113">EXAMPLES</span></span>

### <span data-ttu-id="54529-114">Пример 1. Удаление членов из группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="54529-114">Example 1: Remove members from the Administrators group</span></span>

```
PS C:\> Remove-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

<span data-ttu-id="54529-115">Эта команда удаляет несколько членов из локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="54529-115">This command removes several members from the local Administrators group.</span></span>
<span data-ttu-id="54529-116">Члены, которые удаляет этот командлет, включают учетную запись локального пользователя, учетная запись Майкрософт, учетную запись Azure Active Directory и группу домена.</span><span class="sxs-lookup"><span data-stu-id="54529-116">The members that this cmdlet removes include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span>
<span data-ttu-id="54529-117">В этом примере используется значение заполнителя для имени пользователя учетной записи в Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="54529-117">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

## <span data-ttu-id="54529-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54529-118">PARAMETERS</span></span>

### <span data-ttu-id="54529-119">-Group</span><span class="sxs-lookup"><span data-stu-id="54529-119">-Group</span></span>
<span data-ttu-id="54529-120">Указывает группу безопасности, из которой этот командлет удаляет члены.</span><span class="sxs-lookup"><span data-stu-id="54529-120">Specifies the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="54529-121">-Member</span><span class="sxs-lookup"><span data-stu-id="54529-121">-Member</span></span>
<span data-ttu-id="54529-122">Указывает массив пользователей или групп, которые этот командлет удаляет из группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="54529-122">Specifies an array of users or groups that this cmdlet removes from a security group.</span></span>
<span data-ttu-id="54529-123">Можно указать пользователей или группы по имени, ИДЕНТИФИКАТОРу безопасности (SID) или объектам **локалпринЦипал** .</span><span class="sxs-lookup"><span data-stu-id="54529-123">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>
<span data-ttu-id="54529-124">Укажите строки SID в S-R-I-S-S.</span><span class="sxs-lookup"><span data-stu-id="54529-124">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="54529-125">.</span><span class="sxs-lookup"><span data-stu-id="54529-125">.</span></span> <span data-ttu-id="54529-126">.</span><span class="sxs-lookup"><span data-stu-id="54529-126">.</span></span>
<span data-ttu-id="54529-127">ЧЧ:ММ:СС...</span><span class="sxs-lookup"><span data-stu-id="54529-127">format.</span></span>

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

### <span data-ttu-id="54529-128">-Name</span><span class="sxs-lookup"><span data-stu-id="54529-128">-Name</span></span>
<span data-ttu-id="54529-129">Указывает имя группы безопасности, из которой этот командлет удаляет члены.</span><span class="sxs-lookup"><span data-stu-id="54529-129">Specifies the name of the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="54529-130">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="54529-130">-SID</span></span>
<span data-ttu-id="54529-131">Указывает идентификатор безопасности группы безопасности, из которой этот командлет удаляет элементы.</span><span class="sxs-lookup"><span data-stu-id="54529-131">Specifies the security ID of the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="54529-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="54529-132">-Confirm</span></span>
<span data-ttu-id="54529-133">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="54529-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="54529-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="54529-134">-WhatIf</span></span>
<span data-ttu-id="54529-135">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="54529-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="54529-136">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="54529-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="54529-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="54529-137">CommonParameters</span></span>
<span data-ttu-id="54529-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="54529-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54529-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="54529-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54529-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="54529-140">INPUTS</span></span>

### <span data-ttu-id="54529-141">System. Management. Automation. Секуритяккаунтсманажер. ЛокалпринЦипал, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="54529-141">System.Management.Automation.SecurityAccountsManager.LocalPrincipal, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="54529-142">Этому командлету можно передать по конвейеру локальный субъект, строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="54529-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="54529-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="54529-143">OUTPUTS</span></span>

### <span data-ttu-id="54529-144">Нет</span><span class="sxs-lookup"><span data-stu-id="54529-144">None</span></span>
<span data-ttu-id="54529-145">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="54529-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="54529-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="54529-146">NOTES</span></span>

* <span data-ttu-id="54529-147">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="54529-147">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="54529-148">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="54529-148">The possible sources are as follows:</span></span>

- <span data-ttu-id="54529-149">Локальная</span><span class="sxs-lookup"><span data-stu-id="54529-149">Local</span></span>
- <span data-ttu-id="54529-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="54529-150">Active Directory</span></span>
- <span data-ttu-id="54529-151">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="54529-151">Azure Active Directory group</span></span>
- <span data-ttu-id="54529-152">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="54529-152">Microsoft Account</span></span>

<span data-ttu-id="54529-153">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="54529-153">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="54529-154">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="54529-154">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="54529-155">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="54529-155">RELATED LINKS</span></span>

[<span data-ttu-id="54529-156">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="54529-156">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="54529-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="54529-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="54529-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="54529-158">New-LocalGroup</span></span>](New-LocalGroup.md)
