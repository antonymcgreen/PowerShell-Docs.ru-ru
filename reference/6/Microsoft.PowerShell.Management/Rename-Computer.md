---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: e2d4f321609a386c6795949a4a706323b4889f69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228717"
---
# <span data-ttu-id="12d72-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="12d72-103">Rename-Computer</span></span>

## <span data-ttu-id="12d72-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="12d72-104">SYNOPSIS</span></span>
<span data-ttu-id="12d72-105">Переименовывает компьютер.</span><span class="sxs-lookup"><span data-stu-id="12d72-105">Renames a computer.</span></span>

## <span data-ttu-id="12d72-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12d72-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="12d72-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12d72-107">DESCRIPTION</span></span>

<span data-ttu-id="12d72-108">`Rename-Computer`Командлет переименовывает локальный компьютер или удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12d72-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="12d72-109">Он переименовывает один компьютер в каждой команде.</span><span class="sxs-lookup"><span data-stu-id="12d72-109">It renames one computer in each command.</span></span>

<span data-ttu-id="12d72-110">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="12d72-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="12d72-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="12d72-111">EXAMPLES</span></span>

### <span data-ttu-id="12d72-112">Пример 1. Переименование локального компьютера</span><span class="sxs-lookup"><span data-stu-id="12d72-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="12d72-113">Эта команда переименовывает локальный компьютер в `Server044` , а затем перезапускает его, чтобы сделать изменение эффективным.</span><span class="sxs-lookup"><span data-stu-id="12d72-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="12d72-114">Пример 2. Переименование удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="12d72-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="12d72-115">Эта команда переименовывает `Srv01` компьютер в `Server001` .</span><span class="sxs-lookup"><span data-stu-id="12d72-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="12d72-116">Компьютер не перезагружается.</span><span class="sxs-lookup"><span data-stu-id="12d72-116">The computer is not restarted.</span></span>

<span data-ttu-id="12d72-117">Параметр **домаинкредентиал** указывает учетные данные пользователя, имеющего разрешение на переименование компьютеров в домене.</span><span class="sxs-lookup"><span data-stu-id="12d72-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="12d72-118">Параметр **Force** подавляет вывод запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="12d72-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="12d72-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12d72-119">PARAMETERS</span></span>

### <span data-ttu-id="12d72-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="12d72-120">-ComputerName</span></span>

<span data-ttu-id="12d72-121">Переименовывает указанный удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12d72-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="12d72-122">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12d72-122">The default is the local computer.</span></span>

<span data-ttu-id="12d72-123">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="12d72-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="12d72-124">Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или `localhost` .</span><span class="sxs-lookup"><span data-stu-id="12d72-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="12d72-125">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12d72-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="12d72-126">Параметр **ComputerName** можно использовать, `Rename-Computer` даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="12d72-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="12d72-127">-Домаинкредентиал</span><span class="sxs-lookup"><span data-stu-id="12d72-127">-DomainCredential</span></span>

<span data-ttu-id="12d72-128">Указывает учетную запись пользователя, имеющую разрешение на подключение к домену.</span><span class="sxs-lookup"><span data-stu-id="12d72-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="12d72-129">Для переименования компьютера, присоединенного к домену, необходимо явно указать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="12d72-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="12d72-130">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="12d72-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="12d72-131">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="12d72-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="12d72-132">Чтобы указать учетную запись пользователя, имеющую разрешение на подключение к компьютеру, который задается параметром **ComputerName** , используйте параметр **LocalCredential** .</span><span class="sxs-lookup"><span data-stu-id="12d72-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

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

### <span data-ttu-id="12d72-133">-Force</span><span class="sxs-lookup"><span data-stu-id="12d72-133">-Force</span></span>

<span data-ttu-id="12d72-134">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="12d72-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="12d72-135">-Локалкредентиал</span><span class="sxs-lookup"><span data-stu-id="12d72-135">-LocalCredential</span></span>

<span data-ttu-id="12d72-136">Указывает учетную запись пользователя, имеющую разрешение на подключение к компьютеру, заданному параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="12d72-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="12d72-137">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="12d72-137">The default is the current user.</span></span>

<span data-ttu-id="12d72-138">Введите имя пользователя, например `User01` или `Domain01\User01` , или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="12d72-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="12d72-139">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="12d72-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="12d72-140">Чтобы указать учетную запись, имеющую разрешение на подключение к домену, используйте параметр **DomainCredential** .</span><span class="sxs-lookup"><span data-stu-id="12d72-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

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

### <span data-ttu-id="12d72-141">-NewName</span><span class="sxs-lookup"><span data-stu-id="12d72-141">-NewName</span></span>

<span data-ttu-id="12d72-142">Задает новое имя для компьютера.</span><span class="sxs-lookup"><span data-stu-id="12d72-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="12d72-143">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="12d72-143">This parameter is required.</span></span>

<span data-ttu-id="12d72-144">Стандартные имена могут содержать буквы ( `a-z` ), ( `A-Z` ), цифры ( `0-9` ) и дефисы ( `-` ), но без пробелов и точек ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="12d72-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="12d72-145">Имя не может состоять только из цифр и может содержать не более 63 символов.</span><span class="sxs-lookup"><span data-stu-id="12d72-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

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

### <span data-ttu-id="12d72-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="12d72-146">-PassThru</span></span>

<span data-ttu-id="12d72-147">Возвращает результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="12d72-147">Returns the results of the command.</span></span>
<span data-ttu-id="12d72-148">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="12d72-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="12d72-149">-Restart</span><span class="sxs-lookup"><span data-stu-id="12d72-149">-Restart</span></span>

<span data-ttu-id="12d72-150">Указывает, что этот командлет перезапускает переименованный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12d72-150">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="12d72-151">Чтобы изменения вступили в силу, часто требуется перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="12d72-151">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="12d72-152">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="12d72-152">-WsmanAuthentication</span></span>

<span data-ttu-id="12d72-153">Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan.</span><span class="sxs-lookup"><span data-stu-id="12d72-153">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="12d72-154">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="12d72-154">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="12d72-155">**Основной**</span><span class="sxs-lookup"><span data-stu-id="12d72-155">**Basic**</span></span>
- <span data-ttu-id="12d72-156">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="12d72-156">**CredSSP**</span></span>
- <span data-ttu-id="12d72-157">**Default**</span><span class="sxs-lookup"><span data-stu-id="12d72-157">**Default**</span></span>
- <span data-ttu-id="12d72-158">**Digest** (дайджест)</span><span class="sxs-lookup"><span data-stu-id="12d72-158">**Digest**</span></span>
- <span data-ttu-id="12d72-159">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="12d72-159">**Kerberos**</span></span>
- <span data-ttu-id="12d72-160">**Новое**</span><span class="sxs-lookup"><span data-stu-id="12d72-160">**Negotiate**</span></span>

<span data-ttu-id="12d72-161">Значение по умолчанию ― **Default** .</span><span class="sxs-lookup"><span data-stu-id="12d72-161">The default value is **Default** .</span></span>

<span data-ttu-id="12d72-162">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="12d72-162">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="12d72-163">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="12d72-163">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="12d72-164">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="12d72-164">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="12d72-165">Если удаленный компьютер скомпрометирован, передаваемые ему учетные данные можно использовать для управления > сетевого сеанса.</span><span class="sxs-lookup"><span data-stu-id="12d72-165">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="12d72-166">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="12d72-166">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="12d72-167">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12d72-167">-Confirm</span></span>

<span data-ttu-id="12d72-168">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="12d72-168">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="12d72-169">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12d72-169">-WhatIf</span></span>

<span data-ttu-id="12d72-170">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="12d72-170">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="12d72-171">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="12d72-171">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="12d72-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="12d72-172">CommonParameters</span></span>

<span data-ttu-id="12d72-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12d72-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12d72-174">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="12d72-174">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="12d72-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="12d72-175">INPUTS</span></span>

### <span data-ttu-id="12d72-176">Нет</span><span class="sxs-lookup"><span data-stu-id="12d72-176">None</span></span>

<span data-ttu-id="12d72-177">Этот командлет не имеет параметров, которые принимают входные данные по значению.</span><span class="sxs-lookup"><span data-stu-id="12d72-177">This cmdlet does not have parameters that take input by value.</span></span>
<span data-ttu-id="12d72-178">Тем не менее в этот командлет можно передавать значения свойств **ComputerName** и **NewName** объектов.</span><span class="sxs-lookup"><span data-stu-id="12d72-178">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="12d72-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="12d72-179">OUTPUTS</span></span>

### <span data-ttu-id="12d72-180">Microsoft. PowerShell. Commands. Компутерчанжеинфо</span><span class="sxs-lookup"><span data-stu-id="12d72-180">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="12d72-181">Этот командлет возвращает объект **компутерчанжеинфо** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="12d72-181">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="12d72-182">В противном случае не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="12d72-182">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="12d72-183">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="12d72-183">NOTES</span></span>

## <span data-ttu-id="12d72-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="12d72-184">RELATED LINKS</span></span>

[<span data-ttu-id="12d72-185">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="12d72-185">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="12d72-186">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="12d72-186">Stop-Computer</span></span>](Stop-Computer.md)
