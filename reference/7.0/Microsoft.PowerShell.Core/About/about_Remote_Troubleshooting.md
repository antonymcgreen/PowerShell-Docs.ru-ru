---
description: Описывает устранение неполадок удаленных операций в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Сведения об удаленной диагностике
ms.openlocfilehash: acf4f86d8c20f5a8059be48623255696afabbefb
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "93233309"
---
# <a name="about-remote-troubleshooting"></a>Об устранении неполадок удаленного поиска

## <a name="short-description"></a>Краткое описание
Описывает устранение неполадок удаленных операций в PowerShell.

## <a name="long-description"></a>Подробное описание

В этом разделе описываются некоторые проблемы, которые могут возникнуть при использовании функций удаленного взаимодействия PowerShell, основанных на технологии WS-Management и предлагающих решения этих проблем.

Прежде чем использовать удаленное взаимодействие PowerShell, ознакомьтесь со статьей [about_Remote](about_remote.md) и [about_Remote_Requirements](about_Remote_Requirements.md) , где приведены рекомендации по настройке и базовому использованию. Кроме того, разделы справки по каждому из командлетов удаленного взаимодействия, в особенности описания параметров, содержат полезную информацию, которая поможет избежать проблем.

> [!NOTE]
> Чтобы просмотреть или изменить параметры локального компьютера на диске WSMan:, включая изменения в конфигурациях сеансов, доверенных узлах, портах или прослушивателях, запустите PowerShell с параметром **Запуск от имени администратора** .

## <a name="troubleshooting-permission-and-authentication-issues"></a>Устранение неполадок разрешений и проверки подлинности

В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с разрешениями пользователя и компьютера и требованиями удаленного взаимодействия.

### <a name="how-to-run-as-administrator"></a>Запуск от имени администратора

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

Чтобы запустить удаленный сеанс на локальном компьютере или просмотреть или изменить параметры для локального компьютера на диске WSMan:, включая изменения в конфигурациях сеансов, доверенных узлах, портах или прослушивателях, запустите Windows PowerShell с параметром **Запуск от имени администратора** .

Чтобы запустить Windows PowerShell с параметром **Запуск от имени администратора** , выполните следующие действия.

- Щелкните правой кнопкой мыши значок Windows PowerShell (интегрированная среда сценариев Windows PowerShell) и выберите команду **Запуск от имени администратора**.

  Для запуска Windows PowerShell с параметром **Запуск от имени администратора** в Windows 7 и windows Server 2008 R2.

- На панели задач Windows щелкните правой кнопкой мыши значок Windows PowerShell и выберите команду **Запуск от имени администратора**.

  В Windows Server 2008 R2 значок Windows PowerShell закреплен на панели задач по умолчанию.

### <a name="how-to-enable-remoting"></a>Как включить удаленное взаимодействие

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

Для включения отправки удаленных команд на компьютере не требуется настраивать конфигурацию.
Однако для получения удаленных команд на компьютере должна быть включена служба удаленного взаимодействия PowerShell. Включение включает запуск службы WinRM, задание для типа запуска службы WinRM значения автоматически, создание прослушивателей для соединений HTTP и HTTPS и создание конфигураций сеансов по умолчанию.

Удаленное взаимодействие Windows PowerShell включено в Windows Server 2012 и более новых выпусках Windows Server по умолчанию. Во всех остальных системах выполните командлет, `Enable-PSRemoting` чтобы включить удаленное взаимодействие. Можно также выполнить командлет, `Enable-PSRemoting` чтобы повторно включить удаленное взаимодействие на Windows server 2012 и более поздних выпусках Windows Server, если удаленное взаимодействие отключено.

Чтобы настроить компьютер для получения удаленных команд, используйте `Enable-PSRemoting` командлет. Следующая команда включает все необходимые удаленные параметры, включает конфигурации сеанса и перезапускает службу WinRM, чтобы изменения были эффективными.

`Enable-PSRemoting`

Чтобы отключить все запросы пользователя, введите:

`Enable-PSRemoting -Force`

Дополнительные сведения см. в разделе [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).

### <a name="how-to-enable-remoting-in-an-enterprise"></a>Как включить удаленное взаимодействие на предприятии

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Чтобы разрешить одному компьютеру получать удаленные команды PowerShell и принимать подключения, используйте `Enable-PSRemoting` командлет.

Чтобы включить удаленное взаимодействие для нескольких компьютеров в Организации, можно использовать следующие масштабируемые параметры.

- Чтобы настроить прослушиватели для удаленного взаимодействия, включите групповую политику **Разрешить автоматическую настройку прослушивателей** .

- Чтобы задать автоматический тип запуска служба удаленного управления Windows (WinRM) на нескольких компьютерах, используйте `Set-Service` командлет.

- Чтобы включить исключение брандмауэра, воспользуйтесь групповой политикой **Брандмауэр Windows: разрешить исключения локальных портов** .

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a>Включение прослушивателей с помощью групповой политики

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Чтобы настроить прослушиватели для всех компьютеров в домене, включите политику **Разрешить автоматическую настройку прослушивателей** в следующем групповая политика пути:

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

Включите политику и укажите фильтры IPv4 и IPv6. Допускаются подстановочные знаки ( `*` ).

### <a name="how-to-enable-remoting-on-public-networks"></a>Включение удаленного взаимодействия в общедоступных сетях

```
ERROR:  Unable to check the status of the firewall
```

`Enable-PSRemoting`Командлет возвращает эту ошибку, если локальная сеть является общедоступной, а параметр **SkipNetworkProfileCheck** не используется в команде.

В серверных версиях Windows работает `Enable-PSRemoting` на всех типах сетевых расположений. Он создает правила брандмауэра, разрешающие удаленный доступ к частным и доменным (домашним и рабочим) сетям. Для общедоступных сетей он создает правила брандмауэра, разрешающие удаленный доступ из той же локальной подсети.

В клиентских версиях Windows работает `Enable-PSRemoting` в частных и доменных сетях. По умолчанию он завершается сбоем в общедоступных сетях, но если вы используете параметр **SkipNetworkProfileCheck** , то `Enable-PSRemoting` завершается и создается правило брандмауэра, разрешающее трафик из той же локальной подсети.

Чтобы удалить ограничение локальной подсети в общедоступных сетях и разрешить удаленный доступ из любого расположения, выполните следующую команду:

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

`Set-NetFirewallRule`Командлет экспортируется модулем NetSecurity.

> [!NOTE]
> В Windows PowerShell 2,0 на компьютерах под управлением серверных версий Windows `Enable-PSRemoting` создаются правила брандмауэра, обеспечивающие удаленный доступ к частным, доменным и общедоступным сетям. На компьютерах с клиентскими версиями Windows `Enable-PSRemoting` создает правила брандмауэра, разрешающие удаленный доступ только в частных и доменных сетях.

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a>Как включить исключение брандмауэра с помощью групповой политики

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Чтобы включить исключение брандмауэра на всех компьютерах в домене, включите политику **брандмауэра Windows: разрешить исключения локальных портов** в следующем групповая политика пути:

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

Эта политика позволяет членам группы администраторов на компьютере использовать **Брандмауэр Windows** на **панели управления** для создания исключения брандмауэра для службы Служба удаленного управления Windows.

Если конфигурация политики неверна, может появиться следующее сообщение об ошибке:

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

Ошибка конфигурации в политике приводит к пустому значению свойства **листенингон** . Для проверки значения используйте следующую команду.

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a>Как задать тип запуска службы WinRM

```
ERROR:  ACCESS IS DENIED
```

Удаленное взаимодействие PowerShell зависит от службы служба удаленного управления Windows (WinRM).
Служба должна быть запущена для поддержки удаленных команд.

В серверных версиях Windows тип запуска службы служба удаленного управления Windows (WinRM) — автоматически.

Однако в клиентских версиях Windows служба WinRM по умолчанию отключена.

Чтобы задать тип запуска службы на удаленном компьютере, используйте `Set-Service` командлет.

Чтобы выполнить команду на нескольких компьютерах, можно создать текстовый файл или CSV-файл с именами компьютеров.

Например, следующие команды получают список имен компьютеров из `Servers.txt` файла, а затем задает для всех компьютеров **Автоматический** тип запуска службы WinRM.

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

Чтобы просмотреть результаты, используйте `Get-WMIObject` командлет с объектом **Win32_Service** . Дополнительные сведения см. в разделе [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).

### <a name="how-to-recreate-the-default-session-configurations"></a>Повторное создание конфигураций сеансов по умолчанию

```
ERROR:  ACCESS IS DENIED
```

Чтобы подключиться к локальному компьютеру и выполнить команды удаленно, локальный компьютер должен включать конфигурации сеанса для удаленных команд.

При использовании `Enable-PSRemoting` он создает конфигурации сеансов по умолчанию на локальном компьютере. Удаленные пользователи используют эти конфигурации сеанса каждый раз, когда удаленная команда не включает параметр **configurationName** .

Если конфигурации по умолчанию на компьютере не зарегистрированы или удалены, используйте `Enable-PSRemoting` командлет для их повторного создания. Этот командлет можно использовать многократно. Если функция уже настроена, она не создает ошибок.

При изменении конфигураций сеансов по умолчанию и необходимости восстановления исходных конфигураций сеансов по умолчанию используйте `Unregister-PSSessionConfiguration` командлет для удаления измененных конфигураций сеанса, а затем используйте `Enable-PSRemoting` командлет для их восстановления.
`Enable-PSRemoting` не изменяет существующие конфигурации сеанса.

> [!NOTE]
> При `Enable-PSRemoting` восстановлении конфигурации сеанса по умолчанию не создаются явные дескрипторы безопасности для конфигураций. Вместо этого конфигурации наследуют дескриптор безопасности Рутсддл, который является безопасным по умолчанию.

Чтобы просмотреть дескриптор безопасности Рутсддл, введите:

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

Чтобы изменить Рутсддл, используйте `Set-Item` командлет на диске WSMan:. Чтобы изменить дескриптор безопасности конфигурации сеанса, используйте `Set-PSSessionConfiguration` командлет с параметрами **SecurityDescriptorSDDL** или **ShowSecurityDescriptorUI** .

Дополнительные сведения о диске WSMan: см. в разделе справки по поставщику WSMan ("Get-Help WSMAN").

### <a name="how-to-provide-administrator-credentials"></a>Как указать учетные данные администратора

```
ERROR:  ACCESS IS DENIED
```

Чтобы создать сеанс PSSession или выполнить команды на удаленном компьютере, по умолчанию текущий пользователь должен быть членом группы администраторов на удаленном компьютере. Учетные данные иногда требуются даже при входе текущего пользователя в учетную запись, которая является членом группы "Администраторы".

Если текущий пользователь является членом группы "Администраторы" на удаленном компьютере или может предоставить учетные данные члена группы "Администраторы", используйте параметр **Credential** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлета или, чтобы подключиться удаленно.

Например, следующая команда предоставляет учетные данные администратора.

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

Дополнительные сведения о параметре **Credential** см. в разделе [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) или [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).

### <a name="how-to-enable-remoting-for-non-administrative-users"></a>Включение удаленного взаимодействия для пользователей, не являющихся администраторами

```
ERROR:  ACCESS IS DENIED
```

Чтобы установить PSSession или выполнить команду на удаленном компьютере, пользователь должен иметь разрешение на использование конфигураций сеансов на удаленном компьютере.

По умолчанию разрешения на использование конфигураций сеансов по умолчанию имеют только члены группы «Администраторы» на компьютере. Таким образом, только члены группы «Администраторы» могут подключаться к компьютеру удаленно.

Чтобы разрешить другим пользователям подключаться к локальному компьютеру, предоставьте пользователю разрешения на выполнение конфигураций сеансов по умолчанию на локальном компьютере.

Следующая команда открывает страницу свойств, которая позволяет изменить дескриптор безопасности конфигурации сеанса Microsoft. PowerShell по умолчанию на локальном компьютере.

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

Дополнительные сведения см. в разделе [about_Session_Configurations](about_Session_Configurations.md).

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a>Включение удаленного взаимодействия для администраторов в других доменах

```
ERROR:  ACCESS IS DENIED
```

Если пользователь в другом домене входит в группу администраторов на локальном компьютере, он не может удаленно подключиться к локальному компьютеру с правами администратора. По умолчанию удаленные подключения из других доменов выполняются только с маркерами прав обычного пользователя.

Однако можно использовать запись реестра **LocalAccountTokenFilterPolicy** , чтобы изменить поведение по умолчанию и разрешить удаленным пользователям, которые являются членами группы "Администраторы", работать с правами администратора.

> [!CAUTION]
> Запись **LocalAccountTokenFilterPolicy** отключает удаленные ограничения контроля учетных записей (UAC) для всех пользователей всех затронутых компьютеров. Прежде чем изменять политику, внимательно изучите последствия этого параметра.

Чтобы изменить политику, используйте следующую команду, чтобы присвоить параметру реестра **LocalAccountTokenFilterPolicy** значение 1.

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a>Использование IP-адреса в удаленной команде

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

Параметр **ComputerName** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, и принимает IP-адрес как допустимое значение. Однако так как проверка подлинности Kerberos не поддерживает IP-адреса, проверка подлинности NTLM используется по умолчанию при указании IP-адреса.

При использовании проверки подлинности NTLM для удаленного взаимодействия требуется следующая процедура.

1. Настройте компьютер для транспорта HTTPS или добавьте IP-адреса удаленных компьютеров в список TrustedHosts на локальном компьютере.

1. Используйте параметр **Credential** во всех удаленных командах.

   Это необходимо даже при отправке учетных данных текущего пользователя.

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a>Удаленное подключение с компьютера, созданного в Рабочей группе

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

Если локальный компьютер не входит в домен, для удаленного взаимодействия требуется следующая процедура.

1. Настройте компьютер для транспорта HTTPS или добавьте имена удаленных компьютеров в список TrustedHosts на локальном компьютере.

1. Убедитесь, что пароль установлен на компьютере рабочей группы. Если пароль не задан или значение пароля пусто, то нельзя выполнять удаленные команды.

   Чтобы задать пароль для учетной записи пользователя, используйте учетные записи пользователей в панели управления.

1. Используйте параметр **Credential** во всех удаленных командах.

   Это необходимо даже при отправке учетных данных текущего пользователя.

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a>Добавление компьютера в список надежных узлов

Элемент TrustedHosts может содержать разделенный запятыми список имен компьютеров, IP-адресов и полных доменных имен. Разрешено использовать подстановочные знаки.

Чтобы просмотреть или изменить список надежных узлов, используйте диск WSMan:. Элемент Трустедхост находится в `WSMan:\localhost\Client` узле.

Только члены группы "Администраторы" на компьютере имеют разрешение на изменение списка доверенных узлов на компьютере.

Внимание! значение, заданное для элемента TrustedHosts, влияет на всех пользователей компьютера.

Чтобы просмотреть список доверенных узлов, используйте следующую команду:

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

Можно также использовать `Set-Location` командлет (Alias = CD) для перемещения по адресу WSMan: Drive в расположение. Пример:

```powershell
cd WSMan:\localhost\Client; dir
```

Чтобы добавить все компьютеры в список доверенных узлов, используйте следующую команду, которая помещает в ComputerName значение * (ALL).

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

Можно также использовать подстановочный знак ( `*` ) для добавления всех компьютеров в определенном домене в список доверенных узлов. Например, следующая команда добавляет все компьютеры из домена Fabrikam в список доверенных узлов.

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

Чтобы добавить имена определенных компьютеров в список доверенных узлов, используйте следующий формат команды:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

где каждое значение `<ComputerName>` должно иметь следующий формат:

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

Пример:

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

Чтобы добавить имя компьютера в существующий список доверенных узлов, сначала сохраните текущее значение в переменной, а затем задайте в качестве значения список с разделителями-запятыми, включающий текущие и новые значения.

Например, чтобы добавить компьютер Server01 в существующий список доверенных узлов, используйте следующую команду:

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

Чтобы добавить IP-адреса определенных компьютеров в список доверенных узлов, используйте следующий формат команды:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

Пример:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

Чтобы добавить компьютер в список TrustedHosts на удаленном компьютере, используйте `Connect-WSMan` командлет, чтобы добавить узел для удаленного компьютера на диск WSMan: на локальном компьютере. Затем используйте `Set-Item` команду, чтобы добавить компьютер.

Дополнительные сведения о `Connect-WSMan` командлете см. в разделе [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).

## <a name="troubleshooting-computer-configuration-issues"></a>Устранение проблем с конфигурацией компьютера

В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с определенными конфигурациями компьютера, домена или предприятия.

### <a name="how-to-configure-remoting-on-alternate-ports"></a>Настройка удаленного взаимодействия на альтернативных портах

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Удаленное взаимодействие PowerShell по умолчанию использует порт 80 для транспорта HTTP. Порт по умолчанию используется каждый раз, когда пользователь не задает параметры **ConnectionURI** или **Port** в удаленной команде.

Чтобы изменить порт по умолчанию, используемый PowerShell, используйте `Set-Item` командлет на диске WSMan:, чтобы изменить значение порта на конечном узле прослушивателя.

Например, следующая команда изменяет порт по умолчанию на 8080.

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a>Настройка удаленного взаимодействия с помощью прокси-сервера

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

Поскольку удаленное взаимодействие PowerShell использует протокол HTTP, на него влияют параметры HTTP-прокси. В организациях, имеющих прокси-серверы, пользователи не могут напрямую получить доступ к удаленному компьютеру PowerShell.

Чтобы устранить эту проблему, используйте параметры настройки прокси-сервера в удаленной команде. Доступны следующие параметры.

- проксякцесстипе
- проксяусентикатион
- ProxyCredential

Чтобы задать эти параметры для определенной команды, выполните следующую процедуру.

1. Используйте параметры **проксякцесстипе** , **проксяусентикатион** и **ProxyCredential** `New-PSSessionOption` командлета, чтобы создать объект параметров сеанса с параметрами прокси-сервера для вашей организации. Сохраните объект параметра — это переменная.

1. Используйте переменную, содержащую объект Option, в качестве значения параметра **SessionOption** `New-PSSession` `Enter-PSSession` команды, или `Invoke-Command` .

Например, следующая команда создает объект параметра сеанса с параметрами сеанса прокси-сервера, а затем использует объект для создания удаленного сеанса.

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

Чтобы задать эти параметры для всех удаленных команд в текущем сеансе, используйте объект параметра, который `New-PSSessionOption` создает в значении `$PSSessionOption` переменной предпочтений. Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).

Чтобы задать эти параметры для всех удаленных команд, всех сеансов PowerShell на локальном компьютере, добавьте `$PSSessionOption` переменную предпочтений в профиль PowerShell. Дополнительные сведения о профилях PowerShell см. в разделе [about_Profiles](about_Profiles.md).

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a>Обнаружение 32-разрядного сеанса на 64-разрядном компьютере

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Если удаленный компьютер работает под управлением 64-разрядной версии Windows, а удаленная команда использует конфигурацию с 32-битным сеансом, например Microsoft. PowerShell32, служба удаленного управления Windows (WinRM) загружает процесс WOW64 и Windows автоматически перенаправляет все ссылки на `$env:Windir\System32` каталог в `$env:Windir\SysWOW64` каталог.

В результате, если вы попытаетесь использовать в каталоге System32 средства, не имеющие аналога в каталоге SysWow64, например `Defrag.exe` , эти средства не найдены в каталоге.

Чтобы найти архитектуру процессора, используемую в сеансе, используйте значение переменной среды **PROCESSOR_ARCHITECTURE** . Следующая команда находит архитектуру процессора для сеанса в `$s` переменной.

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).

## <a name="troubleshooting-policy-and-preference-issues"></a>Устранение проблем политики и предпочтений

В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с политиками и предпочтениями, заданными на локальном и удаленном компьютерах.

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a>Изменение политики выполнения для Import-PSSession и Import-Module

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

`Import-PSSession` `Export-PSSession` Командлеты и создают модули, которые содержат неподписанные файлы скриптов и файлы форматирования.

Чтобы импортировать модули, созданные этими командлетами, с помощью `Import-PSSession` или `Import-Module` , политика выполнения в текущем сеансе не может быть ограничена или AllSigned. Дополнительные сведения о политиках выполнения PowerShell см. в разделе [about_Execution_Policies](about_Execution_Policies.md).

Чтобы импортировать модули без изменения политики выполнения для локального компьютера, установленного в реестре, используйте параметр **Scope** параметра, `Set-ExecutionPolicy` чтобы задать менее ограниченную политику выполнения для одного процесса.

Например, следующая команда запускает процесс с `RemoteSigned` политикой выполнения. Изменение политики выполнения влияет только на текущий процесс и не изменяет параметр реестра PowerShell **ExecutionPolicy** .

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

Кроме того, с помощью параметра **ExecutionPolicy** можно `PowerShell.exe` запустить один сеанс с менее ограниченной политикой выполнения.

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

Дополнительные сведения о политиках выполнения см. в разделе [about_Execution_Policies](about_Execution_Policies.md). Для получения дополнительных сведений введите `PowerShell.exe -?`.

### <a name="how-to-set-and-change-quotas"></a>Как задать и изменить квоты

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

Квоты можно использовать для защиты локального компьютера и удаленного компьютера от чрезмерного использования ресурсов, как случайных, так и вредоносных.

В базовой конфигурации доступны следующие квоты.

- Поставщик WSMan (WSMan:) предоставляет несколько параметров квот, таких как параметры **максенвелопесизекб** и **макспровидеррекуестс** в узле, `WSMan:<ComputerName>` а также параметры **максконкуррентоператионс** , **свойств maxconcurrentoperationsperuser** и **MaxConnections** в `WSMan:<ComputerName>\Service` узле.

- Защитить локальный компьютер можно с помощью параметров **максимумрецеиведдатасизеперкомманд** и **максимумрецеиведобжектсизе** `New-PSSessionOption` командлета и `$PSSessionOption` переменной предпочтений.

- Защитить удаленный компьютер можно, добавив ограничения в конфигурации сеанса, например с помощью параметров **максимумрецеиведдатасизеперкоммандмб** и **максимумрецеиведобжектсиземб** `Register-PSSessionConfiguration` командлета.

При конфликте квот с помощью команды PowerShell создает ошибку.

Чтобы устранить эту ошибку, измените удаленную команду так, чтобы она соответствовала квоте. Или определите источник квоты, а затем увеличьте квоту, чтобы завершить выполнение команды.

Например, следующая команда увеличивает квоту размера объекта в конфигурации сеанса Microsoft. PowerShell на удаленном компьютере с 10 МБ (значение по умолчанию) до 11 МБ.

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе `New-PSSessionOption` .

Дополнительные сведения о WS-Management квотах см. в разделе [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).

### <a name="how-to-resolve-timeout-errors"></a>Устранение ошибок времени ожидания

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

Можно использовать время ожидания для защиты локального компьютера и удаленного компьютера от чрезмерного использования ресурсов, как случайных, так и вредоносных. Если время ожидания задано как на локальном, так и на удаленном компьютере, PowerShell использует самые короткие параметры времени ожидания.

В базовой конфигурации доступны следующие тайм-ауты.

- Поставщик WSMan (WSMan:) предоставляет несколько параметров времени ожидания на стороне клиента и службы, например параметр **макстимеаутмс** в `WSMan:<ComputerName>` узле и параметры **енумератионтимеаутмс** и **макспаккетретриевалтимесекондс** в `WSMan:<ComputerName>\Service` узле.

- Защитить локальный компьютер можно с помощью параметров **канцелтимеаут** , **IdleTimeout** , **OpenTimeout** и **OperationTimeout** `New-PSSessionOption` командлета и `$PSSessionOption` переменной предпочтений.

- Кроме того, можно защитить удаленный компьютер, задавая значения времени ожидания программным способом в конфигурации сеанса для сеанса.

Если значение времени ожидания не позволяет завершить операцию, PowerShell завершает операцию и создает ошибку.

Чтобы устранить эту ошибку, измените команду для завершения в течение интервала времени ожидания или определите источник предельного времени ожидания и Увеличьте интервал времени ожидания, чтобы завершить выполнение команды.

Например, следующие команды используют `New-PSSessionOption` командлет для создания объекта параметра сеанса со значением **OperationTimeout** , равным 4 минутам (в мс), а затем используйте объект параметра сеанса для создания удаленного сеанса.

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

Дополнительные сведения об истечении времени ожидания WS-Management см. в разделе справки по поставщику WSMan (тип `Get-Help WSMan` ).

Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

## <a name="troubleshooting-unresponsive-behavior"></a>Устранение неполадок при неотвечающем взаимодействиях

В этом разделе обсуждаются проблемы удаленного взаимодействия, препятствующие выполнению команды и предотвращению или задержке возврата командной строки PowerShell.

### <a name="how-to-interrupt-a-command"></a>Прерывание команды

Некоторые программы Windows, такие как программы с пользовательским интерфейсом, консольные приложения, запрашивающие ввод, и консольные приложения, использующие API консоли Win32, не работают должным образом на удаленном узле PowerShell.

При использовании этих программ может возникнуть непредвиденное поведение, например отсутствие выходных данных, частичный вывод или удаленная команда, которая не завершена.

Чтобы завершить работу программы, не отвечающей, введите <kbd>CTRL</kbd> + <kbd>C</kbd>. Чтобы просмотреть сообщения об ошибках, которые могли быть получены, введите `$error` локальный узел и удаленный сеанс.

## <a name="how-to-recover-from-an-operation-failure"></a>Восстановление после сбоя операции

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

Эта ошибка возвращается в случае завершения операции до ее завершения.
Как правило, это происходит, когда служба WinRM останавливается или перезапускается во время выполнения других операций WinRM.

Чтобы устранить эту проблему, убедитесь, что служба WinRM запущена, и повторите команду.

1. Запустите PowerShell с параметром **Запуск от имени администратора** .
1. Выполните следующую команду:

   `Start-Service WinRM`

1. Повторно выполните команду, вызвавшую ошибку.

## <a name="linux-and-macos-limitations"></a>Ограничения Linux и macOS

### <a name="authentication"></a>Аутентификация

В macOS работает только обычная проверка подлинности, и попытка использовать другие схемы проверки подлинности может привести к сбою процесса.

Ознакомьтесь с инструкциями по [проверке подлинности OMI](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .

## <a name="see-also"></a>СМ. ТАКЖЕ

[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

[about_Remote](about_Remote.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[about_Remote_Variables](about_Remote_Variables.md)
