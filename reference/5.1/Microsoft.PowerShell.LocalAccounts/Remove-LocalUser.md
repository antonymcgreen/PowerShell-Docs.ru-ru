---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalUser
ms.openlocfilehash: de1054971dab19f8cfae654208488ca9ce5e17e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228482"
---
# <span data-ttu-id="f63af-103">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-103">Remove-LocalUser</span></span>

## <span data-ttu-id="f63af-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f63af-104">SYNOPSIS</span></span>
<span data-ttu-id="f63af-105">Удаляет локальные учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="f63af-105">Deletes local user accounts.</span></span>

## <span data-ttu-id="f63af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f63af-106">SYNTAX</span></span>

### <span data-ttu-id="f63af-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="f63af-107">InputObject</span></span>

```
Remove-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f63af-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="f63af-108">Default</span></span>

```
Remove-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f63af-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="f63af-109">SecurityIdentifier</span></span>

```
Remove-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f63af-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f63af-110">DESCRIPTION</span></span>
<span data-ttu-id="f63af-111">Командлет **Remove-LocalUser** Удаляет локальные учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="f63af-111">The **Remove-LocalUser** cmdlet deletes local user accounts.</span></span>

## <span data-ttu-id="f63af-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="f63af-112">EXAMPLES</span></span>

### <span data-ttu-id="f63af-113">Пример 1. Удаление учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="f63af-113">Example 1: Delete a user account</span></span>

```
PS C:\> Remove-LocalUser -Name "AdminContoso02"
```

<span data-ttu-id="f63af-114">Эта команда удаляет учетную запись пользователя с именем AdminContoso02.</span><span class="sxs-lookup"><span data-stu-id="f63af-114">This command deletes the user account named AdminContoso02.</span></span>

> [!NOTE]
> <span data-ttu-id="f63af-115">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="f63af-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="f63af-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f63af-116">PARAMETERS</span></span>

### <span data-ttu-id="f63af-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f63af-117">-InputObject</span></span>
<span data-ttu-id="f63af-118">Указывает массив учетных записей пользователей, которые удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="f63af-118">Specifies an array of user accounts that this cmdlet deletes.</span></span>
<span data-ttu-id="f63af-119">Чтобы получить учетную запись пользователя, используйте командлет Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="f63af-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f63af-120">-Name</span><span class="sxs-lookup"><span data-stu-id="f63af-120">-Name</span></span>
<span data-ttu-id="f63af-121">Указывает массив имен учетных записей пользователей, которые удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="f63af-121">Specifies an array of names of the user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="f63af-122">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="f63af-122">-SID</span></span>
<span data-ttu-id="f63af-123">Указывает массив идентификаторов безопасности (SID) учетных записей пользователей, которые удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="f63af-123">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="f63af-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f63af-124">-Confirm</span></span>
<span data-ttu-id="f63af-125">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f63af-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f63af-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f63af-126">-WhatIf</span></span>
<span data-ttu-id="f63af-127">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f63af-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f63af-128">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f63af-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f63af-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f63af-129">CommonParameters</span></span>
<span data-ttu-id="f63af-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f63af-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f63af-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f63af-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f63af-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f63af-132">INPUTS</span></span>

### <span data-ttu-id="f63af-133">System. Management. Automation. Секуритяккаунтсманажер. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="f63af-133">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="f63af-134">Этот командлет можно передать по конвейеру локальному пользователю, строке или идентификатору безопасности.</span><span class="sxs-lookup"><span data-stu-id="f63af-134">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="f63af-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f63af-135">OUTPUTS</span></span>

### <span data-ttu-id="f63af-136">Нет</span><span class="sxs-lookup"><span data-stu-id="f63af-136">None</span></span>
<span data-ttu-id="f63af-137">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f63af-137">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f63af-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f63af-138">NOTES</span></span>

* <span data-ttu-id="f63af-139">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="f63af-139">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="f63af-140">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="f63af-140">The possible sources are as follows:</span></span>

- <span data-ttu-id="f63af-141">Локальная</span><span class="sxs-lookup"><span data-stu-id="f63af-141">Local</span></span>
- <span data-ttu-id="f63af-142">Active Directory</span><span class="sxs-lookup"><span data-stu-id="f63af-142">Active Directory</span></span>
- <span data-ttu-id="f63af-143">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f63af-143">Azure Active Directory group</span></span>
- <span data-ttu-id="f63af-144">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f63af-144">Microsoft Account</span></span>

<span data-ttu-id="f63af-145">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="f63af-145">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="f63af-146">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="f63af-146">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="f63af-147">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f63af-147">RELATED LINKS</span></span>

[<span data-ttu-id="f63af-148">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-148">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="f63af-149">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-149">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="f63af-150">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-150">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="f63af-151">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-151">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="f63af-152">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-152">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="f63af-153">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="f63af-153">Set-LocalUser</span></span>](Set-LocalUser.md)
