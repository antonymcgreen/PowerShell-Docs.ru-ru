---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalUser
ms.openlocfilehash: a6352611b757dae828a2efef07f9ce65abaa5e2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228473"
---
# <span data-ttu-id="61186-103">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-103">Set-LocalUser</span></span>

## <span data-ttu-id="61186-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="61186-104">SYNOPSIS</span></span>
<span data-ttu-id="61186-105">Изменяет локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-105">Modifies a local user account.</span></span>

## <span data-ttu-id="61186-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61186-106">SYNTAX</span></span>

### <span data-ttu-id="61186-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="61186-107">Name (Default)</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Name] <String> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="61186-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="61186-108">InputObject</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-InputObject] <LocalUser> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="61186-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="61186-109">SecurityIdentifier</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Password <SecureString>] [-PasswordNeverExpires <Boolean>] [-SID] <SecurityIdentifier>
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="61186-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61186-110">DESCRIPTION</span></span>
<span data-ttu-id="61186-111">Командлет **Set-LocalUser** изменяет локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-111">The **Set-LocalUser** cmdlet modifies a local user account.</span></span>
<span data-ttu-id="61186-112">Этот командлет может сбросить пароль учетной записи локального пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-112">This cmdlet can reset the password of a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="61186-113">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="61186-113">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="61186-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="61186-114">EXAMPLES</span></span>

### <span data-ttu-id="61186-115">Пример 1. изменение описания учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="61186-115">Example 1: Change a description of a user account</span></span>

```
PS C:\> Set-LocalUser -Name "Admin07" -Description "Description of this account."
```

<span data-ttu-id="61186-116">Эта команда изменяет описание учетной записи пользователя с именем Admin07.</span><span class="sxs-lookup"><span data-stu-id="61186-116">This command changes the description of a user account named Admin07.</span></span>

### <span data-ttu-id="61186-117">Пример 2. изменение пароля для учетной записи</span><span class="sxs-lookup"><span data-stu-id="61186-117">Example 2: Change the password on an account</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> $UserAccount = Get-LocalUser -Name "User02"
PS C:\> $UserAccount | Set-LocalUser -Password $Password
```

<span data-ttu-id="61186-118">Первая команда запрашивает пароль с помощью командлета Read-Host.</span><span class="sxs-lookup"><span data-stu-id="61186-118">The first command prompts you for a password by using the Read-Host cmdlet.</span></span>
<span data-ttu-id="61186-119">Команда сохраняет пароль в виде защищенной строки в переменной $Password.</span><span class="sxs-lookup"><span data-stu-id="61186-119">The command stores the password as a secure string in the $Password variable.</span></span>

<span data-ttu-id="61186-120">Вторая команда получает учетную запись пользователя с именем User02 с помощью **Get-LocalUser** .</span><span class="sxs-lookup"><span data-stu-id="61186-120">The second command gets a user account named User02 by using **Get-LocalUser** .</span></span>
<span data-ttu-id="61186-121">Команда сохраняет учетную запись в переменной $UserAccount.</span><span class="sxs-lookup"><span data-stu-id="61186-121">The command stores the account in the $UserAccount variable.</span></span>

<span data-ttu-id="61186-122">Третья команда задает новый пароль для учетной записи пользователя, хранящейся в $UserAccount.</span><span class="sxs-lookup"><span data-stu-id="61186-122">The third command sets the new password on the user account stored in $UserAccount.</span></span>

## <span data-ttu-id="61186-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61186-123">PARAMETERS</span></span>

### <span data-ttu-id="61186-124">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="61186-124">-AccountExpires</span></span>
<span data-ttu-id="61186-125">Указывает, когда истекает срок действия учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-125">Specifies when the user account expires.</span></span>
<span data-ttu-id="61186-126">Чтобы получить объект **DateTime** , используйте командлет Get-Date.</span><span class="sxs-lookup"><span data-stu-id="61186-126">To obtain a **DateTime** object, use the Get-Date cmdlet.</span></span>

<span data-ttu-id="61186-127">Если срок действия учетной записи не должен истечь, укажите параметр *аккаунтневерекспирес* .</span><span class="sxs-lookup"><span data-stu-id="61186-127">If you do not want the account to expire, specify the *AccountNeverExpires* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-128">-Аккаунтневерекспирес</span><span class="sxs-lookup"><span data-stu-id="61186-128">-AccountNeverExpires</span></span>
<span data-ttu-id="61186-129">Указывает, что срок действия учетной записи не истекает.</span><span class="sxs-lookup"><span data-stu-id="61186-129">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-130">-Description</span><span class="sxs-lookup"><span data-stu-id="61186-130">-Description</span></span>
<span data-ttu-id="61186-131">Указывает комментарий для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-131">Specifies a comment for the user account.</span></span>
<span data-ttu-id="61186-132">Максимальная длина — 48 символов.</span><span class="sxs-lookup"><span data-stu-id="61186-132">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-133">-FullName</span><span class="sxs-lookup"><span data-stu-id="61186-133">-FullName</span></span>
<span data-ttu-id="61186-134">Указывает полное имя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-134">Specifies the full name for the user account.</span></span>
<span data-ttu-id="61186-135">Полное имя отличается от имени пользователя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-135">The full name differs from the user name of the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="61186-136">-InputObject</span></span>
<span data-ttu-id="61186-137">Указывает учетную запись пользователя, которую изменяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="61186-137">Specifies the user account that this cmdlet changes.</span></span>
<span data-ttu-id="61186-138">Чтобы получить учетную запись пользователя, используйте командлет Get-LocalUser.</span><span class="sxs-lookup"><span data-stu-id="61186-138">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="61186-139">-Name</span><span class="sxs-lookup"><span data-stu-id="61186-139">-Name</span></span>
<span data-ttu-id="61186-140">Указывает имя учетной записи пользователя, которую изменяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="61186-140">Specifies the name of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="61186-141">-Password</span><span class="sxs-lookup"><span data-stu-id="61186-141">-Password</span></span>
<span data-ttu-id="61186-142">Указывает пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-142">Specifies a password for the user account.</span></span>
<span data-ttu-id="61186-143">Если учетная запись пользователя подключена к учетная запись Майкрософт, не устанавливайте пароль.</span><span class="sxs-lookup"><span data-stu-id="61186-143">If the user account is connected to a Microsoft account, do not set a password.</span></span>

<span data-ttu-id="61186-144">Для `Read-Host -GetCredential` создания объекта **SecureString** для пароля можно использовать, Get-Credential или ConvertTo-SecureString.</span><span class="sxs-lookup"><span data-stu-id="61186-144">You can use `Read-Host -GetCredential`, Get-Credential, or ConvertTo-SecureString to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="61186-145">Если вы не пропускаете параметры *Password* *и Password* , **Set-LocalUser** запрашивает пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-145">If you omit the *Password* and *NoPassword* parameters, **Set-LocalUser** prompts you for the user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-146">-Пассвордневерекспирес</span><span class="sxs-lookup"><span data-stu-id="61186-146">-PasswordNeverExpires</span></span>
<span data-ttu-id="61186-147">Указывает, истечет ли срок действия пароля.</span><span class="sxs-lookup"><span data-stu-id="61186-147">Indicates whether the password expires.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-148">ИД безопасности</span><span class="sxs-lookup"><span data-stu-id="61186-148">-SID</span></span>
<span data-ttu-id="61186-149">Указывает идентификатор безопасности (SID) учетной записи пользователя, которую изменяет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="61186-149">Specifies the security ID (SID) of the user account that this cmdlet changes.</span></span>

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

### <span data-ttu-id="61186-150">-Усермайчанжепассворд</span><span class="sxs-lookup"><span data-stu-id="61186-150">-UserMayChangePassword</span></span>
<span data-ttu-id="61186-151">Указывает, что пользователь может изменить пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61186-151">Indicates that the user can change the password on the user account.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61186-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="61186-152">-Confirm</span></span>
<span data-ttu-id="61186-153">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="61186-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="61186-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="61186-154">-WhatIf</span></span>
<span data-ttu-id="61186-155">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="61186-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="61186-156">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="61186-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="61186-157">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="61186-157">CommonParameters</span></span>
<span data-ttu-id="61186-158">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61186-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61186-159">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="61186-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="61186-160">Входные данные</span><span class="sxs-lookup"><span data-stu-id="61186-160">INPUTS</span></span>

### <span data-ttu-id="61186-161">System. Management. Automation. Секуритяккаунтсманажер. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="61186-161">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="61186-162">Этот командлет можно передать по конвейеру локальному пользователю, строке или идентификатору безопасности.</span><span class="sxs-lookup"><span data-stu-id="61186-162">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="61186-163">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="61186-163">OUTPUTS</span></span>

### <span data-ttu-id="61186-164">Нет</span><span class="sxs-lookup"><span data-stu-id="61186-164">None</span></span>
<span data-ttu-id="61186-165">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="61186-165">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="61186-166">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="61186-166">NOTES</span></span>

* <span data-ttu-id="61186-167">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="61186-167">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="61186-168">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="61186-168">The possible sources are as follows:</span></span>

- <span data-ttu-id="61186-169">Локальная</span><span class="sxs-lookup"><span data-stu-id="61186-169">Local</span></span>
- <span data-ttu-id="61186-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="61186-170">Active Directory</span></span>
- <span data-ttu-id="61186-171">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="61186-171">Azure Active Directory group</span></span>
- <span data-ttu-id="61186-172">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="61186-172">Microsoft Account</span></span>

<span data-ttu-id="61186-173">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="61186-173">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="61186-174">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="61186-174">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="61186-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="61186-175">RELATED LINKS</span></span>

[<span data-ttu-id="61186-176">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-176">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="61186-177">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-177">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="61186-178">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-178">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="61186-179">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-179">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="61186-180">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-180">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="61186-181">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="61186-181">Rename-LocalUser</span></span>](Rename-LocalUser.md)
