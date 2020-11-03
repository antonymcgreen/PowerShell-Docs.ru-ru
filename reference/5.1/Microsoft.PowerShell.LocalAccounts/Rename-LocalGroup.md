---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalGroup
ms.openlocfilehash: 566d33bdeb52323cca41fa9757d36334b40f1654
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228477"
---
# <span data-ttu-id="5923d-103">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="5923d-103">Rename-LocalGroup</span></span>

## <span data-ttu-id="5923d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5923d-104">SYNOPSIS</span></span>
<span data-ttu-id="5923d-105">Переименовывает локальную группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="5923d-105">Renames a local security group.</span></span>

## <span data-ttu-id="5923d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5923d-106">SYNTAX</span></span>

### <span data-ttu-id="5923d-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="5923d-107">InputObject</span></span>

```
Rename-LocalGroup [-InputObject] <LocalGroup> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5923d-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="5923d-108">Default</span></span>

```
Rename-LocalGroup [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5923d-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="5923d-109">SecurityIdentifier</span></span>

```
Rename-LocalGroup [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5923d-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5923d-110">DESCRIPTION</span></span>
<span data-ttu-id="5923d-111">Командлет **Rename-LocalGroup** переименовывает локальную группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="5923d-111">The **Rename-LocalGroup** cmdlet renames a local security group.</span></span>

> [!NOTE]
> <span data-ttu-id="5923d-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="5923d-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="5923d-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="5923d-113">EXAMPLES</span></span>

### <span data-ttu-id="5923d-114">Пример 1. изменение имени группы</span><span class="sxs-lookup"><span data-stu-id="5923d-114">Example 1: Change the name of a group</span></span>

```
PS C:\> Rename-LocalGroup -Name "SecurityGroup" -NewName "SecurityGroup04"
```

<span data-ttu-id="5923d-115">Эта команда переименовывает группу безопасности с именем SecurityGroup.</span><span class="sxs-lookup"><span data-stu-id="5923d-115">This command renames a security group named SecurityGroup.</span></span>

## <span data-ttu-id="5923d-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5923d-116">PARAMETERS</span></span>

### <span data-ttu-id="5923d-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5923d-117">-InputObject</span></span>
<span data-ttu-id="5923d-118">Указывает группу безопасности, которую этот командлет переименовывает.</span><span class="sxs-lookup"><span data-stu-id="5923d-118">Specifies the security group that this cmdlet renames.</span></span>
<span data-ttu-id="5923d-119">Чтобы получить группу безопасности, используйте командлет Get-LocalGroup.</span><span class="sxs-lookup"><span data-stu-id="5923d-119">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5923d-120">-Name</span><span class="sxs-lookup"><span data-stu-id="5923d-120">-Name</span></span>
<span data-ttu-id="5923d-121">Указывает имя группы безопасности, которую этот командлет переименовывает.</span><span class="sxs-lookup"><span data-stu-id="5923d-121">Specifies the name of the security group that this cmdlet renames.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5923d-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="5923d-122">-NewName</span></span>
<span data-ttu-id="5923d-123">Указывает новое имя для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="5923d-123">Specifies a new name for the security group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5923d-124">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="5923d-124">-SID</span></span>
<span data-ttu-id="5923d-125">Указывает идентификатор безопасности (SID) группы безопасности, которую переименовывает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="5923d-125">Specifies the security ID (SID) of a security group that this cmdlet renames.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5923d-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5923d-126">-Confirm</span></span>
<span data-ttu-id="5923d-127">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5923d-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5923d-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5923d-128">-WhatIf</span></span>
<span data-ttu-id="5923d-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5923d-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5923d-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5923d-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5923d-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5923d-131">CommonParameters</span></span>
<span data-ttu-id="5923d-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5923d-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5923d-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5923d-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5923d-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5923d-134">INPUTS</span></span>

### <span data-ttu-id="5923d-135">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="5923d-135">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="5923d-136">Этому командлету можно передать по конвейеру группу безопасности, строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="5923d-136">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="5923d-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5923d-137">OUTPUTS</span></span>

### <span data-ttu-id="5923d-138">Нет</span><span class="sxs-lookup"><span data-stu-id="5923d-138">None</span></span>
<span data-ttu-id="5923d-139">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5923d-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5923d-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5923d-140">NOTES</span></span>

* <span data-ttu-id="5923d-141">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="5923d-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="5923d-142">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="5923d-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="5923d-143">Локальная</span><span class="sxs-lookup"><span data-stu-id="5923d-143">Local</span></span>
- <span data-ttu-id="5923d-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="5923d-144">Active Directory</span></span>
- <span data-ttu-id="5923d-145">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5923d-145">Azure Active Directory group</span></span>
- <span data-ttu-id="5923d-146">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5923d-146">Microsoft Account</span></span>

<span data-ttu-id="5923d-147">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="5923d-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="5923d-148">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="5923d-148">For earlier  versions, the property is blank.</span></span>

## <span data-ttu-id="5923d-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5923d-149">RELATED LINKS</span></span>

[<span data-ttu-id="5923d-150">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="5923d-150">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="5923d-151">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="5923d-151">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="5923d-152">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="5923d-152">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="5923d-153">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="5923d-153">Set-LocalGroup</span></span>](Set-LocalGroup.md)
