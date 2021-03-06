---
description: Описание требований к системе и требований к конфигурации для выполнения удаленных команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: 63971aeaa92eb10a745f2a02e0c7cf00dbf65d8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232298"
---
# <a name="about-remote-requirements"></a>Сведения о удаленных требованиях

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описание требований к системе и требований к конфигурации для выполнения удаленных команд в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

В этом разделе описываются требования к системе, требования пользователей и требования к ресурсам для установки удаленных подключений и выполнения удаленных команд в PowerShell. В нем также приводятся инструкции по настройке удаленных операций.

Примечание. многие командлеты (включая командлеты Get-Service, Get-Process, Get-WMIObject, Get-EventLog и Get-WinEvent) получают объекты с удаленных компьютеров с помощью методов Microsoft .NET Framework для получения объектов. Они не используют инфраструктуру удаленного взаимодействия PowerShell. Требования, описанные в этом документе, не применяются к этим командлетам.

Чтобы найти командлеты, имеющие параметр ComputerName, но не использующие удаленное взаимодействие Windows PowerShell, прочитайте описание параметра ComputerName командлетов.

## <a name="system-requirements"></a>ТРЕБОВАНИЯ К СИСТЕМЕ

Для запуска удаленных сеансов в Windows PowerShell 3,0 на локальном и удаленном компьютерах должны быть выполнены следующие действия.

- Windows PowerShell 3,0 или более поздней версии
- Microsoft .NET Framework 4 или более поздней версии
- Служба удаленного управления Windows 3,0

Для запуска удаленных сеансов в Windows PowerShell 2,0 на локальном и удаленном компьютерах должны быть выполнены следующие действия.

- Windows PowerShell 2,0 или более поздней версии
- Microsoft .NET Framework 2,0 или более поздней версии
- Служба удаленного управления Windows 2,0

Можно создавать удаленные сеансы между компьютерами, на которых выполняется Windows PowerShell 2,0 и Windows PowerShell 3,0. Однако функции, которые выполняются только в Windows PowerShell 3,0, такие как возможность отключения и повторного подключения к сеансам, доступны только в том случае, если оба компьютера работают под управлением Windows PowerShell 3,0.

Чтобы узнать номер версии установленной версии PowerShell, используйте автоматическую переменную $PSVersionTable.

Служба удаленного управления Windows (WinRM) 3,0 и Microsoft .NET Framework 4 включены в Windows 8, Windows Server 2012 и более новые выпуски операционной системы Windows. WinRM 3,0 входит в комплект Windows Management Framework 3,0 для старых операционных систем. Если на компьютере не установлена требуемая версия WinRM или платформа Microsoft .NET, установка завершается сбоем.

## <a name="user-permissions"></a>РАЗРЕШЕНИЯ ПОЛЬЗОВАТЕЛЯ

Для создания удаленных сеансов и выполнения удаленных команд по умолчанию текущий пользователь должен быть членом группы "Администраторы" на удаленном компьютере или предоставлять учетные данные администратора. В противном случае произойдет сбой команды.

Разрешения, необходимые для создания сеансов и выполнения команд на удаленном компьютере (или в удаленном сеансе на локальном компьютере), устанавливаются конфигурацией сеанса (также называемой конечной точкой) на удаленном компьютере, к которому подключается сеанс. В частности, дескриптор безопасности в конфигурации сеанса определяет, кто имеет доступ к конфигурации сеанса и кто может использовать его для подключения.

Дескрипторы безопасности в конфигурациях сеансов по умолчанию, Microsoft. PowerShell, Microsoft. PowerShell32 и Microsoft. PowerShell. Workflow, разрешают доступ только членам группы администраторов.

Если у текущего пользователя нет разрешения на использование конфигурации сеанса, команда для выполнения команды (использующая временный сеанс) или создание постоянного сеанса на удаленном компьютере завершается сбоем. Пользователь может использовать параметр ConfigurationName командлетов, которые создают сеансы, чтобы выбрать другую конфигурацию сеанса, если она доступна.

Члены группы "Администраторы" на компьютере могут определить, кто имеет разрешение на удаленное подключение к компьютеру, изменив дескрипторы безопасности в конфигурациях сеансов по умолчанию и создав новые конфигурации сеанса с разными дескрипторами безопасности.

Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).

## <a name="windows-network-locations"></a>СЕТЕВЫЕ РАСПОЛОЖЕНИЯ WINDOWS

Начиная с Windows PowerShell 3,0, командлет Enable-PSRemoting может включить удаленное взаимодействие на клиентских и серверных версиях Windows в частных, доменных и общедоступных сетях.

В серверных версиях Windows с частными и доменными сетями командлет Enable-PSRemoting создает правила брандмауэра, которые допускают неограниченный удаленный доступ. Он также создает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров в той же локальной подсети. Это правило брандмауэра для локальной подсети включено по умолчанию для серверных версий Windows в общедоступных сетях, но Enable-PSRemoting повторно применяет правило, если оно было изменено или удалено.

В клиентских версиях Windows с частными и доменными сетями по умолчанию командлет Enable-PSRemoting создает правила брандмауэра, которые допускают неограниченный удаленный доступ.

Чтобы включить удаленное взаимодействие для клиентских версий Windows с общедоступными сетями, используйте параметр SkipNetworkProfileCheck командлета Enable-PSRemoting. Он создает правило брандмауэра, разрешающее удаленный доступ только с компьютеров в той же локальной подсети.

Чтобы удалить ограничение локальной подсети в общедоступных сетях и разрешить удаленный доступ из всех расположений в клиентских и серверных версиях Windows, используйте командлет Set-NetFirewallRule в модуле NetSecurity. Выполните следующую команду:

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

В Windows PowerShell 2,0 в серверных версиях Windows Enable-PSRemoting создает правила брандмауэра, разрешив удаленный доступ ко всем сетям.

В Windows PowerShell 2,0 на клиентских версиях Windows Enable-PSRemoting создает правила брандмауэра только для частных и доменных сетей. Если сетевое расположение является общедоступным, Enable-PSRemoting завершается сбоем.

## <a name="run-as-administrator"></a>ЗАПУСК ОТ ИМЕНИ АДМИНИСТРАТОРА

Для следующих операций удаленного взаимодействия требуются права администратора.

- Установление удаленного подключения к локальному компьютеру. Такой сценарий обычно называется «замыканием на себя».

- Управление конфигурациями сеансов на локальном компьютере.

- Просмотр и изменение параметров WS-Management на локальном компьютере. Это параметры в узле LocalHost на диске WSMAN:.

Для выполнения этих задач необходимо запустить PowerShell с параметром "Запуск от имени администратора", даже если вы являетесь членом группы "Администраторы" на локальном компьютере.

В Windows 7 и Windows Server 2008 R2 для запуска Windows PowerShell с параметром "Запуск от имени администратора":

1. Нажмите кнопку Пуск, выберите пункт Все программы, затем стандартные, а затем щелкните папку Windows PowerShell.
2. Щелкните правой кнопкой мыши Windows PowerShell и выберите команду "Запуск от имени администратора".

Чтобы запустить Windows PowerShell с параметром "Запуск от имени администратора", выполните следующие действия.

1. Нажмите кнопку Пуск, выберите пункт Все программы, а затем щелкните папку Windows PowerShell.
2. Щелкните правой кнопкой мыши Windows PowerShell и выберите команду "Запуск от имени администратора".

Параметр "Запуск от имени администратора" также доступен в других записях проводника Windows для Windows PowerShell, включая ярлыки. Просто щелкните элемент правой кнопкой мыши и выберите команду "Запуск от имени администратора".

При запуске Windows PowerShell из другой программы, например Cmd.exe, используйте параметр "Запуск от имени администратора" для запуска программы.

## <a name="how-to-configure-your-computer-for-remoting"></a>НАСТРОЙКА КОМПЬЮТЕРА ДЛЯ УДАЛЕННОГО ВЗАИМОДЕЙСТВИЯ

Компьютеры, на которых работают все поддерживаемые версии Windows, могут устанавливать удаленные подключения к и выполнять удаленные команды в PowerShell без какой бы то ни было конфигурации. Однако для получения подключений и разрешения пользователям создавать локальные и удаленные сеансы PowerShell ("PSSession") и выполнять команды на локальном компьютере необходимо включить удаленное взаимодействие PowerShell на компьютере.

По умолчанию для Windows Server 2012 и более новых выпусков Windows Server включено удаленное взаимодействие PowerShell. Если параметры изменены, можно восстановить параметры по умолчанию, запустив командлет Enable-PSRemoting.

Во всех остальных поддерживаемых версиях Windows необходимо запустить командлет Enable-PSRemoting, чтобы включить удаленное взаимодействие PowerShell.

Функции удаленного взаимодействия PowerShell поддерживаются службой WinRM, которая является реализацией Майкрософт протокола веб-служб для управления (WS-Management). При включении удаленного взаимодействия PowerShell вы изменяете конфигурацию по умолчанию WS-Management и добавляете конфигурацию системы, позволяющую пользователям подключаться к WS-Management.

Чтобы настроить PowerShell для получения удаленных команд:

1. Запустите PowerShell с параметром "Запуск от имени администратора".
2. В командной строке введите следующий текст: `Enable-PSRemoting`.

Чтобы убедиться, что удаленное взаимодействие настроено правильно, выполните команду теста, например следующую команду, которая создает удаленный сеанс на локальном компьютере.

```powershell
New-PSSession
```

Если удаленное взаимодействие настроено правильно, команда создаст сеанс на локальном компьютере и возвратит объект, представляющий сеанс. Выходные данные должны выглядеть следующим образом:

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

Если команда завершается ошибкой, обратитесь к разделу [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).

## <a name="understand-policies"></a>ОБЩИЕ СВЕДЕНИЯ О ПОЛИТИКАХ

При удаленной работе вы используете два экземпляра PowerShell: один на локальном компьютере и один на удаленном компьютере. В результате работа зависит от политик Windows и политик PowerShell на локальном и удаленном компьютерах.

Как правило, перед подключением и установкой подключения действуют политики на локальном компьютере. При использовании подключения политики на удаленном компьютере вступают в действие.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[about_PSSessions](about_PSSessions.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
