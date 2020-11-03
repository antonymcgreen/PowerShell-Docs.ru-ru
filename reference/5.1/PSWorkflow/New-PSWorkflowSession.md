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
# New-PSWorkflowSession

## Краткий обзор
Создает сеанс рабочего процесса.

## SYNTAX

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## DESCRIPTION

`New-PSWorkflowSession`Командлет создает управляемый пользователем сеанс ( **PSSession** ), который специально предназначен для запуска рабочих процессов Windows PowerShell. Он использует конфигурацию сеанса Microsoft.PowerShell.Workflow, которая включает в себя сценарии, файлы типов и форматирования, а также параметры, необходимые для рабочих процессов.

Можно использовать `New-PSWorkflowSession` или его псевдоним, `nwsn` .

В эту команду также можно добавить общие параметры рабочих процессов. Дополнительные сведения о общих параметрах рабочего процесса см. в разделе [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Создание сеанса рабочего процесса на удаленном компьютере

В этом примере создается сеанс **воркфловтестс** на удаленном компьютере ServerNode01.

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

Значение параметра **SessionOption** — это `New-PSSessionOption` команда, которая устанавливает режим буферизации вывода в сеансе для **удаления** .

### Пример 2. Создание сеансов рабочих процессов на нескольких удаленных компьютерах

В этом примере создаются сеансы рабочего процесса на компьютерах ServerNode01 и Server12. Команда использует параметр **Credential** для выполнения с правами администратора домена.

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

Команда использует параметр **ThrottleLimit** , чтобы увеличить предел регулирования для отдельной команды до 150.
Это значение имеет приоритет над ограничением регулирования по умолчанию 100, установленным в конфигурации сеанса **Microsoft. PowerShell. Workflow** .

## PARAMETERS

### -ApplicationName

Определяет сегмент имени приложения в URI соединения.

Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере. Если привилегированная переменная не определена, значение по умолчанию — WSMAN. Это значение подходит для большинства случаев Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.
Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.

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

### -Authentication

Указывает механизм, используемый для проверки подлинности учетных данных пользователя.
Допустимые значения для этого параметра:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Значение по умолчанию — Default.

Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

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

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить отпечаток сертификата, используйте `Get-Item` командлет или `Get-ChildItem` командлет на диске Windows PowerShell CERT:.

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

### -ComputerName

Создает постоянное подключение ( **PSSession** ) к указанному компьютеру. При вводе нескольких имен компьютеров Windows PowerShell создает несколько **PSSession** , по одному на каждый компьютер. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.). Если компьютер находится в другом домене, отличном от домена пользователя, полное доменное имя является обязательным. Также можно передать имя компьютера в кавычках в `New-PSWorkflowSession` .

Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** . Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере. Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

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

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь. Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com , или введите объект **PSCredential** , например, возвращаемый `Get-Credential` командлетом.

При вводе имени пользователя этот командлет запрашивает пароль.

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

### -EnableNetworkAccess

Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя. Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров. Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.

Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере. Чтобы создать сеанс замыкания на себя, не указывайте параметр **ComputerName** или задайте для него значение Dot, localhost или имя локального компьютера.

По умолчанию создаются сеансы замыкания на себя, имеющие токен сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.

Параметр **EnableNetworkAccess** действует только в петлевых сеансах. Если при создании сеанса на удаленном компьютере указать параметр **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.

Удаленный доступ в петлевом сеансе также можно разрешить с помощью значения **CredSSP** параметра **Authentication** , который делегирует учетные данные сеанса на другие компьютеры.

Для защиты компьютера от вредоносного доступа отключенные сеансы замыкания на себя с интерактивными маркерами, созданные с помощью параметра **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс. Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров. Дополнительную информацию см. в описании командлета `Disconnect-PSSession`.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Name

Задает понятное имя для сеанса рабочего процесса. Имя можно использовать с другими командлетами, такими как `Get-PSSession` и `Enter-PSSession` . Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.

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

### -Port

Задает сетевой порт на удаленном компьютере, используемый для данного соединения. Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением. Порты по умолчанию: 5985 (порт WinRM для HTTP) и 5986 (порт WinRM для HTTPS).

Прежде чем использовать другой порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта. Для настройки прослушивателя используйте следующие команды:

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Не используйте параметр **Port** , если этого можно избежать. Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

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

### -SessionOption

Задает дополнительные параметры для сеанса. Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета.

Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано. В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.

Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса. Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса. Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).

Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .
Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

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

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Если опустить этот параметр или ввести значение 0 (ноль), используется значение по умолчанию для конфигурации сеанса **Microsoft. повершеллворкфлов** , 100.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

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

### -UseSSL

Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером. По умолчанию SSL не используется.

Протокол WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети. Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.

Если указать этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.Runspaces.PSSession[], System.String

В этот командлет можно передать по конвейеру сеанс или имя компьютера.

## Выходные данные

### System.Management.Automation.Runspaces.PSSession

## ПРИМЕЧАНИЯ

`New-PSWorkflowSession`Команда эквивалентна следующей команде:

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## Связанные ссылки

[Disconnect-PSSession](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSTransportOption](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[Register-PSSessionConfiguration](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
