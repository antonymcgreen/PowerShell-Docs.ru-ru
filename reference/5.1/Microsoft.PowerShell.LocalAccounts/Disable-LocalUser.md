---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/disable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-LocalUser
ms.openlocfilehash: a62242251da00688d3299c60e4cdae7aae6f581a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226626"
---
# <span data-ttu-id="4d8c8-103">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-103">Disable-LocalUser</span></span>

## <span data-ttu-id="4d8c8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4d8c8-104">SYNOPSIS</span></span>
<span data-ttu-id="4d8c8-105">Отключает локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-105">Disables a local user account.</span></span>

## <span data-ttu-id="4d8c8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d8c8-106">SYNTAX</span></span>

### <span data-ttu-id="4d8c8-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="4d8c8-107">InputObject</span></span>

```
Disable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d8c8-108">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="4d8c8-108">Default</span></span>

```
Disable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d8c8-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="4d8c8-109">SecurityIdentifier</span></span>

```
Disable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4d8c8-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4d8c8-110">DESCRIPTION</span></span>
<span data-ttu-id="4d8c8-111">Командлет **Disable-LocalUser** отключает локальные учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-111">The **Disable-LocalUser** cmdlet disables local user accounts.</span></span>
<span data-ttu-id="4d8c8-112">Если учетная запись пользователя отключена, пользователь не может войти в систему.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="4d8c8-113">Если учетная запись пользователя включена, пользователь может войти в систему.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8c8-114">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="4d8c8-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="4d8c8-115">EXAMPLES</span></span>

### <span data-ttu-id="4d8c8-116">Пример 1. Отключение учетной записи путем указания имени</span><span class="sxs-lookup"><span data-stu-id="4d8c8-116">Example 1: Disable an account by specifying a name</span></span>

```
PS C:\> Disable-LocalUser -Name "Admin02"
```

<span data-ttu-id="4d8c8-117">Эта команда отключает учетную запись пользователя с именем Admin02.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-117">This command disables the user account named Admin02.</span></span>

### <span data-ttu-id="4d8c8-118">Пример 2. Отключение учетной записи с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="4d8c8-118">Example 2: Disable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser Guest | Disable-LocalUser
```

<span data-ttu-id="4d8c8-119">Эта команда получает встроенную учетную запись гостя с помощью командлета **Get-LocalUser** , а затем передает ее в текущий командлет с помощью конвейерного оператора.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-119">This command gets the built-in Guest account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="4d8c8-120">Этот командлет отключает эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-120">That cmdlet disables that account.</span></span>

## <span data-ttu-id="4d8c8-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d8c8-121">PARAMETERS</span></span>

### <span data-ttu-id="4d8c8-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4d8c8-122">-InputObject</span></span>
<span data-ttu-id="4d8c8-123">Указывает массив учетных записей пользователей, которые отключает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-123">Specifies an array of user accounts that this cmdlet disables.</span></span>
<span data-ttu-id="4d8c8-124">Чтобы получить учетную запись пользователя, используйте командлет Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="4d8c8-125">-Name</span><span class="sxs-lookup"><span data-stu-id="4d8c8-125">-Name</span></span>
<span data-ttu-id="4d8c8-126">Указывает массив имен учетных записей пользователей, которые отключает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-126">Specifies an array of names of the user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="4d8c8-127">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="4d8c8-127">-SID</span></span>
<span data-ttu-id="4d8c8-128">Указывает массив учетных записей пользователей, которые отключает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-128">Specifies an array of user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="4d8c8-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4d8c8-129">-Confirm</span></span>
<span data-ttu-id="4d8c8-130">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4d8c8-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4d8c8-131">-WhatIf</span></span>
<span data-ttu-id="4d8c8-132">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4d8c8-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4d8c8-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4d8c8-134">CommonParameters</span></span>
<span data-ttu-id="4d8c8-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4d8c8-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4d8c8-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4d8c8-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4d8c8-137">INPUTS</span></span>

### <span data-ttu-id="4d8c8-138">System. Management. Automation. Секуритяккаунтсманажер. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="4d8c8-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="4d8c8-139">Этот командлет можно передать по конвейеру локальному пользователю, строке или идентификатору безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="4d8c8-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4d8c8-140">OUTPUTS</span></span>

### <span data-ttu-id="4d8c8-141">Нет</span><span class="sxs-lookup"><span data-stu-id="4d8c8-141">None</span></span>
<span data-ttu-id="4d8c8-142">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4d8c8-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4d8c8-143">NOTES</span></span>

* <span data-ttu-id="4d8c8-144">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="4d8c8-145">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="4d8c8-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="4d8c8-146">Локальная</span><span class="sxs-lookup"><span data-stu-id="4d8c8-146">Local</span></span>
- <span data-ttu-id="4d8c8-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4d8c8-147">Active Directory</span></span>
- <span data-ttu-id="4d8c8-148">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4d8c8-148">Azure Active Directory group</span></span>
- <span data-ttu-id="4d8c8-149">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4d8c8-149">Microsoft Account</span></span>

<span data-ttu-id="4d8c8-150">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="4d8c8-151">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="4d8c8-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="4d8c8-152">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4d8c8-152">RELATED LINKS</span></span>

[<span data-ttu-id="4d8c8-153">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-153">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="4d8c8-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="4d8c8-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="4d8c8-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="4d8c8-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="4d8c8-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4d8c8-158">Set-LocalUser</span></span>](Set-LocalUser.md)
