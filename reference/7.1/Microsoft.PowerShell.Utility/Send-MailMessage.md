---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: e100189b6c7fa128c373d9f2b9e1d6029162c0ed
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226578"
---
# <span data-ttu-id="a578c-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="a578c-103">Send-MailMessage</span></span>

## <span data-ttu-id="a578c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a578c-104">SYNOPSIS</span></span>
<span data-ttu-id="a578c-105">Отправляет сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-105">Sends an email message.</span></span>

## <span data-ttu-id="a578c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a578c-106">SYNTAX</span></span>

### <span data-ttu-id="a578c-107">Все</span><span class="sxs-lookup"><span data-stu-id="a578c-107">All</span></span>

```
Send-MailMessage [-Attachments <String[]>] [-Bcc <String[]>] [[-Body] <String>] [-BodyAsHtml]
 [-Encoding <Encoding>] [-Cc <String[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 -From <String> [[-SmtpServer] <String>] [-Priority <MailPriority>] [-ReplyTo <String[]>]
 [[-Subject] <String>] [-To] <String[]> [-Credential <PSCredential>] [-UseSsl] [-Port <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="a578c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a578c-108">DESCRIPTION</span></span>

<span data-ttu-id="a578c-109">`Send-MailMessage`Командлет отправляет сообщение электронной почты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a578c-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="a578c-110">Необходимо указать SMTP-сервер или `Send-MailMessage` выполнить команду с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a578c-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="a578c-111">Используйте параметр **SMTP** или задайте `$PSEmailServer` для переменной допустимый SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="a578c-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="a578c-112">Значение, присваиваемое, `$PSEmailServer` является параметром SMTP по умолчанию для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a578c-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="a578c-113">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a578c-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="a578c-114">`Send-MailMessage`Командлет устарел.</span><span class="sxs-lookup"><span data-stu-id="a578c-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="a578c-115">Этот командлет не гарантирует безопасное подключение к SMTP-серверам.</span><span class="sxs-lookup"><span data-stu-id="a578c-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="a578c-116">Хотя в PowerShell нет доступной немедленной замены, мы рекомендуем не использовать `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="a578c-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="a578c-117">Дополнительные сведения см. в разделе [Примечание о совместимости платформ DE0005](https://aka.ms/SendMailMessage).</span><span class="sxs-lookup"><span data-stu-id="a578c-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="a578c-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="a578c-118">EXAMPLES</span></span>

### <span data-ttu-id="a578c-119">Пример 1. Отправка сообщения электронной почты от одного пользователя другому человеку</span><span class="sxs-lookup"><span data-stu-id="a578c-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="a578c-120">В этом примере посылается сообщение электронной почты от одного лица другому человеку.</span><span class="sxs-lookup"><span data-stu-id="a578c-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="a578c-121">Параметры **from** , **to** и **subject** обязательны для `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="a578c-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="a578c-122">В этом примере используется переменная по умолчанию `$PSEmailServer` для SMTP-сервера, поэтому параметр **SMTP** не требуется.</span><span class="sxs-lookup"><span data-stu-id="a578c-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="a578c-123">`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="a578c-124">Параметр **to** указывает получателя сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="a578c-125">Параметр **subject** использует **тестовую почту** Text String в качестве сообщения, так как необязательный параметр **Body** не включен.</span><span class="sxs-lookup"><span data-stu-id="a578c-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="a578c-126">Пример 2. Отправка вложения</span><span class="sxs-lookup"><span data-stu-id="a578c-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="a578c-127">В этом примере отправляется сообщение электронной почты с вложением.</span><span class="sxs-lookup"><span data-stu-id="a578c-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="a578c-128">`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="a578c-129">Параметр **to** указывает получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="a578c-130">Параметр **subject** описывает содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="a578c-131">Параметр **Body** — это содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="a578c-132">Параметр **вложения** указывает файл в текущем каталоге, присоединенном к сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="a578c-133">Параметр **Priority** задает для сообщения **высокий** приоритет.</span><span class="sxs-lookup"><span data-stu-id="a578c-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="a578c-134">Параметр **-деливеринотификатионоптион** задает два значения: **onsuccesss** и **onSuccess**.</span><span class="sxs-lookup"><span data-stu-id="a578c-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure**.</span></span> <span data-ttu-id="a578c-135">Отправитель получит уведомления по электронной почте для подтверждения успешной или неуспешной доставки сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="a578c-136">Параметр **SMTP** задает для SMTP-сервера значение **SMTP.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="a578c-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com**.</span></span>

### <span data-ttu-id="a578c-137">Пример 3. Отправка сообщения электронной почты в список рассылки</span><span class="sxs-lookup"><span data-stu-id="a578c-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="a578c-138">В этом примере сообщение электронной почты отправляется в список рассылки.</span><span class="sxs-lookup"><span data-stu-id="a578c-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="a578c-139">`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="a578c-140">Параметр **to** указывает получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="a578c-141">Параметр **CC** отправляет копию сообщения указанному получателю.</span><span class="sxs-lookup"><span data-stu-id="a578c-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="a578c-142">Параметр **BCC** отправляет скрытую копию сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="a578c-143">Скрытая копия — это адрес электронной почты, который скрыт от других получателей.</span><span class="sxs-lookup"><span data-stu-id="a578c-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="a578c-144">Параметр **subject** является сообщением, так как необязательный параметр **тела** не включен.</span><span class="sxs-lookup"><span data-stu-id="a578c-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="a578c-145">Параметр **Credential** указывает учетные данные администратора домена, используемые для отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="a578c-146">Параметр **UseSsl** указывает, что протокол SSL создает безопасное соединение.</span><span class="sxs-lookup"><span data-stu-id="a578c-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="a578c-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a578c-147">PARAMETERS</span></span>

### <span data-ttu-id="a578c-148">— Вложения</span><span class="sxs-lookup"><span data-stu-id="a578c-148">-Attachments</span></span>

<span data-ttu-id="a578c-149">Указывает путь и имена файлов, которые будут присоединены к сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="a578c-150">Можно использовать этот параметр или передать пути и имена файлов в `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="a578c-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-151">-СК</span><span class="sxs-lookup"><span data-stu-id="a578c-151">-Bcc</span></span>

<span data-ttu-id="a578c-152">Указывает адреса электронной почты, получающие копию почты, но не указанные в качестве получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="a578c-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="a578c-153">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="a578c-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-154">-Body</span><span class="sxs-lookup"><span data-stu-id="a578c-154">-Body</span></span>

<span data-ttu-id="a578c-155">Указывает содержимое сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-155">Specifies the content of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-156">-Бодяштмл</span><span class="sxs-lookup"><span data-stu-id="a578c-156">-BodyAsHtml</span></span>

<span data-ttu-id="a578c-157">Указывает, что значение параметра **Body** содержит HTML.</span><span class="sxs-lookup"><span data-stu-id="a578c-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-158">-Копия</span><span class="sxs-lookup"><span data-stu-id="a578c-158">-Cc</span></span>

<span data-ttu-id="a578c-159">Указывает адреса электронной почты, на которые отправляется копия (CC) сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="a578c-160">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="a578c-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="a578c-161">-Credential</span></span>

<span data-ttu-id="a578c-162">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="a578c-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="a578c-163">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="a578c-163">The default is the current user.</span></span>

<span data-ttu-id="a578c-164">Введите имя пользователя, например **User01** или **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="a578c-164">Type a user name, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="a578c-165">Или введите объект **PSCredential** , например один из `Get-Credential` командлетов.</span><span class="sxs-lookup"><span data-stu-id="a578c-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="a578c-166">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="a578c-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a578c-167">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="a578c-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-168">-Деливеринотификатионоптион</span><span class="sxs-lookup"><span data-stu-id="a578c-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="a578c-169">Указывает параметры уведомлений о доставке для сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="a578c-170">Можно указать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="a578c-170">You can specify multiple values.</span></span>
<span data-ttu-id="a578c-171">Значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="a578c-171">None is the default value.</span></span> <span data-ttu-id="a578c-172">Псевдоним для этого параметра — **дно**.</span><span class="sxs-lookup"><span data-stu-id="a578c-172">The alias for this parameter is **DNO**.</span></span>

<span data-ttu-id="a578c-173">Уведомления о доставке отправляются на адрес в параметре **from** .</span><span class="sxs-lookup"><span data-stu-id="a578c-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="a578c-174">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a578c-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a578c-175">`None`: Нет уведомления.</span><span class="sxs-lookup"><span data-stu-id="a578c-175">`None`: No notification.</span></span>
- <span data-ttu-id="a578c-176">`OnSuccess`: Уведомлять, если доставка выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a578c-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="a578c-177">`OnFailure`: Уведомлять, если доставка не выполнена.</span><span class="sxs-lookup"><span data-stu-id="a578c-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="a578c-178">`Delay`: Уведомлять при задержке доставки.</span><span class="sxs-lookup"><span data-stu-id="a578c-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="a578c-179">`Never`: Никогда не уведомлять.</span><span class="sxs-lookup"><span data-stu-id="a578c-179">`Never`: Never notify.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-180">-Encoding</span><span class="sxs-lookup"><span data-stu-id="a578c-180">-Encoding</span></span>

<span data-ttu-id="a578c-181">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="a578c-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="a578c-182">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="a578c-182">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="a578c-183">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a578c-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a578c-184">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="a578c-184">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="a578c-185">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="a578c-185">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="a578c-186">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="a578c-186">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="a578c-187">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="a578c-187">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="a578c-188">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="a578c-188">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="a578c-189">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="a578c-189">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="a578c-190">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a578c-190">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="a578c-191">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="a578c-191">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a578c-192">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="a578c-192">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="a578c-193">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="a578c-193">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="a578c-194">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="a578c-194">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="a578c-195">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="a578c-195">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-196">— От</span><span class="sxs-lookup"><span data-stu-id="a578c-196">-From</span></span>

<span data-ttu-id="a578c-197">Параметр **from** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="a578c-197">The **From** parameter is required.</span></span> <span data-ttu-id="a578c-198">Этот параметр указывает адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="a578c-198">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="a578c-199">Введите имя (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="a578c-199">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-200">-Port</span><span class="sxs-lookup"><span data-stu-id="a578c-200">-Port</span></span>

<span data-ttu-id="a578c-201">Указывает дополнительный порт на сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="a578c-201">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="a578c-202">Значение по умолчанию — 25 (значение по умолчанию для порта SMTP).</span><span class="sxs-lookup"><span data-stu-id="a578c-202">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-203">-Priority</span><span class="sxs-lookup"><span data-stu-id="a578c-203">-Priority</span></span>

<span data-ttu-id="a578c-204">Указывает приоритет сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-204">Specifies the priority of the email message.</span></span> <span data-ttu-id="a578c-205">Значение по умолчанию: Normal.</span><span class="sxs-lookup"><span data-stu-id="a578c-205">Normal is the default.</span></span> <span data-ttu-id="a578c-206">Допустимые значения для этого параметра: обычная, высокая и низкая.</span><span class="sxs-lookup"><span data-stu-id="a578c-206">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-207">-ReplyTo</span><span class="sxs-lookup"><span data-stu-id="a578c-207">-ReplyTo</span></span>

<span data-ttu-id="a578c-208">Указывает дополнительные адреса электронной почты (отличные от адреса отклика), которые следует использовать для ответа на это сообщение.</span><span class="sxs-lookup"><span data-stu-id="a578c-208">Specifies additional email addresses (other than the From address) to use to reply to this message.</span></span>
<span data-ttu-id="a578c-209">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="a578c-209">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

<span data-ttu-id="a578c-210">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="a578c-210">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-211">-SMTP</span><span class="sxs-lookup"><span data-stu-id="a578c-211">-SmtpServer</span></span>

<span data-ttu-id="a578c-212">Указывает имя SMTP-сервера, который отправляет сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-212">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="a578c-213">Значением по умолчанию является значение `$PSEmailServer` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="a578c-213">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="a578c-214">Если переменная предпочтений не задана и этот параметр не используется, `Send-MailMessage` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a578c-214">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-215">-Subject</span><span class="sxs-lookup"><span data-stu-id="a578c-215">-Subject</span></span>

<span data-ttu-id="a578c-216">Параметр **subject** не требуется.</span><span class="sxs-lookup"><span data-stu-id="a578c-216">The **Subject** parameter isn't required.</span></span> <span data-ttu-id="a578c-217">Этот параметр указывает тему сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-217">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-218">— Для</span><span class="sxs-lookup"><span data-stu-id="a578c-218">-To</span></span>

<span data-ttu-id="a578c-219">Параметр **to** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="a578c-219">The **To** parameter is required.</span></span> <span data-ttu-id="a578c-220">Этот параметр указывает адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="a578c-220">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="a578c-221">При наличии нескольких получателей разделите их адреса запятой ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="a578c-221">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="a578c-222">Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="a578c-222">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a578c-223">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="a578c-223">-UseSsl</span></span>

<span data-ttu-id="a578c-224">Протокол SSL (SSL) используется для установления безопасного подключения к удаленному компьютеру для отправки почты.</span><span class="sxs-lookup"><span data-stu-id="a578c-224">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="a578c-225">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="a578c-225">By default, SSL is not used.</span></span>

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

### <span data-ttu-id="a578c-226">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a578c-226">CommonParameters</span></span>

<span data-ttu-id="a578c-227">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a578c-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a578c-228">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a578c-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a578c-229">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a578c-229">INPUTS</span></span>

### <span data-ttu-id="a578c-230">System.String</span><span class="sxs-lookup"><span data-stu-id="a578c-230">System.String</span></span>

<span data-ttu-id="a578c-231">Путь и имена файлов вложений можно передать в `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="a578c-231">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="a578c-232">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a578c-232">OUTPUTS</span></span>

### <span data-ttu-id="a578c-233">Нет</span><span class="sxs-lookup"><span data-stu-id="a578c-233">None</span></span>

<span data-ttu-id="a578c-234">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a578c-234">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a578c-235">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a578c-235">NOTES</span></span>

## <span data-ttu-id="a578c-236">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a578c-236">RELATED LINKS</span></span>

[<span data-ttu-id="a578c-237">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a578c-237">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="a578c-238">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="a578c-238">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

