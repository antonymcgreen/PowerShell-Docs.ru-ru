---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 6f98c95e6c0144f76393e9d28454833097894512
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227525"
---
# <span data-ttu-id="62fe6-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="62fe6-103">Send-MailMessage</span></span>

## <span data-ttu-id="62fe6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="62fe6-104">SYNOPSIS</span></span>
<span data-ttu-id="62fe6-105">Отправляет сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-105">Sends an email message.</span></span>

## <span data-ttu-id="62fe6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="62fe6-106">SYNTAX</span></span>

### <span data-ttu-id="62fe6-107">Все</span><span class="sxs-lookup"><span data-stu-id="62fe6-107">All</span></span>

```
Send-MailMessage [-To] <string[]> [-Subject] <string> [[-Body] <string>] [[-SmtpServer] <string>]
 -From <string> [-Attachments <string[]>] [-Bcc <string[]>] [-BodyAsHtml] [-Encoding <Encoding>]
 [-Cc <string[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 [-Priority <MailPriority>] [-Credential <pscredential>] [-UseSsl] [-Port <int>]
 [<CommonParameters>]
```

## <span data-ttu-id="62fe6-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="62fe6-108">DESCRIPTION</span></span>

<span data-ttu-id="62fe6-109">`Send-MailMessage`Командлет отправляет сообщение электронной почты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62fe6-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="62fe6-110">Необходимо указать SMTP-сервер или `Send-MailMessage` выполнить команду с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="62fe6-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="62fe6-111">Используйте параметр **SMTP** или задайте `$PSEmailServer` для переменной допустимый SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="62fe6-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="62fe6-112">Значение, присваиваемое, `$PSEmailServer` является параметром SMTP по умолчанию для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62fe6-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="62fe6-113">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="62fe6-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="62fe6-114">`Send-MailMessage`Командлет устарел.</span><span class="sxs-lookup"><span data-stu-id="62fe6-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="62fe6-115">Этот командлет не гарантирует безопасное подключение к SMTP-серверам.</span><span class="sxs-lookup"><span data-stu-id="62fe6-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="62fe6-116">Хотя в PowerShell нет доступной немедленной замены, мы рекомендуем не использовать `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="62fe6-117">Дополнительные сведения см. в разделе [Примечание о совместимости платформ DE0005](https://aka.ms/SendMailMessage).</span><span class="sxs-lookup"><span data-stu-id="62fe6-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="62fe6-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="62fe6-118">EXAMPLES</span></span>

### <span data-ttu-id="62fe6-119">Пример 1. Отправка сообщения электронной почты от одного пользователя другому человеку</span><span class="sxs-lookup"><span data-stu-id="62fe6-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="62fe6-120">В этом примере посылается сообщение электронной почты от одного лица другому человеку.</span><span class="sxs-lookup"><span data-stu-id="62fe6-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="62fe6-121">Параметры **from** , **to** и **subject** обязательны для `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="62fe6-122">В этом примере используется переменная по умолчанию `$PSEmailServer` для SMTP-сервера, поэтому параметр **SMTP** не требуется.</span><span class="sxs-lookup"><span data-stu-id="62fe6-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="62fe6-123">`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="62fe6-124">Параметр **to** указывает получателя сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="62fe6-125">Параметр **subject** использует **тестовую почту** Text String в качестве сообщения, так как необязательный параметр **Body** не включен.</span><span class="sxs-lookup"><span data-stu-id="62fe6-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="62fe6-126">Пример 2. Отправка вложения</span><span class="sxs-lookup"><span data-stu-id="62fe6-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="62fe6-127">В этом примере отправляется сообщение электронной почты с вложением.</span><span class="sxs-lookup"><span data-stu-id="62fe6-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="62fe6-128">`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="62fe6-129">Параметр **to** указывает получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="62fe6-130">Параметр **subject** описывает содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="62fe6-131">Параметр **Body** — это содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="62fe6-132">Параметр **вложения** указывает файл в текущем каталоге, присоединенном к сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="62fe6-133">Параметр **Priority** задает для сообщения **высокий** приоритет.</span><span class="sxs-lookup"><span data-stu-id="62fe6-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="62fe6-134">Параметр **-деливеринотификатионоптион** задает два значения: **onsuccesss** и **onSuccess** .</span><span class="sxs-lookup"><span data-stu-id="62fe6-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure** .</span></span> <span data-ttu-id="62fe6-135">Отправитель получит уведомления по электронной почте для подтверждения успешной или неуспешной доставки сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="62fe6-136">Параметр **SMTP** задает для SMTP-сервера значение **SMTP.fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="62fe6-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com** .</span></span>

### <span data-ttu-id="62fe6-137">Пример 3. Отправка сообщения электронной почты в список рассылки</span><span class="sxs-lookup"><span data-stu-id="62fe6-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="62fe6-138">В этом примере сообщение электронной почты отправляется в список рассылки.</span><span class="sxs-lookup"><span data-stu-id="62fe6-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="62fe6-139">`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="62fe6-140">Параметр **to** указывает получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="62fe6-141">Параметр **CC** отправляет копию сообщения указанному получателю.</span><span class="sxs-lookup"><span data-stu-id="62fe6-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="62fe6-142">Параметр **BCC** отправляет скрытую копию сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="62fe6-143">Скрытая копия — это адрес электронной почты, который скрыт от других получателей.</span><span class="sxs-lookup"><span data-stu-id="62fe6-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="62fe6-144">Параметр **subject** является сообщением, так как необязательный параметр **тела** не включен.</span><span class="sxs-lookup"><span data-stu-id="62fe6-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="62fe6-145">Параметр **Credential** указывает учетные данные администратора домена, используемые для отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="62fe6-146">Параметр **UseSsl** указывает, что протокол SSL создает безопасное соединение.</span><span class="sxs-lookup"><span data-stu-id="62fe6-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="62fe6-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="62fe6-147">PARAMETERS</span></span>

### <span data-ttu-id="62fe6-148">— Вложения</span><span class="sxs-lookup"><span data-stu-id="62fe6-148">-Attachments</span></span>

<span data-ttu-id="62fe6-149">Указывает путь и имена файлов, которые будут присоединены к сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="62fe6-150">Можно использовать этот параметр или передать пути и имена файлов в `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-151">-СК</span><span class="sxs-lookup"><span data-stu-id="62fe6-151">-Bcc</span></span>

<span data-ttu-id="62fe6-152">Указывает адреса электронной почты, получающие копию почты, но не указанные в качестве получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="62fe6-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="62fe6-153">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-154">-Body</span><span class="sxs-lookup"><span data-stu-id="62fe6-154">-Body</span></span>

<span data-ttu-id="62fe6-155">Указывает содержимое сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-155">Specifies the content of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-156">-Бодяштмл</span><span class="sxs-lookup"><span data-stu-id="62fe6-156">-BodyAsHtml</span></span>

<span data-ttu-id="62fe6-157">Указывает, что значение параметра **Body** содержит HTML.</span><span class="sxs-lookup"><span data-stu-id="62fe6-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-158">-Копия</span><span class="sxs-lookup"><span data-stu-id="62fe6-158">-Cc</span></span>

<span data-ttu-id="62fe6-159">Указывает адреса электронной почты, на которые отправляется копия (CC) сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="62fe6-160">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="62fe6-161">-Credential</span></span>

<span data-ttu-id="62fe6-162">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="62fe6-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="62fe6-163">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="62fe6-163">The default is the current user.</span></span>

<span data-ttu-id="62fe6-164">Введите имя пользователя, например **User01** или **Domain01\User01** .</span><span class="sxs-lookup"><span data-stu-id="62fe6-164">Type a user name, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="62fe6-165">Или введите объект **PSCredential** , например один из `Get-Credential` командлетов.</span><span class="sxs-lookup"><span data-stu-id="62fe6-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="62fe6-166">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="62fe6-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="62fe6-167">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="62fe6-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-168">-Деливеринотификатионоптион</span><span class="sxs-lookup"><span data-stu-id="62fe6-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="62fe6-169">Указывает параметры уведомлений о доставке для сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="62fe6-170">Можно указать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="62fe6-170">You can specify multiple values.</span></span>
<span data-ttu-id="62fe6-171">Значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="62fe6-171">None is the default value.</span></span> <span data-ttu-id="62fe6-172">Псевдоним для этого параметра — **дно** .</span><span class="sxs-lookup"><span data-stu-id="62fe6-172">The alias for this parameter is **DNO** .</span></span>

<span data-ttu-id="62fe6-173">Уведомления о доставке отправляются на адрес в параметре **from** .</span><span class="sxs-lookup"><span data-stu-id="62fe6-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="62fe6-174">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="62fe6-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="62fe6-175">`None`: Нет уведомления.</span><span class="sxs-lookup"><span data-stu-id="62fe6-175">`None`: No notification.</span></span>
- <span data-ttu-id="62fe6-176">`OnSuccess`: Уведомлять, если доставка выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="62fe6-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="62fe6-177">`OnFailure`: Уведомлять, если доставка не выполнена.</span><span class="sxs-lookup"><span data-stu-id="62fe6-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="62fe6-178">`Delay`: Уведомлять при задержке доставки.</span><span class="sxs-lookup"><span data-stu-id="62fe6-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="62fe6-179">`Never`: Никогда не уведомлять.</span><span class="sxs-lookup"><span data-stu-id="62fe6-179">`Never`: Never notify.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-180">-Encoding</span><span class="sxs-lookup"><span data-stu-id="62fe6-180">-Encoding</span></span>

<span data-ttu-id="62fe6-181">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="62fe6-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="62fe6-182">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="62fe6-182">The default value is `Default`.</span></span>

<span data-ttu-id="62fe6-183">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="62fe6-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="62fe6-184">`ASCII` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="62fe6-184">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="62fe6-185">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="62fe6-185">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="62fe6-186">`Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="62fe6-186">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="62fe6-187">`OEM` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="62fe6-187">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="62fe6-188">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="62fe6-188">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="62fe6-189">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="62fe6-189">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="62fe6-190">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="62fe6-190">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="62fe6-191">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="62fe6-191">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-192">— От</span><span class="sxs-lookup"><span data-stu-id="62fe6-192">-From</span></span>

<span data-ttu-id="62fe6-193">Параметр **from** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="62fe6-193">The **From** parameter is required.</span></span> <span data-ttu-id="62fe6-194">Этот параметр указывает адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="62fe6-194">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="62fe6-195">Введите имя (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-195">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="62fe6-196">-Port</span><span class="sxs-lookup"><span data-stu-id="62fe6-196">-Port</span></span>

<span data-ttu-id="62fe6-197">Указывает дополнительный порт на сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="62fe6-197">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="62fe6-198">Значение по умолчанию — 25 (значение по умолчанию для порта SMTP).</span><span class="sxs-lookup"><span data-stu-id="62fe6-198">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-199">-Priority</span><span class="sxs-lookup"><span data-stu-id="62fe6-199">-Priority</span></span>

<span data-ttu-id="62fe6-200">Указывает приоритет сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-200">Specifies the priority of the email message.</span></span> <span data-ttu-id="62fe6-201">Значение по умолчанию: Normal.</span><span class="sxs-lookup"><span data-stu-id="62fe6-201">Normal is the default.</span></span> <span data-ttu-id="62fe6-202">Допустимые значения для этого параметра: обычная, высокая и низкая.</span><span class="sxs-lookup"><span data-stu-id="62fe6-202">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-203">-SMTP</span><span class="sxs-lookup"><span data-stu-id="62fe6-203">-SmtpServer</span></span>

<span data-ttu-id="62fe6-204">Указывает имя SMTP-сервера, который отправляет сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-204">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="62fe6-205">Значением по умолчанию является значение `$PSEmailServer` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="62fe6-205">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="62fe6-206">Если переменная предпочтений не задана и этот параметр не используется, `Send-MailMessage` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="62fe6-206">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-207">-Subject</span><span class="sxs-lookup"><span data-stu-id="62fe6-207">-Subject</span></span>

<span data-ttu-id="62fe6-208">Параметр **subject** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="62fe6-208">The **Subject** parameter is required.</span></span> <span data-ttu-id="62fe6-209">Этот параметр указывает тему сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-209">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-210">— Для</span><span class="sxs-lookup"><span data-stu-id="62fe6-210">-To</span></span>

<span data-ttu-id="62fe6-211">Параметр **to** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="62fe6-211">The **To** parameter is required.</span></span> <span data-ttu-id="62fe6-212">Этот параметр указывает адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="62fe6-212">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="62fe6-213">При наличии нескольких получателей разделите их адреса запятой ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="62fe6-213">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="62fe6-214">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-214">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="62fe6-215">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="62fe6-215">-UseSsl</span></span>

<span data-ttu-id="62fe6-216">Протокол SSL (SSL) используется для установления безопасного подключения к удаленному компьютеру для отправки почты.</span><span class="sxs-lookup"><span data-stu-id="62fe6-216">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="62fe6-217">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="62fe6-217">By default, SSL is not used.</span></span>

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

### <span data-ttu-id="62fe6-218">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="62fe6-218">CommonParameters</span></span>

<span data-ttu-id="62fe6-219">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="62fe6-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="62fe6-220">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="62fe6-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="62fe6-221">Входные данные</span><span class="sxs-lookup"><span data-stu-id="62fe6-221">INPUTS</span></span>

### <span data-ttu-id="62fe6-222">System.String</span><span class="sxs-lookup"><span data-stu-id="62fe6-222">System.String</span></span>

<span data-ttu-id="62fe6-223">Путь и имена файлов вложений можно передать в `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="62fe6-223">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="62fe6-224">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="62fe6-224">OUTPUTS</span></span>

### <span data-ttu-id="62fe6-225">Нет</span><span class="sxs-lookup"><span data-stu-id="62fe6-225">None</span></span>

<span data-ttu-id="62fe6-226">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="62fe6-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="62fe6-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="62fe6-227">NOTES</span></span>

## <span data-ttu-id="62fe6-228">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="62fe6-228">RELATED LINKS</span></span>

[<span data-ttu-id="62fe6-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="62fe6-229">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="62fe6-230">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="62fe6-230">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)
