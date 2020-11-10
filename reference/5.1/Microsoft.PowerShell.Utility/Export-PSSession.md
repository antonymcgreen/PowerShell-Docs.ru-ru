---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: 11533a9b127dc6d088258392c0e142bfbe5c070c
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388031"
---
# <span data-ttu-id="73a94-103">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="73a94-103">Export-PSSession</span></span>

## <span data-ttu-id="73a94-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="73a94-104">SYNOPSIS</span></span>

<span data-ttu-id="73a94-105">Экспортирует команды из другого сеанса и сохраняет их в модуле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-105">Exports commands from another session and saves them in a PowerShell module.</span></span>

## <span data-ttu-id="73a94-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73a94-106">SYNTAX</span></span>

```
Export-PSSession [-Session] <PSSession> [-OutputModule] <string> [[-CommandName] <string[]>]
 [[-FormatTypeName] <string[]>] [-Force] [-Encoding <string>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <string[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-Certificate <X509Certificate2>]
 [<CommonParameters>]
```

## <span data-ttu-id="73a94-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73a94-107">DESCRIPTION</span></span>

<span data-ttu-id="73a94-108">`Export-PSSession`Командлет получает командлеты, функции, псевдонимы и другие типы команд из другого сеанса PowerShell (PSSession) на локальном или удаленном компьютере и сохраняет их в модуле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-108">The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module.</span></span> <span data-ttu-id="73a94-109">Чтобы добавить команды из модуля в текущий сеанс, используйте `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="73a94-109">To add the commands from the module to the current session, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="73a94-110">В отличие от `Import-PSSession` , которое импортирует команды из другого PSSession в текущий сеанс, `Export-PSSession` сохраняет команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="73a94-110">Unlike `Import-PSSession`, which imports commands from another PSSession into the current session, `Export-PSSession` saves the commands in a module.</span></span> <span data-ttu-id="73a94-111">Команды не импортируются в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="73a94-111">The commands are not imported into the current session.</span></span>

<span data-ttu-id="73a94-112">Чтобы экспортировать команды, используйте `New-PSSession` командлет, чтобы создать сеанс PSSession с командами, которые необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="73a94-112">To export commands, use the `New-PSSession` cmdlet to create a PSSession that has the commands that you want to export.</span></span> <span data-ttu-id="73a94-113">Затем с помощью `Export-PSSession` командлета экспортируйте команды.</span><span class="sxs-lookup"><span data-stu-id="73a94-113">Then use the `Export-PSSession` cmdlet to export the commands.</span></span>

<span data-ttu-id="73a94-114">Чтобы избежать конфликтов имен команд, по умолчанию для `Export-PSSession` используется параметр экспортировать все команды, за исключением команд, существующих в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-114">To prevent command name conflicts, the default for `Export-PSSession` is to export all commands, except for commands that exist in the current session.</span></span> <span data-ttu-id="73a94-115">Для указания экспортируемых команд можно использовать параметр **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="73a94-115">You can use the **CommandName** parameter to specify the commands to export.</span></span>

<span data-ttu-id="73a94-116">`Export-PSSession`Командлет использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-116">The `Export-PSSession` cmdlet uses the implicit remoting feature of PowerShell.</span></span> <span data-ttu-id="73a94-117">При импорте команд в текущий сеанс они выполняются неявно в исходном сеансе или в аналогичном сеансе на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73a94-117">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

## <span data-ttu-id="73a94-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="73a94-118">EXAMPLES</span></span>

### <span data-ttu-id="73a94-119">Пример 1. экспорт команд из PSSession</span><span class="sxs-lookup"><span data-stu-id="73a94-119">Example 1: Export commands from a PSSession</span></span>

<span data-ttu-id="73a94-120">В этом примере создается новый сеанс PSSession с локального компьютера на компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-120">This example creates a new PSSession from the local computer to the Server01 computer.</span></span> <span data-ttu-id="73a94-121">Все команды, за исключением тех, которые существуют в текущем сеансе, экспортируются в модуль с именем Server01 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73a94-121">All of the commands, except those that exist in the current session, are exported to the module named Server01 on the local computer.</span></span> <span data-ttu-id="73a94-122">Экспорт включает данные форматирования для команд.</span><span class="sxs-lookup"><span data-stu-id="73a94-122">The export includes the formatting data for the commands.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

<span data-ttu-id="73a94-123">`New-PSSession`Команда создает сеанс PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-123">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span> <span data-ttu-id="73a94-124">Сеанс PSSession хранится в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="73a94-124">The PSSession is stored in the `$S` variable.</span></span> <span data-ttu-id="73a94-125">`Export-PSSession`Команда экспортирует `$S` команды и данные форматирования переменной в модуль Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-125">The `Export-PSSession` command exports the `$S` variable's commands and formatting data into the Server01 module.</span></span>

### <span data-ttu-id="73a94-126">Пример 2. экспорт команд Get и Set</span><span class="sxs-lookup"><span data-stu-id="73a94-126">Example 2: Export the Get and Set commands</span></span>

<span data-ttu-id="73a94-127">В этом примере все `Get` команды и экспортируются `Set` с сервера.</span><span class="sxs-lookup"><span data-stu-id="73a94-127">This example exports all of the `Get` and `Set` commands from a server.</span></span>

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

<span data-ttu-id="73a94-128">Эти команды экспортируют `Get` `Set` команды и из оснастки Microsoft Exchange Server на удаленном компьютере в модуль Exchange в `$PSHOME\Modules` каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73a94-128">These commands export the `Get` and `Set` commands from a Microsoft Exchange Server snap-in on a remote computer to an Exchange module in the `$PSHOME\Modules` directory on the local computer.</span></span>
<span data-ttu-id="73a94-129">Размещение модуля в `$PSHOME\Modules` каталоге делает его доступным для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="73a94-129">Placing the module in the `$PSHOME\Modules` directory makes it accessible to all users of the computer.</span></span>

### <span data-ttu-id="73a94-130">Пример 3. экспорт команд с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="73a94-130">Example 3: Export commands from a remote computer</span></span>

<span data-ttu-id="73a94-131">В этом примере командлеты экспортируются из сеанса PSSession на удаленном компьютере и сохраняются в модуль на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73a94-131">This example exports cmdlets from a PSSession on a remote computer and saves them in a module on the local computer.</span></span> <span data-ttu-id="73a94-132">Командлеты из модуля добавляются в текущий сеанс, чтобы их можно было использовать.</span><span class="sxs-lookup"><span data-stu-id="73a94-132">The cmdlets from the module are added to the current session so that they can be used.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

<span data-ttu-id="73a94-133">`New-PSSession`Команда создает сеанс PSSession на компьютере Server01 и сохраняет его в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="73a94-133">The `New-PSSession` command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span> <span data-ttu-id="73a94-134">`Export-PSSession`Команда экспортирует командлеты, имена которых начинаются с сеанса PSSession в, в `$S` модуль TestCmdlets на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73a94-134">The `Export-PSSession` command exports the cmdlets whose names begin with Test from the PSSession in `$S` to the TestCmdlets module on the local computer.</span></span>

<span data-ttu-id="73a94-135">`Remove-PSSession`Командлет удаляет сеанс PSSession `$S` из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="73a94-135">The `Remove-PSSession` cmdlet deletes the PSSession in `$S` from the current session.</span></span> <span data-ttu-id="73a94-136">Эта команда показывает, что сеанс PSSession не должен быть активным для использования команд, импортированных из сеанса.</span><span class="sxs-lookup"><span data-stu-id="73a94-136">This command shows that the PSSession need not be active to use the commands that were imported from the session.</span></span> <span data-ttu-id="73a94-137">`Import-Module`Командлет добавляет командлеты в модуль TestCmdlets в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="73a94-137">The `Import-Module` cmdlet adds the cmdlets in the TestCmdlets module to the current session.</span></span> <span data-ttu-id="73a94-138">Команда может быть запущена в любом сеансе в любое время.</span><span class="sxs-lookup"><span data-stu-id="73a94-138">The command can be run in any session at any time.</span></span>

<span data-ttu-id="73a94-139">`Get-Help`Командлет возвращает справку для командлетов, имена которых начинаются с Test.</span><span class="sxs-lookup"><span data-stu-id="73a94-139">The `Get-Help` cmdlet gets help for cmdlets whose names begin with Test.</span></span> <span data-ttu-id="73a94-140">После добавления команд в модуль в текущий сеанс можно использовать `Get-Help` `Get-Command` командлеты и для получения сведений о импортированных командах.</span><span class="sxs-lookup"><span data-stu-id="73a94-140">After the commands in a module are added to the current session, you can use the `Get-Help` and `Get-Command` cmdlets to learn about the imported commands.</span></span> <span data-ttu-id="73a94-141">`Test-Files`Командлет был экспортирован с компьютера Server01 и добавлен в сеанс.</span><span class="sxs-lookup"><span data-stu-id="73a94-141">The `Test-Files` cmdlet was exported from the Server01 computer and added to the session.</span></span> <span data-ttu-id="73a94-142">`Test-Files`Командлет выполняется в удаленном сеансе на компьютере, с которого была импортирована команда.</span><span class="sxs-lookup"><span data-stu-id="73a94-142">The `Test-Files` cmdlet runs in a remote session on the computer from which the command was imported.</span></span> <span data-ttu-id="73a94-143">PowerShell создает сеанс на основе сведений, которые хранятся в модуле TestCmdlets.</span><span class="sxs-lookup"><span data-stu-id="73a94-143">PowerShell creates a session from information that is stored in the TestCmdlets module.</span></span>

### <span data-ttu-id="73a94-144">Пример 4. экспорт и затереть команд в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="73a94-144">Example 4: Export and clobber commands in the current session</span></span>

<span data-ttu-id="73a94-145">В этом примере выполняется экспорт команд, хранимых в переменной, в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="73a94-145">This example exports commands that are stored in a variable into the current session.</span></span>

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

<span data-ttu-id="73a94-146">Эта `Export-PSSession` команда экспортирует все команды и данные форматирования из сеанса PSSession в переменной в `$S` текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="73a94-146">This `Export-PSSession` command exports all commands and all formatting data from the PSSession in the `$S` variable into the current session.</span></span> <span data-ttu-id="73a94-147">Параметр **AllowClobber** включает команды с теми же именами, что и команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-147">The **AllowClobber** parameter includes commands with the same names as commands in the current session.</span></span>

### <span data-ttu-id="73a94-148">Пример 5. экспорт команд из закрытого сеанса PSSession</span><span class="sxs-lookup"><span data-stu-id="73a94-148">Example 5: Export commands from a closed PSSession</span></span>

<span data-ttu-id="73a94-149">В этом примере показано, как выполнить экспортированные команды с особыми параметрами, когда сеанс PSSession, создавший экспортированные команды, закрыт.</span><span class="sxs-lookup"><span data-stu-id="73a94-149">This example shows how to run the exported commands with special options when the PSSession that created the exported commands is closed.</span></span>

<span data-ttu-id="73a94-150">Если исходный удаленный сеанс закрывается при импорте модуля, модуль будет использовать любой открытый удаленный сеанс, который подключается к исходному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="73a94-150">If the original remote session is closed when a module is imported, the module will use any open remote session that connects to the originating computer.</span></span> <span data-ttu-id="73a94-151">Если на исходном компьютере нет текущего сеанса, модуль повторно установит сеанс.</span><span class="sxs-lookup"><span data-stu-id="73a94-151">If there is no current session to the originating computer, the module will reestablish a session.</span></span>

<span data-ttu-id="73a94-152">Чтобы выполнить экспортированные команды с особыми параметрами в удаленном сеансе, необходимо создать удаленный сеанс с этими параметрами перед импортом модуля.</span><span class="sxs-lookup"><span data-stu-id="73a94-152">To run exported commands with special options in a remote session, you must create a remote session with those options before you import the module.</span></span> <span data-ttu-id="73a94-153">Используйте `New-PSSession` командлет с параметром **SessionOption**</span><span class="sxs-lookup"><span data-stu-id="73a94-153">Use the `New-PSSession` cmdlet with the **SessionOption** parameter</span></span>

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

<span data-ttu-id="73a94-154">`New-PSSessionOption`Командлет создает объект **PSSessionOption** и сохраняет объект в `$Options` переменной.</span><span class="sxs-lookup"><span data-stu-id="73a94-154">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object, and it saves the object in the `$Options` variable.</span></span> <span data-ttu-id="73a94-155">`New-PSSession`Команда создает сеанс PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-155">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span>
<span data-ttu-id="73a94-156">Параметр **SessionOption** использует объект, хранящийся в `$Options` .</span><span class="sxs-lookup"><span data-stu-id="73a94-156">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="73a94-157">Сеанс хранится в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="73a94-157">The session is stored in the `$S` variable.</span></span>

<span data-ttu-id="73a94-158">`Export-PSSession`Командлет экспортирует команды из PSSession в в `$S` модуль Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-158">The `Export-PSSession` cmdlet exports commands from the PSSession in `$S` to the Server01 module.</span></span>
<span data-ttu-id="73a94-159">`Remove-PSSession`Командлет удаляет сеанс PSSession в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="73a94-159">The `Remove-PSSession` cmdlet deletes the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="73a94-160">`New-PSSession`Командлет создает новый сеанс PSSession, который подключается к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-160">The `New-PSSession` cmdlet creates a new PSSession that connects to the Server01 computer.</span></span> <span data-ttu-id="73a94-161">Параметр **SessionOption** использует объект, хранящийся в `$Options` .</span><span class="sxs-lookup"><span data-stu-id="73a94-161">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="73a94-162">`Import-Module`Командлет импортирует команды из модуля Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-162">The `Import-Module` cmdlet imports the commands from the Server01 module.</span></span> <span data-ttu-id="73a94-163">Команды в модуле запускаются в сеансе PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="73a94-163">The commands in the module are run in the PSSession on the Server01 computer.</span></span>

## <span data-ttu-id="73a94-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73a94-164">PARAMETERS</span></span>

### <span data-ttu-id="73a94-165">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="73a94-165">-AllowClobber</span></span>

<span data-ttu-id="73a94-166">Экспортирует указанные команды, даже если их имена совпадают с именами команд в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-166">Exports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="73a94-167">При экспорте команды с тем же именем, что и у команды в текущем сеансе, экспортированная команда скрывает или заменяет исходные команды.</span><span class="sxs-lookup"><span data-stu-id="73a94-167">If you export a command with the same name as a command in the current session, the exported command hides or replaces the original commands.</span></span> <span data-ttu-id="73a94-168">Дополнительные сведения см. в разделе [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="73a94-168">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>

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

### <span data-ttu-id="73a94-169">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="73a94-169">-ArgumentList</span></span>

<span data-ttu-id="73a94-170">Экспортирует вариант команды, полученный с использованием заданных аргументов (значений параметров).</span><span class="sxs-lookup"><span data-stu-id="73a94-170">Exports the variant of the command that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="73a94-171">Например, чтобы экспортировать вариант `Get-Item` команды в сертификате (CERT:) диск в PSSession в `$S` введите `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="73a94-171">For example, to export the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-172">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="73a94-172">-Certificate</span></span>

<span data-ttu-id="73a94-173">Указывает сертификат клиента, используемый для подписи файлов форматирования (\* .Format.ps1XML) или файлов модулей скриптов (. PSM1) в `Export-PSSession` создаваемом модуле.</span><span class="sxs-lookup"><span data-stu-id="73a94-173">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the module that `Export-PSSession` creates.</span></span> <span data-ttu-id="73a94-174">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="73a94-174">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="73a94-175">Чтобы найти сертификат, используйте `Get-PfxCertificate` командлет или используйте `Get-ChildItem` командлет в сертификате (CERT:). диск.</span><span class="sxs-lookup"><span data-stu-id="73a94-175">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="73a94-176">Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="73a94-176">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-177">-CommandName</span><span class="sxs-lookup"><span data-stu-id="73a94-177">-CommandName</span></span>

<span data-ttu-id="73a94-178">Экспортирует только команды с указанными именами или шаблонами имен.</span><span class="sxs-lookup"><span data-stu-id="73a94-178">Exports only the commands with the specified names or name patterns.</span></span> <span data-ttu-id="73a94-179">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="73a94-179">Wildcards are permitted.</span></span> <span data-ttu-id="73a94-180">Используйте **CommandName** или его псевдоним, **имя**.</span><span class="sxs-lookup"><span data-stu-id="73a94-180">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="73a94-181">По умолчанию `Export-PSSession` экспортирует все команды из PSSession, за исключением команд, имена которых совпадают с именами команд в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-181">By default, `Export-PSSession` exports all commands from the PSSession except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="73a94-182">Это предотвращает скрытие и замену команд в текущем сеансе командами.</span><span class="sxs-lookup"><span data-stu-id="73a94-182">This prevents commands from being hidden or replaced by commands in the current session.</span></span> <span data-ttu-id="73a94-183">Чтобы экспортировать все команды, даже те, которые скрывают или заменяют другие команды, используйте параметр **AllowClobber** .</span><span class="sxs-lookup"><span data-stu-id="73a94-183">To export all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="73a94-184">При использовании параметра **CommandName** файлы форматирования для команд не экспортируются, если не используется параметр **FormatTypeName** .</span><span class="sxs-lookup"><span data-stu-id="73a94-184">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="73a94-185">Аналогично, если используется параметр **FormatTypeName** , команды не экспортируются, если не используется параметр **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="73a94-185">Similarly, if you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="73a94-186">-CommandType</span><span class="sxs-lookup"><span data-stu-id="73a94-186">-CommandType</span></span>

<span data-ttu-id="73a94-187">Экспортирует только указанные типы объектов команд.</span><span class="sxs-lookup"><span data-stu-id="73a94-187">Exports only the specified types of command objects.</span></span> <span data-ttu-id="73a94-188">Используйте параметр **CommandType** или его псевдоним **Type**.</span><span class="sxs-lookup"><span data-stu-id="73a94-188">Use **CommandType** or its alias, **Type**.</span></span>

<span data-ttu-id="73a94-189">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="73a94-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="73a94-190">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="73a94-190">Alias.</span></span> <span data-ttu-id="73a94-191">Все псевдонимы PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-191">All PowerShell aliases in the current session.</span></span>
- <span data-ttu-id="73a94-192">Все.</span><span class="sxs-lookup"><span data-stu-id="73a94-192">All.</span></span> <span data-ttu-id="73a94-193">все типы команд.</span><span class="sxs-lookup"><span data-stu-id="73a94-193">All command types.</span></span> <span data-ttu-id="73a94-194">Он эквивалентен `Get-Command -Name *` .</span><span class="sxs-lookup"><span data-stu-id="73a94-194">It is the equivalent of `Get-Command -Name *`.</span></span>
- <span data-ttu-id="73a94-195">приложение.</span><span class="sxs-lookup"><span data-stu-id="73a94-195">Application.</span></span> <span data-ttu-id="73a94-196">Все файлы, кроме файлов PowerShell, в путях, указанных в переменной среды PATH ( `$env:path` ), включая txt, exe и DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="73a94-196">All files other than PowerShell files in paths listed in the Path environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="73a94-197">Командлет.</span><span class="sxs-lookup"><span data-stu-id="73a94-197">Cmdlet.</span></span> <span data-ttu-id="73a94-198">командлеты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-198">The cmdlets in the current session.</span></span> <span data-ttu-id="73a94-199">По умолчанию используется командлет.</span><span class="sxs-lookup"><span data-stu-id="73a94-199">Cmdlet is the default.</span></span>
- <span data-ttu-id="73a94-200">Настройка.</span><span class="sxs-lookup"><span data-stu-id="73a94-200">Configuration.</span></span> <span data-ttu-id="73a94-201">Конфигурация PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-201">A PowerShell configuration.</span></span> <span data-ttu-id="73a94-202">Дополнительные сведения см. в разделе [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="73a94-202">For more information, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>
- <span data-ttu-id="73a94-203">Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="73a94-203">ExternalScript.</span></span> <span data-ttu-id="73a94-204">Все PS1-файлы в путях, указанных в переменной среды PATH ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="73a94-204">All .ps1 files in the paths listed in the Path environment variable (`$env:path`).</span></span>
- <span data-ttu-id="73a94-205">Фильтр и функция.</span><span class="sxs-lookup"><span data-stu-id="73a94-205">Filter and Function.</span></span> <span data-ttu-id="73a94-206">Все функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-206">All PowerShell functions.</span></span>
- <span data-ttu-id="73a94-207">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="73a94-207">Script.</span></span> <span data-ttu-id="73a94-208">блоки скриптов в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="73a94-208">Script blocks in the current session.</span></span>
- <span data-ttu-id="73a94-209">Процессов.</span><span class="sxs-lookup"><span data-stu-id="73a94-209">Workflow.</span></span> <span data-ttu-id="73a94-210">Рабочий процесс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-210">A PowerShell workflow.</span></span> <span data-ttu-id="73a94-211">Дополнительные сведения см. в разделе [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span><span class="sxs-lookup"><span data-stu-id="73a94-211">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-212">-Encoding</span><span class="sxs-lookup"><span data-stu-id="73a94-212">-Encoding</span></span>

<span data-ttu-id="73a94-213">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="73a94-213">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="73a94-214">Значение по умолчанию — `UTF8`.</span><span class="sxs-lookup"><span data-stu-id="73a94-214">The default value is `UTF8`.</span></span>

<span data-ttu-id="73a94-215">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="73a94-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="73a94-216">`ASCII` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="73a94-216">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="73a94-217">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="73a94-217">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="73a94-218">`Default` Использует кодировку, соответствующую активной кодовой странице системы.</span><span class="sxs-lookup"><span data-stu-id="73a94-218">`Default` Uses the encoding that corresponds to the system's active code page.</span></span>
- <span data-ttu-id="73a94-219">`OEM` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="73a94-219">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="73a94-220">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="73a94-220">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="73a94-221">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="73a94-221">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="73a94-222">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="73a94-222">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="73a94-223">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="73a94-223">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: UTF8
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-224">-Force</span><span class="sxs-lookup"><span data-stu-id="73a94-224">-Force</span></span>

<span data-ttu-id="73a94-225">Перезаписывает один или несколько существующих выходных файлов, даже если для них задан атрибут "Только для чтения".</span><span class="sxs-lookup"><span data-stu-id="73a94-225">Overwrites one or more existing output files, even if the file has the read-only attribute.</span></span>

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

### <span data-ttu-id="73a94-226">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="73a94-226">-FormatTypeName</span></span>

<span data-ttu-id="73a94-227">Экспортирует инструкции форматирования только для указанных типов Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73a94-227">Exports formatting instructions only for the specified Microsoft .NET Framework types.</span></span> <span data-ttu-id="73a94-228">Введите имена типов.</span><span class="sxs-lookup"><span data-stu-id="73a94-228">Enter the type names.</span></span> <span data-ttu-id="73a94-229">По умолчанию `Export-PSSession` экспортирует инструкции по форматированию для всех типов .NET Framework, которые не входят в пространство имен **System. Management. Automation** .</span><span class="sxs-lookup"><span data-stu-id="73a94-229">By default, `Export-PSSession` exports formatting instructions for all .NET Framework types that are not in the **System.Management.Automation** namespace.</span></span>

<span data-ttu-id="73a94-230">Значение этого параметра должно быть именем типа, возвращаемого `Get-FormatData` командой в сеансе, из которого импортируются команды.</span><span class="sxs-lookup"><span data-stu-id="73a94-230">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="73a94-231">Чтобы получить все данные форматирования в удаленном сеансе, введите `*` .</span><span class="sxs-lookup"><span data-stu-id="73a94-231">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="73a94-232">Если используется параметр **FormatTypeName** , команды не экспортируются, если не используется параметр **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="73a94-232">If you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="73a94-233">При использовании параметра **CommandName** файлы форматирования для команд не экспортируются, если не используется параметр **FormatTypeName** .</span><span class="sxs-lookup"><span data-stu-id="73a94-233">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-234">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="73a94-234">-FullyQualifiedModule</span></span>

<span data-ttu-id="73a94-235">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="73a94-235">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="73a94-236">См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="73a94-236">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="73a94-237">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="73a94-237">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="73a94-238">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="73a94-238">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="73a94-239">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="73a94-239">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="73a94-240">два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="73a94-240">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-241">-Module</span><span class="sxs-lookup"><span data-stu-id="73a94-241">-Module</span></span>

<span data-ttu-id="73a94-242">Экспортирует только команды в указанных оснастках и модулях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-242">Exports only the commands in the specified PowerShell snap-ins and modules.</span></span> <span data-ttu-id="73a94-243">Введите имена оснасток и модулей.</span><span class="sxs-lookup"><span data-stu-id="73a94-243">Enter the snap-in and module names.</span></span> <span data-ttu-id="73a94-244">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="73a94-244">Wildcards are not permitted.</span></span>

<span data-ttu-id="73a94-245">Дополнительные сведения см. в статьях `Import-Module` и [about_PSSnapins](../Microsoft.PowerShell.Core/About/about_PSSnapins.md).</span><span class="sxs-lookup"><span data-stu-id="73a94-245">For more information, see `Import-Module` and [about_PSSnapins](../Microsoft.PowerShell.Core/About/about_PSSnapins.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-246">-Аутпутмодуле</span><span class="sxs-lookup"><span data-stu-id="73a94-246">-OutputModule</span></span>

<span data-ttu-id="73a94-247">Указывает необязательный путь и имя для модуля, созданного `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="73a94-247">Specifies an optional path and name for the module created by `Export-PSSession`.</span></span> <span data-ttu-id="73a94-248">Путь по умолчанию: `$home\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="73a94-248">The default path is `$home\Documents\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="73a94-249">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="73a94-249">This parameter is required.</span></span>

<span data-ttu-id="73a94-250">Если подкаталог модуля или любой из создаваемых файлов `Export-PSSession` уже существует, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="73a94-250">If the module subdirectory or any of the files that `Export-PSSession` creates already exist, the command fails.</span></span> <span data-ttu-id="73a94-251">Чтобы перезаписать существующие файлы, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="73a94-251">To overwrite existing files, use the **Force** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-252">-Session</span><span class="sxs-lookup"><span data-stu-id="73a94-252">-Session</span></span>

<span data-ttu-id="73a94-253">Указывает сеанс PSSession, из которого экспортируются команды.</span><span class="sxs-lookup"><span data-stu-id="73a94-253">Specifies the PSSession from which the commands are exported.</span></span> <span data-ttu-id="73a94-254">Введите переменную, содержащую объект сеанса, или команду, которая получает объект сеанса, например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="73a94-254">Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="73a94-255">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="73a94-255">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73a94-256">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="73a94-256">CommonParameters</span></span>

<span data-ttu-id="73a94-257">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73a94-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73a94-258">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="73a94-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="73a94-259">Входные данные</span><span class="sxs-lookup"><span data-stu-id="73a94-259">INPUTS</span></span>

### <span data-ttu-id="73a94-260">Нет</span><span class="sxs-lookup"><span data-stu-id="73a94-260">None</span></span>

<span data-ttu-id="73a94-261">Вы не можете передать объекты в `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="73a94-261">You cannot pipe objects to `Export-PSSession`.</span></span>

## <span data-ttu-id="73a94-262">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="73a94-262">OUTPUTS</span></span>

### <span data-ttu-id="73a94-263">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="73a94-263">System.IO.FileInfo</span></span>

<span data-ttu-id="73a94-264">`Export-PSSession` Возвращает список файлов, составляющих созданный им модуль.</span><span class="sxs-lookup"><span data-stu-id="73a94-264">`Export-PSSession` returns a list of files that comprise the module that it created.</span></span>

## <span data-ttu-id="73a94-265">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="73a94-265">NOTES</span></span>

<span data-ttu-id="73a94-266">`Export-PSSession` полагается на инфраструктуру удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-266">`Export-PSSession` relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="73a94-267">Для использования этого командлета компьютер должен быть настроен для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="73a94-267">To use this cmdlet, the computer must be configured for remoting.</span></span> <span data-ttu-id="73a94-268">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73a94-268">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="73a94-269">Нельзя использовать `Export-PSSession` для экспорта поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-269">You cannot use `Export-PSSession` to export a PowerShell provider.</span></span>

<span data-ttu-id="73a94-270">Экспортируемые команды выполняются неявно в сеансе PSSession, из которого они были экспортированы.</span><span class="sxs-lookup"><span data-stu-id="73a94-270">Exported commands run implicitly in the PSSession from which they were exported.</span></span> <span data-ttu-id="73a94-271">Сведения об удаленном выполнении команд полностью обрабатываются PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73a94-271">The details of running the commands remotely are handled entirely by PowerShell.</span></span> <span data-ttu-id="73a94-272">Экспортируемые команды можно выполнять так же, как и локальные.</span><span class="sxs-lookup"><span data-stu-id="73a94-272">You can run the exported commands just as you would run local commands.</span></span>

<span data-ttu-id="73a94-273">`Export-ModuleMember` захватывает и сохраняет сведения о PSSession в экспортируемом модуле.</span><span class="sxs-lookup"><span data-stu-id="73a94-273">`Export-ModuleMember` captures and saves information about the PSSession in the module that it exports.</span></span> <span data-ttu-id="73a94-274">Если сеанс PSSession, из которого экспортированы команды, закрывается при импорте модуля и отсутствуют активные PSSession на том же компьютере, команды в модуле пытаются повторно создать PSSession.</span><span class="sxs-lookup"><span data-stu-id="73a94-274">If the PSSession from which the commands were exported is closed when you import the module, and there are no active PSSessions to the same computer, the commands in the module attempt to recreate the PSSession.</span></span> <span data-ttu-id="73a94-275">Если попытка повторно создать сеанс PSSession завершится ошибкой, экспортированные команды не будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="73a94-275">If attempts to recreate the PSSession fail, the exported commands will not run.</span></span>

<span data-ttu-id="73a94-276">Сведения о сеансе, которые `Export-ModuleMember` регистрируются и сохраняются в модуле, не включают параметры сеанса, такие как указанные в `$PSSessionOption` переменной предпочтений или с помощью параметра **SessionOption** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, или.</span><span class="sxs-lookup"><span data-stu-id="73a94-276">The session information that `Export-ModuleMember` captures and saves in the module does not include session options, such as those that you specify in the `$PSSessionOption` preference variable or by using the **SessionOption** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span> <span data-ttu-id="73a94-277">Если при импорте модуля исходный сеанс PSSession закрыт, модуль будет использовать другой сеанс PSSession на том же компьютере, если такой доступен.</span><span class="sxs-lookup"><span data-stu-id="73a94-277">If the original PSSession is closed when you import the module, the module will use another PSSession to the same computer, if one is available.</span></span> <span data-ttu-id="73a94-278">Чтобы импортированные команды могли выполняться в правильно настроенном сеансе, создайте сеанс PSSession с нужными параметрами перед импортом модуля.</span><span class="sxs-lookup"><span data-stu-id="73a94-278">To enable the imported commands to run in a correctly configured session, create a PSSession with the options that you want before you import the module.</span></span>

<span data-ttu-id="73a94-279">Чтобы найти команды для экспорта, `Export-PSSession` использует `Invoke-Command` командлет для выполнения `Get-Command` команды в PSSession.</span><span class="sxs-lookup"><span data-stu-id="73a94-279">To find the commands to export, `Export-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="73a94-280">Чтобы получить и сохранить данные форматирования для команд, используются `Get-FormatData` `Export-FormatData` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="73a94-280">To get and save formatting data for the commands, it uses the `Get-FormatData` and `Export-FormatData` cmdlets.</span></span> <span data-ttu-id="73a94-281">При выполнении команды могут отображаться сообщения об ошибках `Invoke-Command` , `Get-Command` , `Get-FormatData` и `Export-FormatData` `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="73a94-281">You might see error messages from `Invoke-Command`, `Get-Command`, `Get-FormatData`, and `Export-FormatData` when you run an `Export-PSSession` command.</span></span> <span data-ttu-id="73a94-282">Кроме того, `Export-PSSession` не может экспортировать команды из сеанса, не включающего `Get-Command` `Get-FormatData` командлеты,, `Select-Object` и `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="73a94-282">Also, `Export-PSSession` cannot export commands from a session that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>

<span data-ttu-id="73a94-283">`Export-PSSession``Write-Progress`отображает ход выполнения команды с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="73a94-283">`Export-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="73a94-284">Во время выполнения команды может отображаться индикатор выполнения .</span><span class="sxs-lookup"><span data-stu-id="73a94-284">You might see the progress bar while the command is running.</span></span>

<span data-ttu-id="73a94-285">К экспортированным командам применяются те же ограничения, что и к другим удаленным командам, включая невозможность запустить программу с пользовательским интерфейсом, например Блокнот.</span><span class="sxs-lookup"><span data-stu-id="73a94-285">Exported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>

<span data-ttu-id="73a94-286">Так как профили PowerShell не выполняются в PSSession, команды, которые профиль добавляет в сеанс, недоступны `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="73a94-286">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Export-PSSession`.</span></span> <span data-ttu-id="73a94-287">Чтобы экспортировать команды из профиля, используйте `Invoke-Command` команду для запуска профиля в сеансе PSSession вручную перед экспортом команд.</span><span class="sxs-lookup"><span data-stu-id="73a94-287">To export commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before exporting commands.</span></span>

<span data-ttu-id="73a94-288">`Export-PSSession`Создаваемый модуль может включать файл форматирования, даже если команда не импортирует данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="73a94-288">The module that `Export-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="73a94-289">Если команда не импортирует данные форматирования, все создаваемые файлы форматирования не будут содержать данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="73a94-289">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>

## <span data-ttu-id="73a94-290">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="73a94-290">RELATED LINKS</span></span>

[<span data-ttu-id="73a94-291">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="73a94-291">about_Command_Precedence</span></span>](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[<span data-ttu-id="73a94-292">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="73a94-292">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="73a94-293">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="73a94-293">about_PSSnapins</span></span>](../Microsoft.PowerShell.Core/About/about_PSSnapins.md)

[<span data-ttu-id="73a94-294">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="73a94-294">about_Remote_Requirements</span></span>](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[<span data-ttu-id="73a94-295">Import-Module</span><span class="sxs-lookup"><span data-stu-id="73a94-295">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="73a94-296">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="73a94-296">Import-PSSession</span></span>](Import-PSSession.md)

[<span data-ttu-id="73a94-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="73a94-297">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="73a94-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="73a94-298">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="73a94-299">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="73a94-299">New-PSSessionOption</span></span>](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[<span data-ttu-id="73a94-300">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="73a94-300">Remove-PSSession</span></span>](../Microsoft.PowerShell.Core/Remove-PSSession.md)
