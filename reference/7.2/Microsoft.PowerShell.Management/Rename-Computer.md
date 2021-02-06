---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 070a428530f4f3eecceb0ae3f520ad565097c1e0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604784"
---
# <span data-ttu-id="8384b-102">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="8384b-102">Rename-Computer</span></span>

## <span data-ttu-id="8384b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8384b-103">SYNOPSIS</span></span>
<span data-ttu-id="8384b-104">Переименовывает компьютер.</span><span class="sxs-lookup"><span data-stu-id="8384b-104">Renames a computer.</span></span>

## <span data-ttu-id="8384b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8384b-105">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8384b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8384b-106">DESCRIPTION</span></span>

<span data-ttu-id="8384b-107">`Rename-Computer`Командлет переименовывает локальный компьютер или удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8384b-107">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="8384b-108">Он переименовывает один компьютер в каждой команде.</span><span class="sxs-lookup"><span data-stu-id="8384b-108">It renames one computer in each command.</span></span>

<span data-ttu-id="8384b-109">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8384b-109">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="8384b-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="8384b-110">EXAMPLES</span></span>

### <span data-ttu-id="8384b-111">Пример 1. Переименование локального компьютера</span><span class="sxs-lookup"><span data-stu-id="8384b-111">Example 1: Rename the local computer</span></span>

<span data-ttu-id="8384b-112">Эта команда переименовывает локальный компьютер в `Server044` , а затем перезапускает его, чтобы сделать изменение эффективным.</span><span class="sxs-lookup"><span data-stu-id="8384b-112">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="8384b-113">Пример 2. Переименование удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="8384b-113">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="8384b-114">Эта команда переименовывает `Srv01` компьютер в `Server001` .</span><span class="sxs-lookup"><span data-stu-id="8384b-114">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="8384b-115">Компьютер не перезагружается.</span><span class="sxs-lookup"><span data-stu-id="8384b-115">The computer is not restarted.</span></span>

<span data-ttu-id="8384b-116">Параметр **домаинкредентиал** указывает учетные данные пользователя, имеющего разрешение на переименование компьютеров в домене.</span><span class="sxs-lookup"><span data-stu-id="8384b-116">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="8384b-117">Параметр **Force** подавляет вывод запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="8384b-117">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="8384b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8384b-118">PARAMETERS</span></span>

### <span data-ttu-id="8384b-119">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8384b-119">-ComputerName</span></span>

<span data-ttu-id="8384b-120">Переименовывает указанный удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8384b-120">Renames the specified remote computer.</span></span>
<span data-ttu-id="8384b-121">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8384b-121">The default is the local computer.</span></span>

<span data-ttu-id="8384b-122">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="8384b-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="8384b-123">Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или `localhost` .</span><span class="sxs-lookup"><span data-stu-id="8384b-123">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="8384b-124">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8384b-124">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="8384b-125">Параметр **ComputerName** можно использовать, `Rename-Computer` даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="8384b-125">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8384b-126">-Домаинкредентиал</span><span class="sxs-lookup"><span data-stu-id="8384b-126">-DomainCredential</span></span>

<span data-ttu-id="8384b-127">Указывает учетную запись пользователя, имеющую разрешение на подключение к домену.</span><span class="sxs-lookup"><span data-stu-id="8384b-127">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="8384b-128">Для переименования компьютера, присоединенного к домену, необходимо явно указать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="8384b-128">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="8384b-129">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="8384b-129">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="8384b-130">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="8384b-130">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="8384b-131">Чтобы указать учетную запись пользователя, имеющую разрешение на подключение к компьютеру, который задается параметром **ComputerName**, используйте параметр **LocalCredential**.</span><span class="sxs-lookup"><span data-stu-id="8384b-131">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8384b-132">-Force</span><span class="sxs-lookup"><span data-stu-id="8384b-132">-Force</span></span>

<span data-ttu-id="8384b-133">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="8384b-133">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8384b-134">-Локалкредентиал</span><span class="sxs-lookup"><span data-stu-id="8384b-134">-LocalCredential</span></span>

<span data-ttu-id="8384b-135">Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютеру, заданному параметром **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="8384b-135">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="8384b-136">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="8384b-136">The default is the current user.</span></span>

<span data-ttu-id="8384b-137">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="8384b-137">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="8384b-138">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="8384b-138">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="8384b-139">Чтобы указать учетную запись, имеющую разрешение на подключение к домену, используйте параметр **DomainCredential**.</span><span class="sxs-lookup"><span data-stu-id="8384b-139">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8384b-140">-NewName</span><span class="sxs-lookup"><span data-stu-id="8384b-140">-NewName</span></span>

<span data-ttu-id="8384b-141">Задает новое имя для компьютера.</span><span class="sxs-lookup"><span data-stu-id="8384b-141">Specifies a new name for the computer.</span></span>
<span data-ttu-id="8384b-142">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8384b-142">This parameter is required.</span></span>

<span data-ttu-id="8384b-143">Стандартные имена могут содержать буквы ( `a-z` ), ( `A-Z` ), цифры ( `0-9` ) и дефисы ( `-` ), но без пробелов и точек ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="8384b-143">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="8384b-144">Имя не может состоять только из цифр и может содержать не более 63 символов.</span><span class="sxs-lookup"><span data-stu-id="8384b-144">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8384b-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8384b-145">-PassThru</span></span>

<span data-ttu-id="8384b-146">Возвращает результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="8384b-146">Returns the results of the command.</span></span>
<span data-ttu-id="8384b-147">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8384b-147">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8384b-148">-Restart</span><span class="sxs-lookup"><span data-stu-id="8384b-148">-Restart</span></span>

<span data-ttu-id="8384b-149">Указывает, что этот командлет перезапускает переименованный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8384b-149">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="8384b-150">Чтобы изменения вступили в силу, часто требуется перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="8384b-150">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="8384b-151">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="8384b-151">-WsmanAuthentication</span></span>

<span data-ttu-id="8384b-152">Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan.</span><span class="sxs-lookup"><span data-stu-id="8384b-152">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="8384b-153">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8384b-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8384b-154">**Основной**</span><span class="sxs-lookup"><span data-stu-id="8384b-154">**Basic**</span></span>
- <span data-ttu-id="8384b-155">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="8384b-155">**CredSSP**</span></span>
- <span data-ttu-id="8384b-156">**Default**</span><span class="sxs-lookup"><span data-stu-id="8384b-156">**Default**</span></span>
- <span data-ttu-id="8384b-157">**Digest** (дайджест)</span><span class="sxs-lookup"><span data-stu-id="8384b-157">**Digest**</span></span>
- <span data-ttu-id="8384b-158">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="8384b-158">**Kerberos**</span></span>
- <span data-ttu-id="8384b-159">**Согласование**</span><span class="sxs-lookup"><span data-stu-id="8384b-159">**Negotiate**</span></span>

<span data-ttu-id="8384b-160">Значение по умолчанию ― **Default**.</span><span class="sxs-lookup"><span data-stu-id="8384b-160">The default value is **Default**.</span></span>

<span data-ttu-id="8384b-161">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="8384b-161">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="8384b-162">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="8384b-162">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="8384b-163">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="8384b-163">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="8384b-164">Если удаленный компьютер скомпрометирован, передаваемые ему учетные данные можно использовать для управления > сетевого сеанса.</span><span class="sxs-lookup"><span data-stu-id="8384b-164">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="8384b-165">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8384b-165">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8384b-166">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8384b-166">-Confirm</span></span>

<span data-ttu-id="8384b-167">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8384b-167">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8384b-168">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8384b-168">-WhatIf</span></span>

<span data-ttu-id="8384b-169">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8384b-169">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8384b-170">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8384b-170">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8384b-171">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8384b-171">CommonParameters</span></span>

<span data-ttu-id="8384b-172">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8384b-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8384b-173">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8384b-173">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8384b-174">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8384b-174">INPUTS</span></span>

### <span data-ttu-id="8384b-175">None</span><span class="sxs-lookup"><span data-stu-id="8384b-175">None</span></span>

<span data-ttu-id="8384b-176">Этот командлет не имеет параметров, которые принимают входные данные по значению.</span><span class="sxs-lookup"><span data-stu-id="8384b-176">This cmdlet does not have parameters that take input by value.</span></span> <span data-ttu-id="8384b-177">Тем не менее в этот командлет можно передавать значения свойств **ComputerName** и **NewName** объектов.</span><span class="sxs-lookup"><span data-stu-id="8384b-177">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="8384b-178">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8384b-178">OUTPUTS</span></span>

### <span data-ttu-id="8384b-179">Microsoft. PowerShell. Commands. Компутерчанжеинфо</span><span class="sxs-lookup"><span data-stu-id="8384b-179">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="8384b-180">Этот командлет возвращает объект **компутерчанжеинфо** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="8384b-180">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="8384b-181">В противном случае не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8384b-181">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="8384b-182">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8384b-182">NOTES</span></span>

<span data-ttu-id="8384b-183">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="8384b-183">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="8384b-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8384b-184">RELATED LINKS</span></span>

[<span data-ttu-id="8384b-185">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="8384b-185">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="8384b-186">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="8384b-186">Stop-Computer</span></span>](Stop-Computer.md)
