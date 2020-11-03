---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228001"
---
# <span data-ttu-id="c1d85-103">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-103">New-LocalUser</span></span>

## <span data-ttu-id="c1d85-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c1d85-104">SYNOPSIS</span></span>

<span data-ttu-id="c1d85-105">Создает локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-105">Creates a local user account.</span></span>

## <span data-ttu-id="c1d85-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1d85-106">SYNTAX</span></span>

### <span data-ttu-id="c1d85-107">Пароль (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c1d85-107">Password (Default)</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c1d85-108">Не заменять пароль</span><span class="sxs-lookup"><span data-stu-id="c1d85-108">NoPassword</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="c1d85-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1d85-109">DESCRIPTION</span></span>

<span data-ttu-id="c1d85-110">`New-LocalUser`Командлет создает локальную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-110">The `New-LocalUser` cmdlet creates a local user account.</span></span> <span data-ttu-id="c1d85-111">Этот командлет создает локальную учетную запись пользователя или локальную учетную запись пользователя, подключенную к учетная запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c1d85-111">This cmdlet creates a local user account or a local user account that is connected to a Microsoft account.</span></span>

> [!NOTE]
> <span data-ttu-id="c1d85-112">Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="c1d85-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="c1d85-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1d85-113">EXAMPLES</span></span>

### <span data-ttu-id="c1d85-114">Пример 1. Создание учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="c1d85-114">Example 1: Create a user account</span></span>

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

<span data-ttu-id="c1d85-115">Эта команда создает локальную учетную запись пользователя и не указывает параметры **AccountExpires** или **Password** .</span><span class="sxs-lookup"><span data-stu-id="c1d85-115">This command creates a local user account and does not specify the **AccountExpires** or **Password** parameters.</span></span> <span data-ttu-id="c1d85-116">Поэтому срок действия учетной записи не истекает или пароль по умолчанию не используется.</span><span class="sxs-lookup"><span data-stu-id="c1d85-116">Therefore, the account doesn't expire or have a password by default.</span></span>

### <span data-ttu-id="c1d85-117">Пример 2. Создание учетной записи пользователя с паролем</span><span class="sxs-lookup"><span data-stu-id="c1d85-117">Example 2: Create a user account that has a password</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

<span data-ttu-id="c1d85-118">Первая команда запрашивает пароль с помощью `Read-Host` командлета.</span><span class="sxs-lookup"><span data-stu-id="c1d85-118">The first command prompts you for a password by using the `Read-Host` cmdlet.</span></span> <span data-ttu-id="c1d85-119">Команда сохраняет пароль в виде защищенной строки в `$Password` переменной.</span><span class="sxs-lookup"><span data-stu-id="c1d85-119">The command stores the password as a secure string in the `$Password` variable.</span></span>

<span data-ttu-id="c1d85-120">Вторая команда создает локальную учетную запись пользователя, используя пароль, хранящийся в `$Password` .</span><span class="sxs-lookup"><span data-stu-id="c1d85-120">The second command creates a local user account by using the password stored in `$Password`.</span></span> <span data-ttu-id="c1d85-121">Команда задает имя пользователя, полное имя и описание учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-121">The command specifies a user name, full name, and description for the user account.</span></span>

## <span data-ttu-id="c1d85-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1d85-122">PARAMETERS</span></span>

### <span data-ttu-id="c1d85-123">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="c1d85-123">-AccountExpires</span></span>

<span data-ttu-id="c1d85-124">Указывает, когда истекает срок действия учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-124">Specifies when the user account expires.</span></span> <span data-ttu-id="c1d85-125">Чтобы получить объект **DateTime** , используйте `Get-Date` командлет.</span><span class="sxs-lookup"><span data-stu-id="c1d85-125">To obtain a **DateTime** object, use the `Get-Date` cmdlet.</span></span>
<span data-ttu-id="c1d85-126">Если этот параметр не указан, срок действия учетной записи не истечет.</span><span class="sxs-lookup"><span data-stu-id="c1d85-126">If you do not specify this parameter, the account does not expire.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-127">-Аккаунтневерекспирес</span><span class="sxs-lookup"><span data-stu-id="c1d85-127">-AccountNeverExpires</span></span>

<span data-ttu-id="c1d85-128">Указывает, что срок действия учетной записи не истекает.</span><span class="sxs-lookup"><span data-stu-id="c1d85-128">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-129">-Description</span><span class="sxs-lookup"><span data-stu-id="c1d85-129">-Description</span></span>

<span data-ttu-id="c1d85-130">Указывает комментарий для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-130">Specifies a comment for the user account.</span></span>
<span data-ttu-id="c1d85-131">Максимальная длина — 48 символов.</span><span class="sxs-lookup"><span data-stu-id="c1d85-131">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-132">— Отключено</span><span class="sxs-lookup"><span data-stu-id="c1d85-132">-Disabled</span></span>

<span data-ttu-id="c1d85-133">Указывает, что этот командлет создает учетную запись пользователя как отключенную.</span><span class="sxs-lookup"><span data-stu-id="c1d85-133">Indicates that this cmdlet creates the user account as disabled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-134">-FullName</span><span class="sxs-lookup"><span data-stu-id="c1d85-134">-FullName</span></span>

<span data-ttu-id="c1d85-135">Указывает полное имя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-135">Specifies the full name for the user account.</span></span> <span data-ttu-id="c1d85-136">Полное имя отличается от имени пользователя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-136">The full name differs from the user name of the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-137">-Name</span><span class="sxs-lookup"><span data-stu-id="c1d85-137">-Name</span></span>

<span data-ttu-id="c1d85-138">Указывает имя пользователя для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-138">Specifies the user name for the user account.</span></span>

<span data-ttu-id="c1d85-139">Если вы создаете локальную учетную запись пользователя для локальной системы, имя пользователя может содержать до 20 символов верхнего регистра или строчных символов.</span><span class="sxs-lookup"><span data-stu-id="c1d85-139">If you create a local user account for the local system, the user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="c1d85-140">Имя пользователя не может содержать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="c1d85-140">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="c1d85-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="c1d85-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

<span data-ttu-id="c1d85-142">Имя пользователя не может состоять только из точек `.` или пробелов.</span><span class="sxs-lookup"><span data-stu-id="c1d85-142">A user name cannot consist only of periods `.` or spaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-143">-Непарольный</span><span class="sxs-lookup"><span data-stu-id="c1d85-143">-NoPassword</span></span>

<span data-ttu-id="c1d85-144">Указывает, что у учетной записи пользователя нет пароля.</span><span class="sxs-lookup"><span data-stu-id="c1d85-144">Indicates that the user account does not have a password.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-145">-Password</span><span class="sxs-lookup"><span data-stu-id="c1d85-145">-Password</span></span>

<span data-ttu-id="c1d85-146">Указывает пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-146">Specifies a password for the user account.</span></span> <span data-ttu-id="c1d85-147">Для `Read-Host -GetCredential` `Get-Credential` `ConvertTo-SecureString` создания объекта **SecureString** для пароля можно использовать, или.</span><span class="sxs-lookup"><span data-stu-id="c1d85-147">You can use `Read-Host -GetCredential`, `Get-Credential`, or `ConvertTo-SecureString` to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="c1d85-148">Если вы не пропускаете параметры **Password** **и Password,** `New-LocalUser` запрашивает пароль нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-148">If you omit the **Password** and **NoPassword** parameters, `New-LocalUser` prompts you for the new user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-149">-Пассвордневерекспирес</span><span class="sxs-lookup"><span data-stu-id="c1d85-149">-PasswordNeverExpires</span></span>

<span data-ttu-id="c1d85-150">Указывает, истечет ли срок действия пароля.</span><span class="sxs-lookup"><span data-stu-id="c1d85-150">Indicates whether the password expires.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-151">-Усермайнотчанжепассворд</span><span class="sxs-lookup"><span data-stu-id="c1d85-151">-UserMayNotChangePassword</span></span>

<span data-ttu-id="c1d85-152">Указывает, что пользователь не может изменить пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-152">Indicates that the user cannot change the password on the user account.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c1d85-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c1d85-153">-Confirm</span></span>

<span data-ttu-id="c1d85-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c1d85-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c1d85-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c1d85-155">-WhatIf</span></span>

<span data-ttu-id="c1d85-156">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c1d85-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c1d85-157">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c1d85-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c1d85-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c1d85-158">CommonParameters</span></span>

<span data-ttu-id="c1d85-159">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="c1d85-159">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c1d85-160">См. сведения в разделе [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c1d85-160">For more information, see [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c1d85-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c1d85-161">INPUTS</span></span>

### <span data-ttu-id="c1d85-162">System. String, System. DateTime, System. Boolean, System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="c1d85-162">System.String, System.DateTime, System.Boolean, System.Security.SecureString</span></span>

<span data-ttu-id="c1d85-163">В этот командлет можно передать по конвейеру строку, объект **DateTime** , логическое значение или безопасную строку.</span><span class="sxs-lookup"><span data-stu-id="c1d85-163">You can pipe a string, a **DateTime** object, a boolean value, or a secure string to this cmdlet.</span></span>

## <span data-ttu-id="c1d85-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c1d85-164">OUTPUTS</span></span>

### <span data-ttu-id="c1d85-165">System. Management. Automation. Секуритяккаунтсманажер. LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-165">System.Management.Automation.SecurityAccountsManager.LocalUser</span></span>

<span data-ttu-id="c1d85-166">Этот командлет возвращает объект **LocalUser** .</span><span class="sxs-lookup"><span data-stu-id="c1d85-166">This cmdlet returns a **LocalUser** object.</span></span>
<span data-ttu-id="c1d85-167">Этот объект предоставляет сведения об учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1d85-167">This object provides information about the user account.</span></span>

## <span data-ttu-id="c1d85-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c1d85-168">NOTES</span></span>

- <span data-ttu-id="c1d85-169">Имя пользователя не может совпадать с любым другим именем пользователя или группы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c1d85-169">A user name cannot be identical to any other user name or group name on the computer.</span></span> <span data-ttu-id="c1d85-170">Имя пользователя не может состоять только из точек `.` или пробелов.</span><span class="sxs-lookup"><span data-stu-id="c1d85-170">A user name cannot consist only of periods `.` or spaces.</span></span> <span data-ttu-id="c1d85-171">Имя пользователя может содержать до 20 символов верхнего регистра или строчных символов.</span><span class="sxs-lookup"><span data-stu-id="c1d85-171">A user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="c1d85-172">Имя пользователя не может содержать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="c1d85-172">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="c1d85-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="c1d85-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

- <span data-ttu-id="c1d85-174">Пароль может содержать до 127 символов.</span><span class="sxs-lookup"><span data-stu-id="c1d85-174">A password can contain up to 127 characters.</span></span>
- <span data-ttu-id="c1d85-175">Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта.</span><span class="sxs-lookup"><span data-stu-id="c1d85-175">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="c1d85-176">Возможны следующие источники:</span><span class="sxs-lookup"><span data-stu-id="c1d85-176">The possible sources are as follows:</span></span>

  - <span data-ttu-id="c1d85-177">Локальная</span><span class="sxs-lookup"><span data-stu-id="c1d85-177">Local</span></span>
  - <span data-ttu-id="c1d85-178">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c1d85-178">Active Directory</span></span>
  - <span data-ttu-id="c1d85-179">Группа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c1d85-179">Azure Active Directory group</span></span>
  - <span data-ttu-id="c1d85-180">Учетная запись Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c1d85-180">Microsoft Account</span></span>

> [!NOTE]
> <span data-ttu-id="c1d85-181">**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="c1d85-181">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="c1d85-182">Для более ранних версий свойство остается пустым.</span><span class="sxs-lookup"><span data-stu-id="c1d85-182">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="c1d85-183">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c1d85-183">RELATED LINKS</span></span>

[<span data-ttu-id="c1d85-184">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-184">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="c1d85-185">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-185">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="c1d85-186">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-186">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="c1d85-187">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-187">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="c1d85-188">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-188">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="c1d85-189">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c1d85-189">Set-LocalUser</span></span>](Set-LocalUser.md)
