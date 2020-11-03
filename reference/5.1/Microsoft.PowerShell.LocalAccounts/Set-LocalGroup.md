---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalGroup
ms.openlocfilehash: 471c3c7bc01bf26dfe9d8eec26e4414464cae02e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228478"
---
# <span data-ttu-id="dc975-103">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="dc975-103">Set-LocalGroup</span></span>

## <span data-ttu-id="dc975-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dc975-104">SYNOPSIS</span></span>
<span data-ttu-id="dc975-105">Изменяет локальную группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc975-105">Changes a local security group.</span></span>

## <span data-ttu-id="dc975-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dc975-106">SYNTAX</span></span>

### <span data-ttu-id="dc975-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="dc975-107">InputObject</span></span>

```
Set-LocalGroup -Description <String> [-InputObject] <LocalGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dc975-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc975-108">Default</span></span>

```
Set-LocalGroup -Description <String> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dc975-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="dc975-109">SecurityIdentifier</span></span>

```
Set-LocalGroup -Description <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dc975-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dc975-110">DESCRIPTION</span></span>
<span data-ttu-id="dc975-111">Командлет **Set-LocalGroup** изменяет локальную группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc975-111">The **Set-LocalGroup** cmdlet changes a local security group.</span></span>

## <span data-ttu-id="dc975-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="dc975-112">EXAMPLES</span></span>

### <span data-ttu-id="dc975-113">Пример 1. изменение описания группы</span><span class="sxs-lookup"><span data-stu-id="dc975-113">Example 1: Change a group description</span></span>

```
PS C:\> Set-LocalGroup -Name "SecurityGroup04" -Description "This is a sample description."
```

<span data-ttu-id="dc975-114">Эта команда изменяет описание локальной группы.</span><span class="sxs-lookup"><span data-stu-id="dc975-114">This command changes the description of a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="dc975-115">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="dc975-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="dc975-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dc975-116">PARAMETERS</span></span>

### <span data-ttu-id="dc975-117">-Description</span><span class="sxs-lookup"><span data-stu-id="dc975-117">-Description</span></span>
<span data-ttu-id="dc975-118">Задает комментарий для группы.</span><span class="sxs-lookup"><span data-stu-id="dc975-118">Specifies a comment for the group.</span></span>
<span data-ttu-id="dc975-119">Максимальная длина — 48 символов.</span><span class="sxs-lookup"><span data-stu-id="dc975-119">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc975-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dc975-120">-InputObject</span></span>
<span data-ttu-id="dc975-121">Указывает группу безопасности, которую изменяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="dc975-121">Specifies the security group that this cmdlet changes.</span></span>
<span data-ttu-id="dc975-122">Чтобы получить группу безопасности, используйте командлет Get-LocalGroup.</span><span class="sxs-lookup"><span data-stu-id="dc975-122">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

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

### <span data-ttu-id="dc975-123">-Name</span><span class="sxs-lookup"><span data-stu-id="dc975-123">-Name</span></span>
<span data-ttu-id="dc975-124">Указывает имя группы безопасности, которую изменяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="dc975-124">Specifies the name of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="dc975-125">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="dc975-125">-SID</span></span>
<span data-ttu-id="dc975-126">Указывает идентификатор безопасности (SID) группы безопасности, которую изменяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="dc975-126">Specifies the security ID (SID) of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="dc975-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dc975-127">-Confirm</span></span>
<span data-ttu-id="dc975-128">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="dc975-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dc975-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dc975-129">-WhatIf</span></span>
<span data-ttu-id="dc975-130">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="dc975-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="dc975-131">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="dc975-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dc975-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dc975-132">CommonParameters</span></span>
<span data-ttu-id="dc975-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dc975-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dc975-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dc975-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dc975-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dc975-135">INPUTS</span></span>

### <span data-ttu-id="dc975-136">System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="dc975-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="dc975-137">Этому командлету можно передать по конвейеру группу безопасности, строку или идентификатор безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc975-137">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="dc975-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dc975-138">OUTPUTS</span></span>

### <span data-ttu-id="dc975-139">Нет</span><span class="sxs-lookup"><span data-stu-id="dc975-139">None</span></span>
<span data-ttu-id="dc975-140">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="dc975-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dc975-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dc975-141">NOTES</span></span>

* <span data-ttu-id="dc975-142">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="dc975-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="dc975-143">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="dc975-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="dc975-144">Локальная</span><span class="sxs-lookup"><span data-stu-id="dc975-144">Local</span></span>
- <span data-ttu-id="dc975-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="dc975-145">Active Directory</span></span>
- <span data-ttu-id="dc975-146">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dc975-146">Azure Active Directory group</span></span>
- <span data-ttu-id="dc975-147">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dc975-147">Microsoft Account</span></span>

<span data-ttu-id="dc975-148">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="dc975-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="dc975-149">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="dc975-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="dc975-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dc975-150">RELATED LINKS</span></span>

[<span data-ttu-id="dc975-151">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="dc975-151">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="dc975-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="dc975-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="dc975-153">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="dc975-153">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="dc975-154">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="dc975-154">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)
