---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: 5d5841720c6187863902a929632e15d1687685e1
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389408"
---
# <span data-ttu-id="b487d-103">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="b487d-103">Export-PSSession</span></span>

## <span data-ttu-id="b487d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b487d-104">SYNOPSIS</span></span>

<span data-ttu-id="b487d-105">Экспортирует команды из другого сеанса и сохраняет их в модуле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-105">Exports commands from another session and saves them in a PowerShell module.</span></span>

## <span data-ttu-id="b487d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b487d-106">SYNTAX</span></span>

### <span data-ttu-id="b487d-107">Все</span><span class="sxs-lookup"><span data-stu-id="b487d-107">All</span></span>

```
Export-PSSession [-OutputModule] <String> [-Force] [-Encoding <Encoding>]
 [[-CommandName] <String[]>] [-AllowClobber] [-ArgumentList <Object[]>]
 [-CommandType <CommandTypes>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-FormatTypeName] <String[]>] [-Certificate <X509Certificate2>] [-Session] <PSSession>
 [<CommonParameters>]
```

## <span data-ttu-id="b487d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b487d-108">DESCRIPTION</span></span>

<span data-ttu-id="b487d-109">`Export-PSSession`Командлет получает командлеты, функции, псевдонимы и другие типы команд из другого сеанса PowerShell (PSSession) на локальном или удаленном компьютере и сохраняет их в модуле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-109">The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module.</span></span> <span data-ttu-id="b487d-110">Чтобы добавить команды из модуля в текущий сеанс, используйте `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="b487d-110">To add the commands from the module to the current session, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="b487d-111">В отличие от `Import-PSSession` , которое импортирует команды из другого PSSession в текущий сеанс, `Export-PSSession` сохраняет команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="b487d-111">Unlike `Import-PSSession`, which imports commands from another PSSession into the current session, `Export-PSSession` saves the commands in a module.</span></span> <span data-ttu-id="b487d-112">Команды не импортируются в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b487d-112">The commands are not imported into the current session.</span></span>

<span data-ttu-id="b487d-113">Чтобы экспортировать команды, используйте `New-PSSession` командлет, чтобы создать сеанс PSSession с командами, которые необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="b487d-113">To export commands, use the `New-PSSession` cmdlet to create a PSSession that has the commands that you want to export.</span></span> <span data-ttu-id="b487d-114">Затем с помощью `Export-PSSession` командлета экспортируйте команды.</span><span class="sxs-lookup"><span data-stu-id="b487d-114">Then use the `Export-PSSession` cmdlet to export the commands.</span></span>

<span data-ttu-id="b487d-115">Чтобы избежать конфликтов имен команд, по умолчанию для `Export-PSSession` используется параметр экспортировать все команды, за исключением команд, существующих в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-115">To prevent command name conflicts, the default for `Export-PSSession` is to export all commands, except for commands that exist in the current session.</span></span> <span data-ttu-id="b487d-116">Для указания экспортируемых команд можно использовать параметр **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="b487d-116">You can use the **CommandName** parameter to specify the commands to export.</span></span>

<span data-ttu-id="b487d-117">`Export-PSSession`Командлет использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-117">The `Export-PSSession` cmdlet uses the implicit remoting feature of PowerShell.</span></span> <span data-ttu-id="b487d-118">При импорте команд в текущий сеанс они выполняются неявно в исходном сеансе или в аналогичном сеансе на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b487d-118">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

## <span data-ttu-id="b487d-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="b487d-119">EXAMPLES</span></span>

### <span data-ttu-id="b487d-120">Пример 1. экспорт команд из PSSession</span><span class="sxs-lookup"><span data-stu-id="b487d-120">Example 1: Export commands from a PSSession</span></span>

<span data-ttu-id="b487d-121">В этом примере создается новый сеанс PSSession с локального компьютера на компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-121">This example creates a new PSSession from the local computer to the Server01 computer.</span></span> <span data-ttu-id="b487d-122">Все команды, за исключением тех, которые существуют в текущем сеансе, экспортируются в модуль с именем Server01 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b487d-122">All of the commands, except those that exist in the current session, are exported to the module named Server01 on the local computer.</span></span> <span data-ttu-id="b487d-123">Экспорт включает данные форматирования для команд.</span><span class="sxs-lookup"><span data-stu-id="b487d-123">The export includes the formatting data for the commands.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

<span data-ttu-id="b487d-124">`New-PSSession`Команда создает сеанс PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-124">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span> <span data-ttu-id="b487d-125">Сеанс PSSession хранится в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="b487d-125">The PSSession is stored in the `$S` variable.</span></span> <span data-ttu-id="b487d-126">`Export-PSSession`Команда экспортирует `$S` команды и данные форматирования переменной в модуль Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-126">The `Export-PSSession` command exports the `$S` variable's commands and formatting data into the Server01 module.</span></span>

### <span data-ttu-id="b487d-127">Пример 2. экспорт команд Get и Set</span><span class="sxs-lookup"><span data-stu-id="b487d-127">Example 2: Export the Get and Set commands</span></span>

<span data-ttu-id="b487d-128">В этом примере все `Get` команды и экспортируются `Set` с сервера.</span><span class="sxs-lookup"><span data-stu-id="b487d-128">This example exports all of the `Get` and `Set` commands from a server.</span></span>

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

<span data-ttu-id="b487d-129">Эти команды экспортируют `Get` `Set` команды и из оснастки Microsoft Exchange Server на удаленном компьютере в модуль Exchange в `$PSHOME\Modules` каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b487d-129">These commands export the `Get` and `Set` commands from a Microsoft Exchange Server snap-in on a remote computer to an Exchange module in the `$PSHOME\Modules` directory on the local computer.</span></span>
<span data-ttu-id="b487d-130">Размещение модуля в `$PSHOME\Modules` каталоге делает его доступным для всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="b487d-130">Placing the module in the `$PSHOME\Modules` directory makes it accessible to all users of the computer.</span></span>

### <span data-ttu-id="b487d-131">Пример 3. экспорт команд с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="b487d-131">Example 3: Export commands from a remote computer</span></span>

<span data-ttu-id="b487d-132">В этом примере командлеты экспортируются из сеанса PSSession на удаленном компьютере и сохраняются в модуль на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b487d-132">This example exports cmdlets from a PSSession on a remote computer and saves them in a module on the local computer.</span></span> <span data-ttu-id="b487d-133">Командлеты из модуля добавляются в текущий сеанс, чтобы их можно было использовать.</span><span class="sxs-lookup"><span data-stu-id="b487d-133">The cmdlets from the module are added to the current session so that they can be used.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

<span data-ttu-id="b487d-134">`New-PSSession`Команда создает сеанс PSSession на компьютере Server01 и сохраняет его в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="b487d-134">The `New-PSSession` command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span> <span data-ttu-id="b487d-135">`Export-PSSession`Команда экспортирует командлеты, имена которых начинаются с сеанса PSSession в, в `$S` модуль TestCmdlets на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b487d-135">The `Export-PSSession` command exports the cmdlets whose names begin with Test from the PSSession in `$S` to the TestCmdlets module on the local computer.</span></span>

<span data-ttu-id="b487d-136">`Remove-PSSession`Командлет удаляет сеанс PSSession `$S` из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b487d-136">The `Remove-PSSession` cmdlet deletes the PSSession in `$S` from the current session.</span></span> <span data-ttu-id="b487d-137">Эта команда показывает, что сеанс PSSession не должен быть активным для использования команд, импортированных из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b487d-137">This command shows that the PSSession need not be active to use the commands that were imported from the session.</span></span> <span data-ttu-id="b487d-138">`Import-Module`Командлет добавляет командлеты в модуль TestCmdlets в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b487d-138">The `Import-Module` cmdlet adds the cmdlets in the TestCmdlets module to the current session.</span></span> <span data-ttu-id="b487d-139">Команда может быть запущена в любом сеансе в любое время.</span><span class="sxs-lookup"><span data-stu-id="b487d-139">The command can be run in any session at any time.</span></span>

<span data-ttu-id="b487d-140">`Get-Help`Командлет возвращает справку для командлетов, имена которых начинаются с Test.</span><span class="sxs-lookup"><span data-stu-id="b487d-140">The `Get-Help` cmdlet gets help for cmdlets whose names begin with Test.</span></span> <span data-ttu-id="b487d-141">После добавления команд в модуль в текущий сеанс можно использовать `Get-Help` `Get-Command` командлеты и для получения сведений о импортированных командах.</span><span class="sxs-lookup"><span data-stu-id="b487d-141">After the commands in a module are added to the current session, you can use the `Get-Help` and `Get-Command` cmdlets to learn about the imported commands.</span></span> <span data-ttu-id="b487d-142">`Test-Files`Командлет был экспортирован с компьютера Server01 и добавлен в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b487d-142">The `Test-Files` cmdlet was exported from the Server01 computer and added to the session.</span></span> <span data-ttu-id="b487d-143">`Test-Files`Командлет выполняется в удаленном сеансе на компьютере, с которого была импортирована команда.</span><span class="sxs-lookup"><span data-stu-id="b487d-143">The `Test-Files` cmdlet runs in a remote session on the computer from which the command was imported.</span></span> <span data-ttu-id="b487d-144">PowerShell создает сеанс на основе сведений, которые хранятся в модуле TestCmdlets.</span><span class="sxs-lookup"><span data-stu-id="b487d-144">PowerShell creates a session from information that is stored in the TestCmdlets module.</span></span>

### <span data-ttu-id="b487d-145">Пример 4. экспорт и затереть команд в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="b487d-145">Example 4: Export and clobber commands in the current session</span></span>

<span data-ttu-id="b487d-146">В этом примере выполняется экспорт команд, хранимых в переменной, в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b487d-146">This example exports commands that are stored in a variable into the current session.</span></span>

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

<span data-ttu-id="b487d-147">Эта `Export-PSSession` команда экспортирует все команды и данные форматирования из сеанса PSSession в переменной в `$S` текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b487d-147">This `Export-PSSession` command exports all commands and all formatting data from the PSSession in the `$S` variable into the current session.</span></span> <span data-ttu-id="b487d-148">Параметр **AllowClobber** включает команды с теми же именами, что и команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-148">The **AllowClobber** parameter includes commands with the same names as commands in the current session.</span></span>

### <span data-ttu-id="b487d-149">Пример 5. экспорт команд из закрытого сеанса PSSession</span><span class="sxs-lookup"><span data-stu-id="b487d-149">Example 5: Export commands from a closed PSSession</span></span>

<span data-ttu-id="b487d-150">В этом примере показано, как выполнить экспортированные команды с особыми параметрами, когда сеанс PSSession, создавший экспортированные команды, закрыт.</span><span class="sxs-lookup"><span data-stu-id="b487d-150">This example shows how to run the exported commands with special options when the PSSession that created the exported commands is closed.</span></span>

<span data-ttu-id="b487d-151">Если исходный удаленный сеанс закрывается при импорте модуля, модуль будет использовать любой открытый удаленный сеанс, который подключается к исходному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="b487d-151">If the original remote session is closed when a module is imported, the module will use any open remote session that connects to the originating computer.</span></span> <span data-ttu-id="b487d-152">Если на исходном компьютере нет текущего сеанса, модуль повторно установит сеанс.</span><span class="sxs-lookup"><span data-stu-id="b487d-152">If there is no current session to the originating computer, the module will reestablish a session.</span></span>

<span data-ttu-id="b487d-153">Чтобы выполнить экспортированные команды с особыми параметрами в удаленном сеансе, необходимо создать удаленный сеанс с этими параметрами перед импортом модуля.</span><span class="sxs-lookup"><span data-stu-id="b487d-153">To run exported commands with special options in a remote session, you must create a remote session with those options before you import the module.</span></span> <span data-ttu-id="b487d-154">Используйте `New-PSSession` командлет с параметром **SessionOption**</span><span class="sxs-lookup"><span data-stu-id="b487d-154">Use the `New-PSSession` cmdlet with the **SessionOption** parameter</span></span>

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

<span data-ttu-id="b487d-155">`New-PSSessionOption`Командлет создает объект **PSSessionOption** и сохраняет объект в `$Options` переменной.</span><span class="sxs-lookup"><span data-stu-id="b487d-155">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object, and it saves the object in the `$Options` variable.</span></span> <span data-ttu-id="b487d-156">`New-PSSession`Команда создает сеанс PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-156">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span>
<span data-ttu-id="b487d-157">Параметр **SessionOption** использует объект, хранящийся в `$Options` .</span><span class="sxs-lookup"><span data-stu-id="b487d-157">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="b487d-158">Сеанс хранится в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="b487d-158">The session is stored in the `$S` variable.</span></span>

<span data-ttu-id="b487d-159">`Export-PSSession`Командлет экспортирует команды из PSSession в в `$S` модуль Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-159">The `Export-PSSession` cmdlet exports commands from the PSSession in `$S` to the Server01 module.</span></span>
<span data-ttu-id="b487d-160">`Remove-PSSession`Командлет удаляет сеанс PSSession в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="b487d-160">The `Remove-PSSession` cmdlet deletes the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="b487d-161">`New-PSSession`Командлет создает новый сеанс PSSession, который подключается к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-161">The `New-PSSession` cmdlet creates a new PSSession that connects to the Server01 computer.</span></span> <span data-ttu-id="b487d-162">Параметр **SessionOption** использует объект, хранящийся в `$Options` .</span><span class="sxs-lookup"><span data-stu-id="b487d-162">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="b487d-163">`Import-Module`Командлет импортирует команды из модуля Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-163">The `Import-Module` cmdlet imports the commands from the Server01 module.</span></span> <span data-ttu-id="b487d-164">Команды в модуле запускаются в сеансе PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="b487d-164">The commands in the module are run in the PSSession on the Server01 computer.</span></span>

## <span data-ttu-id="b487d-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b487d-165">PARAMETERS</span></span>

### <span data-ttu-id="b487d-166">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="b487d-166">-AllowClobber</span></span>

<span data-ttu-id="b487d-167">Экспортирует указанные команды, даже если их имена совпадают с именами команд в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-167">Exports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="b487d-168">При экспорте команды с тем же именем, что и у команды в текущем сеансе, экспортированная команда скрывает или заменяет исходные команды.</span><span class="sxs-lookup"><span data-stu-id="b487d-168">If you export a command with the same name as a command in the current session, the exported command hides or replaces the original commands.</span></span> <span data-ttu-id="b487d-169">Дополнительные сведения см. в разделе [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b487d-169">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>

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

### <span data-ttu-id="b487d-170">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="b487d-170">-ArgumentList</span></span>

<span data-ttu-id="b487d-171">Экспортирует вариант команды, полученный с использованием заданных аргументов (значений параметров).</span><span class="sxs-lookup"><span data-stu-id="b487d-171">Exports the variant of the command that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="b487d-172">Например, чтобы экспортировать вариант `Get-Item` команды в сертификате (CERT:) диск в PSSession в `$S` введите `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="b487d-172">For example, to export the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="b487d-173">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="b487d-173">-Certificate</span></span>

<span data-ttu-id="b487d-174">Указывает сертификат клиента, используемый для подписи файлов форматирования (\* .Format.ps1XML) или файлов модулей скриптов (. PSM1) в `Export-PSSession` создаваемом модуле.</span><span class="sxs-lookup"><span data-stu-id="b487d-174">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the module that `Export-PSSession` creates.</span></span> <span data-ttu-id="b487d-175">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="b487d-175">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="b487d-176">Чтобы найти сертификат, используйте `Get-PfxCertificate` командлет или используйте `Get-ChildItem` командлет в сертификате (CERT:). диск.</span><span class="sxs-lookup"><span data-stu-id="b487d-176">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="b487d-177">Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b487d-177">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="b487d-178">-CommandName</span><span class="sxs-lookup"><span data-stu-id="b487d-178">-CommandName</span></span>

<span data-ttu-id="b487d-179">Экспортирует только команды с указанными именами или шаблонами имен.</span><span class="sxs-lookup"><span data-stu-id="b487d-179">Exports only the commands with the specified names or name patterns.</span></span> <span data-ttu-id="b487d-180">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b487d-180">Wildcards are permitted.</span></span> <span data-ttu-id="b487d-181">Используйте **CommandName** или его псевдоним, **имя**.</span><span class="sxs-lookup"><span data-stu-id="b487d-181">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="b487d-182">По умолчанию `Export-PSSession` экспортирует все команды из PSSession, за исключением команд, имена которых совпадают с именами команд в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-182">By default, `Export-PSSession` exports all commands from the PSSession except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="b487d-183">Это предотвращает скрытие и замену команд в текущем сеансе командами.</span><span class="sxs-lookup"><span data-stu-id="b487d-183">This prevents commands from being hidden or replaced by commands in the current session.</span></span> <span data-ttu-id="b487d-184">Чтобы экспортировать все команды, даже те, которые скрывают или заменяют другие команды, используйте параметр **AllowClobber** .</span><span class="sxs-lookup"><span data-stu-id="b487d-184">To export all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="b487d-185">При использовании параметра **CommandName** файлы форматирования для команд не экспортируются, если не используется параметр **FormatTypeName** .</span><span class="sxs-lookup"><span data-stu-id="b487d-185">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="b487d-186">Аналогично, если используется параметр **FormatTypeName** , команды не экспортируются, если не используется параметр **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="b487d-186">Similarly, if you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

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

### <span data-ttu-id="b487d-187">-CommandType</span><span class="sxs-lookup"><span data-stu-id="b487d-187">-CommandType</span></span>

<span data-ttu-id="b487d-188">Экспортирует только указанные типы объектов команд.</span><span class="sxs-lookup"><span data-stu-id="b487d-188">Exports only the specified types of command objects.</span></span> <span data-ttu-id="b487d-189">Используйте параметр **CommandType** или его псевдоним **Type**.</span><span class="sxs-lookup"><span data-stu-id="b487d-189">Use **CommandType** or its alias, **Type**.</span></span>

<span data-ttu-id="b487d-190">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b487d-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b487d-191">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b487d-191">Alias.</span></span> <span data-ttu-id="b487d-192">Все псевдонимы PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-192">All PowerShell aliases in the current session.</span></span>
- <span data-ttu-id="b487d-193">Все.</span><span class="sxs-lookup"><span data-stu-id="b487d-193">All.</span></span> <span data-ttu-id="b487d-194">все типы команд.</span><span class="sxs-lookup"><span data-stu-id="b487d-194">All command types.</span></span> <span data-ttu-id="b487d-195">Он эквивалентен `Get-Command -Name *` .</span><span class="sxs-lookup"><span data-stu-id="b487d-195">It is the equivalent of `Get-Command -Name *`.</span></span>
- <span data-ttu-id="b487d-196">приложение.</span><span class="sxs-lookup"><span data-stu-id="b487d-196">Application.</span></span> <span data-ttu-id="b487d-197">Все файлы, кроме файлов PowerShell, в путях, указанных в переменной среды PATH ( `$env:path` ), включая txt, exe и DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="b487d-197">All files other than PowerShell files in paths listed in the Path environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="b487d-198">Командлет.</span><span class="sxs-lookup"><span data-stu-id="b487d-198">Cmdlet.</span></span> <span data-ttu-id="b487d-199">командлеты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-199">The cmdlets in the current session.</span></span> <span data-ttu-id="b487d-200">По умолчанию используется командлет.</span><span class="sxs-lookup"><span data-stu-id="b487d-200">Cmdlet is the default.</span></span>
- <span data-ttu-id="b487d-201">Настройка.</span><span class="sxs-lookup"><span data-stu-id="b487d-201">Configuration.</span></span> <span data-ttu-id="b487d-202">Конфигурация PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-202">A PowerShell configuration.</span></span> <span data-ttu-id="b487d-203">Дополнительные сведения см. в разделе [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="b487d-203">For more information, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>
- <span data-ttu-id="b487d-204">Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="b487d-204">ExternalScript.</span></span> <span data-ttu-id="b487d-205">Все PS1-файлы в путях, указанных в переменной среды PATH ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="b487d-205">All .ps1 files in the paths listed in the Path environment variable (`$env:path`).</span></span>
- <span data-ttu-id="b487d-206">Фильтр и функция.</span><span class="sxs-lookup"><span data-stu-id="b487d-206">Filter and Function.</span></span> <span data-ttu-id="b487d-207">Все функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-207">All PowerShell functions.</span></span>
- <span data-ttu-id="b487d-208">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="b487d-208">Script.</span></span> <span data-ttu-id="b487d-209">блоки скриптов в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b487d-209">Script blocks in the current session.</span></span>
- <span data-ttu-id="b487d-210">Процессов.</span><span class="sxs-lookup"><span data-stu-id="b487d-210">Workflow.</span></span> <span data-ttu-id="b487d-211">Рабочий процесс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-211">A PowerShell workflow.</span></span> <span data-ttu-id="b487d-212">Дополнительные сведения см. в разделе [about_Workflows](/powershell/module/PSWorkflow/About/about_Workflows).</span><span class="sxs-lookup"><span data-stu-id="b487d-212">For more information, see [about_Workflows](/powershell/module/PSWorkflow/About/about_Workflows).</span></span>

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

### <span data-ttu-id="b487d-213">-Encoding</span><span class="sxs-lookup"><span data-stu-id="b487d-213">-Encoding</span></span>

<span data-ttu-id="b487d-214">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="b487d-214">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="b487d-215">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="b487d-215">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="b487d-216">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b487d-216">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b487d-217">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="b487d-217">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b487d-218">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="b487d-218">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="b487d-219">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="b487d-219">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="b487d-220">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="b487d-220">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="b487d-221">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="b487d-221">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="b487d-222">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b487d-222">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="b487d-223">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b487d-223">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="b487d-224">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="b487d-224">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b487d-225">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="b487d-225">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b487d-226">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="b487d-226">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="b487d-227">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="b487d-227">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="b487d-228">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="b487d-228">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b487d-229">-Force</span><span class="sxs-lookup"><span data-stu-id="b487d-229">-Force</span></span>

<span data-ttu-id="b487d-230">Перезаписывает один или несколько существующих выходных файлов, даже если для них задан атрибут "Только для чтения".</span><span class="sxs-lookup"><span data-stu-id="b487d-230">Overwrites one or more existing output files, even if the file has the read-only attribute.</span></span>

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

### <span data-ttu-id="b487d-231">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="b487d-231">-FormatTypeName</span></span>

<span data-ttu-id="b487d-232">Экспортирует инструкции форматирования только для указанных типов Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b487d-232">Exports formatting instructions only for the specified Microsoft .NET Framework types.</span></span> <span data-ttu-id="b487d-233">Введите имена типов.</span><span class="sxs-lookup"><span data-stu-id="b487d-233">Enter the type names.</span></span> <span data-ttu-id="b487d-234">По умолчанию `Export-PSSession` экспортирует инструкции по форматированию для всех типов .NET Framework, которые не входят в пространство имен **System. Management. Automation** .</span><span class="sxs-lookup"><span data-stu-id="b487d-234">By default, `Export-PSSession` exports formatting instructions for all .NET Framework types that are not in the **System.Management.Automation** namespace.</span></span>

<span data-ttu-id="b487d-235">Значение этого параметра должно быть именем типа, возвращаемого `Get-FormatData` командой в сеансе, из которого импортируются команды.</span><span class="sxs-lookup"><span data-stu-id="b487d-235">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="b487d-236">Чтобы получить все данные форматирования в удаленном сеансе, введите `*` .</span><span class="sxs-lookup"><span data-stu-id="b487d-236">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="b487d-237">Если используется параметр **FormatTypeName** , команды не экспортируются, если не используется параметр **CommandName** .</span><span class="sxs-lookup"><span data-stu-id="b487d-237">If you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="b487d-238">При использовании параметра **CommandName** файлы форматирования для команд не экспортируются, если не используется параметр **FormatTypeName** .</span><span class="sxs-lookup"><span data-stu-id="b487d-238">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span>

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

### <span data-ttu-id="b487d-239">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="b487d-239">-FullyQualifiedModule</span></span>

<span data-ttu-id="b487d-240">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="b487d-240">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="b487d-241">См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="b487d-241">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="b487d-242">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="b487d-242">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="b487d-243">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="b487d-243">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="b487d-244">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="b487d-244">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="b487d-245">два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="b487d-245">the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="b487d-246">-Module</span><span class="sxs-lookup"><span data-stu-id="b487d-246">-Module</span></span>

<span data-ttu-id="b487d-247">Экспортирует только команды в указанных оснастках и модулях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-247">Exports only the commands in the specified PowerShell snap-ins and modules.</span></span> <span data-ttu-id="b487d-248">Введите имена оснасток и модулей.</span><span class="sxs-lookup"><span data-stu-id="b487d-248">Enter the snap-in and module names.</span></span> <span data-ttu-id="b487d-249">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="b487d-249">Wildcards are not permitted.</span></span>

<span data-ttu-id="b487d-250">Дополнительные сведения см. в статьях `Import-Module` и [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).</span><span class="sxs-lookup"><span data-stu-id="b487d-250">For more information, see `Import-Module` and [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).</span></span>

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

### <span data-ttu-id="b487d-251">-Аутпутмодуле</span><span class="sxs-lookup"><span data-stu-id="b487d-251">-OutputModule</span></span>

<span data-ttu-id="b487d-252">Указывает необязательный путь и имя для модуля, созданного `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="b487d-252">Specifies an optional path and name for the module created by `Export-PSSession`.</span></span> <span data-ttu-id="b487d-253">Путь по умолчанию: `$home\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="b487d-253">The default path is `$home\Documents\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="b487d-254">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="b487d-254">This parameter is required.</span></span>

<span data-ttu-id="b487d-255">Если подкаталог модуля или любой из создаваемых файлов `Export-PSSession` уже существует, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b487d-255">If the module subdirectory or any of the files that `Export-PSSession` creates already exist, the command fails.</span></span> <span data-ttu-id="b487d-256">Чтобы перезаписать существующие файлы, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b487d-256">To overwrite existing files, use the **Force** parameter.</span></span>

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

### <span data-ttu-id="b487d-257">-Session</span><span class="sxs-lookup"><span data-stu-id="b487d-257">-Session</span></span>

<span data-ttu-id="b487d-258">Указывает сеанс PSSession, из которого экспортируются команды.</span><span class="sxs-lookup"><span data-stu-id="b487d-258">Specifies the PSSession from which the commands are exported.</span></span> <span data-ttu-id="b487d-259">Введите переменную, содержащую объект сеанса, или команду, которая получает объект сеанса, например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="b487d-259">Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="b487d-260">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="b487d-260">This parameter is required.</span></span>

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

### <span data-ttu-id="b487d-261">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b487d-261">CommonParameters</span></span>

<span data-ttu-id="b487d-262">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b487d-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b487d-263">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b487d-263">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b487d-264">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b487d-264">INPUTS</span></span>

### <span data-ttu-id="b487d-265">Нет</span><span class="sxs-lookup"><span data-stu-id="b487d-265">None</span></span>

<span data-ttu-id="b487d-266">Вы не можете передать объекты в `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="b487d-266">You cannot pipe objects to `Export-PSSession`.</span></span>

## <span data-ttu-id="b487d-267">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b487d-267">OUTPUTS</span></span>

### <span data-ttu-id="b487d-268">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="b487d-268">System.IO.FileInfo</span></span>

<span data-ttu-id="b487d-269">`Export-PSSession` Возвращает список файлов, составляющих созданный им модуль.</span><span class="sxs-lookup"><span data-stu-id="b487d-269">`Export-PSSession` returns a list of files that comprise the module that it created.</span></span>

## <span data-ttu-id="b487d-270">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b487d-270">NOTES</span></span>

<span data-ttu-id="b487d-271">`Export-PSSession` полагается на инфраструктуру удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-271">`Export-PSSession` relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="b487d-272">Для использования этого командлета компьютер должен быть настроен для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="b487d-272">To use this cmdlet, the computer must be configured for remoting.</span></span> <span data-ttu-id="b487d-273">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b487d-273">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="b487d-274">Нельзя использовать `Export-PSSession` для экспорта поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-274">You cannot use `Export-PSSession` to export a PowerShell provider.</span></span>

<span data-ttu-id="b487d-275">Экспортируемые команды выполняются неявно в сеансе PSSession, из которого они были экспортированы.</span><span class="sxs-lookup"><span data-stu-id="b487d-275">Exported commands run implicitly in the PSSession from which they were exported.</span></span> <span data-ttu-id="b487d-276">Сведения об удаленном выполнении команд полностью обрабатываются PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b487d-276">The details of running the commands remotely are handled entirely by PowerShell.</span></span> <span data-ttu-id="b487d-277">Экспортируемые команды можно выполнять так же, как и локальные.</span><span class="sxs-lookup"><span data-stu-id="b487d-277">You can run the exported commands just as you would run local commands.</span></span>

<span data-ttu-id="b487d-278">`Export-ModuleMember` захватывает и сохраняет сведения о PSSession в экспортируемом модуле.</span><span class="sxs-lookup"><span data-stu-id="b487d-278">`Export-ModuleMember` captures and saves information about the PSSession in the module that it exports.</span></span> <span data-ttu-id="b487d-279">Если сеанс PSSession, из которого экспортированы команды, закрывается при импорте модуля и отсутствуют активные PSSession на том же компьютере, команды в модуле пытаются повторно создать PSSession.</span><span class="sxs-lookup"><span data-stu-id="b487d-279">If the PSSession from which the commands were exported is closed when you import the module, and there are no active PSSessions to the same computer, the commands in the module attempt to recreate the PSSession.</span></span> <span data-ttu-id="b487d-280">Если попытка повторно создать сеанс PSSession завершится ошибкой, экспортированные команды не будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="b487d-280">If attempts to recreate the PSSession fail, the exported commands will not run.</span></span>

<span data-ttu-id="b487d-281">Сведения о сеансе, которые `Export-ModuleMember` регистрируются и сохраняются в модуле, не включают параметры сеанса, такие как указанные в `$PSSessionOption` переменной предпочтений или с помощью параметра **SessionOption** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, или.</span><span class="sxs-lookup"><span data-stu-id="b487d-281">The session information that `Export-ModuleMember` captures and saves in the module does not include session options, such as those that you specify in the `$PSSessionOption` preference variable or by using the **SessionOption** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span> <span data-ttu-id="b487d-282">Если при импорте модуля исходный сеанс PSSession закрыт, модуль будет использовать другой сеанс PSSession на том же компьютере, если такой доступен.</span><span class="sxs-lookup"><span data-stu-id="b487d-282">If the original PSSession is closed when you import the module, the module will use another PSSession to the same computer, if one is available.</span></span> <span data-ttu-id="b487d-283">Чтобы импортированные команды могли выполняться в правильно настроенном сеансе, создайте сеанс PSSession с нужными параметрами перед импортом модуля.</span><span class="sxs-lookup"><span data-stu-id="b487d-283">To enable the imported commands to run in a correctly configured session, create a PSSession with the options that you want before you import the module.</span></span>

<span data-ttu-id="b487d-284">Чтобы найти команды для экспорта, `Export-PSSession` использует `Invoke-Command` командлет для выполнения `Get-Command` команды в PSSession.</span><span class="sxs-lookup"><span data-stu-id="b487d-284">To find the commands to export, `Export-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="b487d-285">Чтобы получить и сохранить данные форматирования для команд, используются `Get-FormatData` `Export-FormatData` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="b487d-285">To get and save formatting data for the commands, it uses the `Get-FormatData` and `Export-FormatData` cmdlets.</span></span> <span data-ttu-id="b487d-286">При выполнении команды могут отображаться сообщения об ошибках `Invoke-Command` , `Get-Command` , `Get-FormatData` и `Export-FormatData` `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="b487d-286">You might see error messages from `Invoke-Command`, `Get-Command`, `Get-FormatData`, and `Export-FormatData` when you run an `Export-PSSession` command.</span></span> <span data-ttu-id="b487d-287">Кроме того, `Export-PSSession` не может экспортировать команды из сеанса, не включающего `Get-Command` `Get-FormatData` командлеты,, `Select-Object` и `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="b487d-287">Also, `Export-PSSession` cannot export commands from a session that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>

<span data-ttu-id="b487d-288">`Export-PSSession``Write-Progress`отображает ход выполнения команды с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="b487d-288">`Export-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="b487d-289">Во время выполнения команды может отображаться индикатор выполнения .</span><span class="sxs-lookup"><span data-stu-id="b487d-289">You might see the progress bar while the command is running.</span></span>

<span data-ttu-id="b487d-290">К экспортированным командам применяются те же ограничения, что и к другим удаленным командам, включая невозможность запустить программу с пользовательским интерфейсом, например Блокнот.</span><span class="sxs-lookup"><span data-stu-id="b487d-290">Exported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>

<span data-ttu-id="b487d-291">Так как профили PowerShell не выполняются в PSSession, команды, которые профиль добавляет в сеанс, недоступны `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="b487d-291">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Export-PSSession`.</span></span> <span data-ttu-id="b487d-292">Чтобы экспортировать команды из профиля, используйте `Invoke-Command` команду для запуска профиля в сеансе PSSession вручную перед экспортом команд.</span><span class="sxs-lookup"><span data-stu-id="b487d-292">To export commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before exporting commands.</span></span>

<span data-ttu-id="b487d-293">`Export-PSSession`Создаваемый модуль может включать файл форматирования, даже если команда не импортирует данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="b487d-293">The module that `Export-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="b487d-294">Если команда не импортирует данные форматирования, все создаваемые файлы форматирования не будут содержать данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="b487d-294">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>

## <span data-ttu-id="b487d-295">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b487d-295">RELATED LINKS</span></span>

[<span data-ttu-id="b487d-296">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="b487d-296">about_Command_Precedence</span></span>](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[<span data-ttu-id="b487d-297">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="b487d-297">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="b487d-298">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="b487d-298">about_PSSnapins</span></span>](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)

[<span data-ttu-id="b487d-299">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="b487d-299">about_Remote_Requirements</span></span>](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[<span data-ttu-id="b487d-300">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b487d-300">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="b487d-301">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="b487d-301">Import-PSSession</span></span>](Import-PSSession.md)

[<span data-ttu-id="b487d-302">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b487d-302">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="b487d-303">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="b487d-303">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="b487d-304">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="b487d-304">New-PSSessionOption</span></span>](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[<span data-ttu-id="b487d-305">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="b487d-305">Remove-PSSession</span></span>](../Microsoft.PowerShell.Core/Remove-PSSession.md)
