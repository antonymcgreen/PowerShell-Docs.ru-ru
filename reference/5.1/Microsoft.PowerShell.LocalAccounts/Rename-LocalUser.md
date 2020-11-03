---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalUser
ms.openlocfilehash: fc5740e52e08ad2146981799a4e1659cd420b321
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228481"
---
# <span data-ttu-id="9882e-103">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-103">Rename-LocalUser</span></span>

## <span data-ttu-id="9882e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9882e-104">SYNOPSIS</span></span>
<span data-ttu-id="9882e-105">Переименовывает локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="9882e-105">Renames a local user account.</span></span>

## <span data-ttu-id="9882e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9882e-106">SYNTAX</span></span>

### <span data-ttu-id="9882e-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="9882e-107">InputObject</span></span>

```
Rename-LocalUser [-InputObject] <LocalUser> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9882e-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="9882e-108">Default</span></span>

```
Rename-LocalUser [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9882e-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="9882e-109">SecurityIdentifier</span></span>

```
Rename-LocalUser [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9882e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9882e-110">DESCRIPTION</span></span>
<span data-ttu-id="9882e-111">Командлет **Rename-LocalUser** переименовывает локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="9882e-111">The **Rename-LocalUser** cmdlet renames a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="9882e-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="9882e-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="9882e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="9882e-113">EXAMPLES</span></span>

### <span data-ttu-id="9882e-114">Пример 1. Переименование учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="9882e-114">Example 1: Rename a user account</span></span>

```
PS C:\> Rename-LocalUser -Name "Admin02" -NewName "AdminContoso02"
```

<span data-ttu-id="9882e-115">Эта команда переименовывает учетную запись пользователя с именем Admin02.</span><span class="sxs-lookup"><span data-stu-id="9882e-115">This command renames the user account named Admin02.</span></span>

## <span data-ttu-id="9882e-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9882e-116">PARAMETERS</span></span>

### <span data-ttu-id="9882e-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9882e-117">-InputObject</span></span>
<span data-ttu-id="9882e-118">Указывает учетную запись пользователя, которая переименовывается этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9882e-118">Specifies the user account that this cmdlet renames.</span></span>
<span data-ttu-id="9882e-119">Чтобы получить учетную запись пользователя, используйте командлет Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="9882e-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9882e-120">-Name</span><span class="sxs-lookup"><span data-stu-id="9882e-120">-Name</span></span>
<span data-ttu-id="9882e-121">Указывает имя учетной записи пользователя, которая переименовывается этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9882e-121">Specifies the name of the user account that this cmdlet renames.</span></span>

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

### <span data-ttu-id="9882e-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="9882e-122">-NewName</span></span>
<span data-ttu-id="9882e-123">Указывает новое имя для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="9882e-123">Specifies a new name for the user account.</span></span>

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

### <span data-ttu-id="9882e-124">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="9882e-124">-SID</span></span>
<span data-ttu-id="9882e-125">Указывает идентификатор безопасности (SID) учетных записей пользователей, которые переименовывает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="9882e-125">Specifies the security ID (SID) of a user accounts that this cmdlet renames.</span></span>

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

### <span data-ttu-id="9882e-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9882e-126">-Confirm</span></span>
<span data-ttu-id="9882e-127">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9882e-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9882e-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9882e-128">-WhatIf</span></span>
<span data-ttu-id="9882e-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9882e-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9882e-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9882e-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9882e-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9882e-131">CommonParameters</span></span>
<span data-ttu-id="9882e-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9882e-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9882e-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9882e-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9882e-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9882e-134">INPUTS</span></span>

### <span data-ttu-id="9882e-135">System. Management. Automation. Секуритяккаунтсманажер. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="9882e-135">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="9882e-136">Этот командлет можно передать по конвейеру локальному пользователю, строке или идентификатору безопасности.</span><span class="sxs-lookup"><span data-stu-id="9882e-136">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="9882e-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9882e-137">OUTPUTS</span></span>

### <span data-ttu-id="9882e-138">Нет</span><span class="sxs-lookup"><span data-stu-id="9882e-138">None</span></span>
<span data-ttu-id="9882e-139">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9882e-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9882e-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9882e-140">NOTES</span></span>

* <span data-ttu-id="9882e-141">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="9882e-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="9882e-142">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="9882e-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="9882e-143">Локальная</span><span class="sxs-lookup"><span data-stu-id="9882e-143">Local</span></span>
- <span data-ttu-id="9882e-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="9882e-144">Active Directory</span></span>
- <span data-ttu-id="9882e-145">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9882e-145">Azure Active Directory group</span></span>
- <span data-ttu-id="9882e-146">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9882e-146">Microsoft Account</span></span>

<span data-ttu-id="9882e-147">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="9882e-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="9882e-148">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="9882e-148">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="9882e-149">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9882e-149">RELATED LINKS</span></span>

[<span data-ttu-id="9882e-150">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-150">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="9882e-151">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-151">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="9882e-152">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-152">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="9882e-153">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-153">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="9882e-154">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-154">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="9882e-155">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="9882e-155">Set-LocalUser</span></span>](Set-LocalUser.md)
