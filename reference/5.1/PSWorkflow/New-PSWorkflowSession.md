---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227346"
---
# <span data-ttu-id="bd4eb-103">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="bd4eb-103">New-PSWorkflowSession</span></span>

## <span data-ttu-id="bd4eb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bd4eb-104">SYNOPSIS</span></span>
<span data-ttu-id="bd4eb-105">Создает сеанс рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-105">Creates a workflow session.</span></span>

## <span data-ttu-id="bd4eb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd4eb-106">SYNTAX</span></span>

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## <span data-ttu-id="bd4eb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd4eb-107">DESCRIPTION</span></span>

<span data-ttu-id="bd4eb-108">`New-PSWorkflowSession`Командлет создает управляемый пользователем сеанс ( **PSSession** ), который специально предназначен для запуска рабочих процессов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-108">The `New-PSWorkflowSession` cmdlet creates a user-managed session ( **PSSession** ) that is especially designed for running Windows PowerShell workflows.</span></span> <span data-ttu-id="bd4eb-109">Он использует конфигурацию сеанса Microsoft.PowerShell.Workflow, которая включает в себя сценарии, файлы типов и форматирования, а также параметры, необходимые для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-109">It uses the Microsoft.PowerShell.Workflow session configuration, which includes scripts, type and formatting files, and options that are required for workflows.</span></span>

<span data-ttu-id="bd4eb-110">Можно использовать `New-PSWorkflowSession` или его псевдоним, `nwsn` .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-110">You can use `New-PSWorkflowSession` or its alias, `nwsn`.</span></span>

<span data-ttu-id="bd4eb-111">В эту команду также можно добавить общие параметры рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-111">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="bd4eb-112">Дополнительные сведения о общих параметрах рабочего процесса см. в разделе [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="bd4eb-112">For more information about workflow common parameters, see [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="bd4eb-113">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="bd4eb-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="bd4eb-114">EXAMPLES</span></span>

### <span data-ttu-id="bd4eb-115">Пример 1. Создание сеанса рабочего процесса на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="bd4eb-115">Example 1: Create a workflow session on a remote computer</span></span>

<span data-ttu-id="bd4eb-116">В этом примере создается сеанс **воркфловтестс** на удаленном компьютере ServerNode01.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-116">This example creates the **WorkflowTests** session on the ServerNode01 remote computer.</span></span>

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

<span data-ttu-id="bd4eb-117">Значение параметра **SessionOption** — это `New-PSSessionOption` команда, которая устанавливает режим буферизации вывода в сеансе для **удаления** .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-117">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that sets the output buffering mode in the session to **Drop** .</span></span>

### <span data-ttu-id="bd4eb-118">Пример 2. Создание сеансов рабочих процессов на нескольких удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="bd4eb-118">Example 2: Create workflow sessions on multiple remote computers</span></span>

<span data-ttu-id="bd4eb-119">В этом примере создаются сеансы рабочего процесса на компьютерах ServerNode01 и Server12.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-119">This example creates workflow sessions on the ServerNode01 and Server12 computers.</span></span> <span data-ttu-id="bd4eb-120">Команда использует параметр **Credential** для выполнения с правами администратора домена.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-120">The command uses the **Credential** parameter to run with the permissions of the domain administrator.</span></span>

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

<span data-ttu-id="bd4eb-121">Команда использует параметр **ThrottleLimit** , чтобы увеличить предел регулирования для отдельной команды до 150.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-121">The command uses the **ThrottleLimit** parameter to increase the per-command throttle limit to 150.</span></span>
<span data-ttu-id="bd4eb-122">Это значение имеет приоритет над ограничением регулирования по умолчанию 100, установленным в конфигурации сеанса **Microsoft. PowerShell. Workflow** .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-122">This value takes precedence over the default throttle limit of 100 that is set in the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

## <span data-ttu-id="bd4eb-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd4eb-123">PARAMETERS</span></span>

### <span data-ttu-id="bd4eb-124">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="bd4eb-124">-ApplicationName</span></span>

<span data-ttu-id="bd4eb-125">Определяет сегмент имени приложения в URI соединения.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-125">Specifies the application name segment of the connection URI.</span></span>

<span data-ttu-id="bd4eb-126">Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-126">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="bd4eb-127">Если привилегированная переменная не определена, значение по умолчанию — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-127">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="bd4eb-128">Это значение подходит для большинства случаев</span><span class="sxs-lookup"><span data-stu-id="bd4eb-128">This value is appropriate for most uses.</span></span> <span data-ttu-id="bd4eb-129">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-129">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="bd4eb-130">Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-130">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="bd4eb-131">Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-131">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="bd4eb-132">-Authentication</span><span class="sxs-lookup"><span data-stu-id="bd4eb-132">-Authentication</span></span>

<span data-ttu-id="bd4eb-133">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-133">Specifies the mechanism that is used to authenticate the user credentials.</span></span>
<span data-ttu-id="bd4eb-134">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bd4eb-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd4eb-135">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="bd4eb-135">Default</span></span>
- <span data-ttu-id="bd4eb-136">Базовый</span><span class="sxs-lookup"><span data-stu-id="bd4eb-136">Basic</span></span>
- <span data-ttu-id="bd4eb-137">CredSSP</span><span class="sxs-lookup"><span data-stu-id="bd4eb-137">Credssp</span></span>
- <span data-ttu-id="bd4eb-138">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="bd4eb-138">Digest</span></span>
- <span data-ttu-id="bd4eb-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="bd4eb-139">Kerberos</span></span>
- <span data-ttu-id="bd4eb-140">Согласование</span><span class="sxs-lookup"><span data-stu-id="bd4eb-140">Negotiate</span></span>
- <span data-ttu-id="bd4eb-141">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="bd4eb-141">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="bd4eb-142">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-142">The default value is Default.</span></span>

<span data-ttu-id="bd4eb-143">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-143">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="bd4eb-144">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-144">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="bd4eb-145">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-145">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="bd4eb-146">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="bd4eb-147">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-148">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="bd4eb-148">-CertificateThumbprint</span></span>

<span data-ttu-id="bd4eb-149">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-149">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="bd4eb-150">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="bd4eb-151">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="bd4eb-152">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="bd4eb-153">Чтобы получить отпечаток сертификата, используйте `Get-Item` командлет или `Get-ChildItem` командлет на диске Windows PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-153">To get a certificate thumbprint, use the `Get-Item` cmdlet or the `Get-ChildItem` cmdlet in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="bd4eb-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="bd4eb-154">-ComputerName</span></span>

<span data-ttu-id="bd4eb-155">Создает постоянное подключение ( **PSSession** ) к указанному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-155">Creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="bd4eb-156">При вводе нескольких имен компьютеров Windows PowerShell создает несколько **PSSession** , по одному на каждый компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-156">If you enter multiple computer names, Windows PowerShell creates multiple **PSSessions** , one for each computer.</span></span> <span data-ttu-id="bd4eb-157">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-157">The default is the local computer.</span></span>

<span data-ttu-id="bd4eb-158">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-158">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="bd4eb-159">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-159">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="bd4eb-160">Если компьютер находится в другом домене, отличном от домена пользователя, полное доменное имя является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-160">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="bd4eb-161">Также можно передать имя компьютера в кавычках в `New-PSWorkflowSession` .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-161">You can also pipe a computer name, in quotation marks to `New-PSWorkflowSession`.</span></span>

<span data-ttu-id="bd4eb-162">Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-162">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="bd4eb-163">Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-163">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="bd4eb-164">Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-164">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="bd4eb-165">-Credential</span></span>

<span data-ttu-id="bd4eb-166">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="bd4eb-167">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-167">The default is the current user.</span></span> <span data-ttu-id="bd4eb-168">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com , или введите объект **PSCredential** , например, возвращаемый `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com, or enter a **PSCredential** object, such as one returned by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="bd4eb-169">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-169">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-170">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="bd4eb-170">-EnableNetworkAccess</span></span>

<span data-ttu-id="bd4eb-171">Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-171">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="bd4eb-172">Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-172">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="bd4eb-173">Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-173">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="bd4eb-174">Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-174">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="bd4eb-175">Чтобы создать сеанс замыкания на себя, не указывайте параметр **ComputerName** или задайте для него значение Dot, localhost или имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-175">To create a loopback session, do not specify the **ComputerName** parameter or set its value to dot, localhost, or the name of the local computer.</span></span>

<span data-ttu-id="bd4eb-176">По умолчанию создаются сеансы замыкания на себя, имеющие токен сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-176">By default, loopback sessions are created that have a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="bd4eb-177">Параметр **EnableNetworkAccess** действует только в петлевых сеансах.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-177">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="bd4eb-178">Если при создании сеанса на удаленном компьютере указать параметр **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-178">If you specify the **EnableNetworkAccess** parameter when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="bd4eb-179">Удаленный доступ в петлевом сеансе также можно разрешить с помощью значения **CredSSP** параметра **Authentication** , который делегирует учетные данные сеанса на другие компьютеры.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-179">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="bd4eb-180">Для защиты компьютера от вредоносного доступа отключенные сеансы замыкания на себя с интерактивными маркерами, созданные с помощью параметра **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-180">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="bd4eb-181">Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-181">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="bd4eb-182">Дополнительную информацию см. в описании командлета `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-182">For more information, see the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="bd4eb-183">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="bd4eb-184">-Name</span><span class="sxs-lookup"><span data-stu-id="bd4eb-184">-Name</span></span>

<span data-ttu-id="bd4eb-185">Задает понятное имя для сеанса рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-185">Specifies a friendly name for the workflow session.</span></span> <span data-ttu-id="bd4eb-186">Имя можно использовать с другими командлетами, такими как `Get-PSSession` и `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-186">You can use the name with other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="bd4eb-187">Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-187">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-188">-Port</span><span class="sxs-lookup"><span data-stu-id="bd4eb-188">-Port</span></span>

<span data-ttu-id="bd4eb-189">Задает сетевой порт на удаленном компьютере, используемый для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-189">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="bd4eb-190">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-190">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="bd4eb-191">Порты по умолчанию: 5985 (порт WinRM для HTTP) и 5986 (порт WinRM для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-191">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="bd4eb-192">Прежде чем использовать другой порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-192">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="bd4eb-193">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="bd4eb-193">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="bd4eb-194">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-194">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="bd4eb-195">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-195">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="bd4eb-196">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-196">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-197">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="bd4eb-197">-SessionOption</span></span>

<span data-ttu-id="bd4eb-198">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-198">Specifies advanced options for the session.</span></span> <span data-ttu-id="bd4eb-199">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-199">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="bd4eb-200">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-200">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="bd4eb-201">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-201">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="bd4eb-202">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-202">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="bd4eb-203">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-203">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="bd4eb-204">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-204">For more information about session configurations, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="bd4eb-205">Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="bd4eb-205">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="bd4eb-206">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-206">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-207">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="bd4eb-207">-ThrottleLimit</span></span>

<span data-ttu-id="bd4eb-208">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-208">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="bd4eb-209">Если опустить этот параметр или ввести значение 0 (ноль), используется значение по умолчанию для конфигурации сеанса **Microsoft. повершеллворкфлов** , 100.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-209">If you omit this parameter or enter a value of 0 (zero), the default value for the **Microsoft.PowerShellWorkflow** session configuration, 100, is used.</span></span>

<span data-ttu-id="bd4eb-210">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-210">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd4eb-211">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="bd4eb-211">-UseSSL</span></span>

<span data-ttu-id="bd4eb-212">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-212">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="bd4eb-213">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-213">By default, SSL is not used.</span></span>

<span data-ttu-id="bd4eb-214">Протокол WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-214">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="bd4eb-215">Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-215">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="bd4eb-216">Если указать этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-216">If you specify this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="bd4eb-217">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bd4eb-217">CommonParameters</span></span>

<span data-ttu-id="bd4eb-218">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd4eb-219">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd4eb-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd4eb-220">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bd4eb-220">INPUTS</span></span>

### <span data-ttu-id="bd4eb-221">System.Management.Automation.Runspaces.PSSession[], System.String</span><span class="sxs-lookup"><span data-stu-id="bd4eb-221">System.Management.Automation.Runspaces.PSSession[], System.String</span></span>

<span data-ttu-id="bd4eb-222">В этот командлет можно передать по конвейеру сеанс или имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="bd4eb-222">You can pipe a session or a computer name to this cmdlet.</span></span>

## <span data-ttu-id="bd4eb-223">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bd4eb-223">OUTPUTS</span></span>

### <span data-ttu-id="bd4eb-224">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="bd4eb-224">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="bd4eb-225">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bd4eb-225">NOTES</span></span>

<span data-ttu-id="bd4eb-226">`New-PSWorkflowSession`Команда эквивалентна следующей команде:</span><span class="sxs-lookup"><span data-stu-id="bd4eb-226">A `New-PSWorkflowSession` command is equivalent to the following command:</span></span>

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## <span data-ttu-id="bd4eb-227">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bd4eb-227">RELATED LINKS</span></span>

[<span data-ttu-id="bd4eb-228">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="bd4eb-228">Disconnect-PSSession</span></span>](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[<span data-ttu-id="bd4eb-229">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="bd4eb-229">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="bd4eb-230">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="bd4eb-230">New-PSTransportOption</span></span>](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[<span data-ttu-id="bd4eb-231">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="bd4eb-231">Register-PSSessionConfiguration</span></span>](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[<span data-ttu-id="bd4eb-232">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="bd4eb-232">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="bd4eb-233">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="bd4eb-233">about_Session_Configurations</span></span>](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[<span data-ttu-id="bd4eb-234">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="bd4eb-234">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="bd4eb-235">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd4eb-235">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
