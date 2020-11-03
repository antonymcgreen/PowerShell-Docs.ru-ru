---
description: Содержит описание конфигураций сеансов, определяющих, какие пользователи могут подключаться к компьютеру удаленно и какие команды они могут запускать.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 0956e2e96cb67d1c4b8c3ef245c6fa084b781351
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231249"
---
# <a name="about-session-configurations"></a>Сведения о конфигурациях сеансов

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Содержит описание конфигураций сеансов, определяющих, какие пользователи могут подключаться к компьютеру удаленно и какие команды они могут запускать.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Конфигурация сеанса, также известная как "конечная точка", представляет собой группу параметров на локальном компьютере, которые определяют среду для сеансов PowerShell, создаваемых при подключении удаленных или локальных пользователей к PowerShell на локальном компьютере.

Администраторы компьютера могут использовать конфигурации сеанса для защиты компьютера и определения пользовательских сред для пользователей, подключающихся к компьютеру.

Администраторы также могут использовать конфигурации сеанса для определения разрешений, необходимых для удаленного подключения к компьютеру. По умолчанию только члены группы "Администраторы" имеют разрешение на использование конфигурации сеанса для удаленного подключения, но можно изменить параметры по умолчанию, чтобы разрешить удаленное подключение к компьютеру всем пользователям или выбранным пользователям.

Начиная с версии PowerShell 3,0 можно использовать файл конфигурации сеанса для определения элементов конфигурации сеанса. Эта функция упрощает настройку сеансов без написания кода и обнаружение свойств конфигурации сеанса. Чтобы создать файл конфигурации сеанса, используйте командлет New-PSSessionConfiguration. Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files](about_Session_Configuration_Files.md).

Конфигурации сеансов — это функция веб-служб для удаленного взаимодействия PowerShell на основе управления (WS-Management). Они используются только при использовании командлетов New-PSSession, Invoke-Command или Enter-PSSession для подключения к удаленному компьютеру.

Примечание. для управления конфигурациями сеансов запустите PowerShell с параметром "Запуск от имени администратора".

Сведения о конфигурациях сеансов

Каждый сеанс PowerShell использует конфигурацию сеанса. Сюда входят постоянные сеансы, создаваемые с помощью командлетов New-PSSession или Enter-PSSession, а также временные сеансы, создаваемые PowerShell при использовании параметра ComputerName командлета, использующего технологию удаленного взаимодействия на основе WS-Management, например Invoke-Command.

Администраторы могут использовать конфигурации сеанса для защиты ресурсов компьютера и создания пользовательских сред для пользователей, подключающихся к компьютеру. Например, можно использовать конфигурацию сеанса для ограничения размера объектов, получаемых компьютером в сеансе, определения языкового режима сеанса и указания командлетов, поставщиков и функций, доступных в сеансе.

Настроив дескриптор безопасности конфигурации сеанса, вы определяете, кто может использовать конфигурацию сеанса для подключения к компьютеру.
Пользователи должны иметь разрешение EXECUTE на конфигурацию сеанса, чтобы использовать их в сеансе. Если у пользователя нет необходимых разрешений на использование каких-либо конфигураций сеанса на компьютере, пользователь не сможет удаленно подключиться к компьютеру.

По умолчанию разрешения на использование конфигураций сеансов по умолчанию имеют только администраторы компьютера. Однако можно изменить дескрипторы безопасности, чтобы разрешить всем, ни одному пользователю или только выбранным пользователям использовать конфигурации сеанса на компьютере.

Встроенные конфигурации сеансов

PowerShell 3,0 включает встроенные конфигурации сеансов с именами Microsoft. PowerShell и Microsoft. PowerShell. Workflow. На компьютерах под управлением 64-разрядных версий Windows PowerShell также предоставляет конфигурацию сеанса Microsoft. PowerShell32, 32-bit.

Конфигурация сеанса Microsoft. PowerShell используется для сеансов по умолчанию, то есть если команда для создания сеанса не включает параметр ConfigurationName командлета New-PSSession, Enter-PSSession или Invoke-Command.

Дескрипторы безопасности для конфигураций сеансов по умолчанию позволяют использовать их только членам группы «Администраторы» на локальном компьютере. Таким образом, только члены группы «Администраторы» могут подключаться к компьютеру удаленно, если не изменить параметры по умолчанию.

Конфигурации сеансов по умолчанию можно изменить с помощью переменной предпочтений $PSSessionConfigurationName. Дополнительные сведения см. в разделе about_Preference_Variables.

Просмотр конфигураций сеансов на локальном компьютере

Чтобы получить конфигурации сеанса на локальном компьютере, используйте командлет Get-PSSessionConfiguration.

Например, введите:

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

Объект конфигурации сеанса разворачивается в PowerShell 3,0, чтобы отобразить свойства конфигурации сеанса, настроенные с помощью файла конфигурации сеанса.

Например, чтобы просмотреть все свойства объекта конфигурации сеанса, введите:

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

Для просмотра конфигураций сеансов можно также использовать поставщик WSMan в PowerShell. Поставщик WSMan создает на вашем сеансе диск WSMAN:.

На диске WSMAN: конфигурации сеансов находятся в узле подключаемого модуля. (Все конфигурации сеансов находятся в узле подключаемого модуля, но в узле подключаемого модуля имеются элементы, которые не являются конфигурациями сеанса.)

Например, чтобы просмотреть конфигурации сеанса на локальном компьютере, введите:

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

Просмотр конфигураций сеансов на удаленном компьютере

Чтобы просмотреть конфигурации сеанса на удаленном компьютере, используйте командлет Connect-WSMan, чтобы добавить примечание для удаленного компьютера на диск WSMAN: на локальном компьютере, а затем используйте команду WSMAN: Drive для просмотра конфигураций сеанса.

Например, следующая команда добавляет узел для удаленного компьютера Server01 к диску WSMAN: на локальном компьютере.

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

После выполнения команды можно перейти к узлу Server01, чтобы просмотреть конфигурации сеанса.

Пример:

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

Изменение дескриптора безопасности конфигурации сеанса

В Windows Server 2012 и более новых выпусках Windows Server встроенные конфигурации сеансов по умолчанию включены для удаленных пользователей. В других поддерживаемых версиях Windows необходимо изменить дескрипторы безопасности конфигураций сеанса, чтобы разрешить удаленный доступ.

Чтобы включить удаленный доступ к конфигурациям сеансов на компьютере, используйте командлет Enable-PSRemoting. Этот командлет создает две конфигурации сеанса:

- с именем, определенным как "PowerShell". + "Текущая версия PowerShell"
- с именем "PowerShell. 6", без привязки к любой конкретной версии PowerShell.

Кроме того, по умолчанию только члены группы "Администраторы" на компьютере имеют разрешение на выполнение конфигураций сеансов по умолчанию, но вы можете изменить дескрипторы безопасности в конфигурациях сеансов по умолчанию и во всех создаваемых конфигурациях сеансов.

Чтобы предоставить другим пользователям разрешение на удаленное подключение к компьютеру, используйте командлет Set-PSSessionConfiguration, чтобы добавить разрешения на выполнение для этих пользователей в дескрипторы безопасности в конфигурациях сеанса Microsoft. PowerShell и Microsoft. PowerShell32.

Например, следующая команда открывает страницу свойств, которая позволяет изменить дескриптор безопасности для конфигурации сеанса Microsoft. PowerShell по умолчанию.

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

Чтобы запретить доступ всем конфигурациям сеансов на компьютере, используйте командлет Disable-PSSessionConfiguration. Например, следующая команда отключает конфигурации сеанса по умолчанию на компьютере.

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

Чтобы запретить удаленным пользователям подключаться к компьютеру, но разрешить локальным пользователям подключаться, используйте командлет Disable-PSRemoting. Disable-PSRemoting добавляет запись "Network_Deny_All" во все конфигурации сеанса на компьютере.

```powershell
PS C:> Disable-PSRemoting
```

Чтобы разрешить удаленным пользователям использовать все конфигурации сеансов на компьютере, используйте командлет Enable-PSRemoting или Enable-PSSessionConfiguration. Например, следующая команда включает удаленный доступ к встроенным конфигурациям сеанса.

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

Чтобы внести другие изменения в дескриптор безопасности конфигурации сеанса, используйте командлет Set-PSSessionConfiguration. Используйте параметр SecurityDescriptorSDDL для отправки строкового значения SDDL. Используйте параметр ShowSecurityDescriptorUI для вывода страницы свойств пользовательского интерфейса, помогающей создать новый SDDL.

Пример:

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

Создание новой конфигурации сеанса

Чтобы создать новую конфигурацию сеанса на локальном компьютере, используйте командлет Register-PSSessionConfiguration. Чтобы определить новую конфигурацию сеанса, можно использовать сборку C#, сценарий PowerShell и параметры командлета Register-PSSessionConfiguration.

Например, следующая команда создает конфигурацию сеанса, идентичную конфигурации сеанса Microsoft. PowerShell, за исключением того, что она ограничивает данные, получаемые от удаленной команды, до 20 мегабайт (МБ). (Значение по умолчанию — 50 МБ).

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

При создании конфигурации сеанса ее можно управлять с помощью других командлетов конфигурации сеанса, которые отображаются на диске WSMAN:.

Дополнительные сведения см. в разделе Register-PSSessionConfiguration.

Удаление конфигурации сеанса

Чтобы удалить конфигурацию сеанса с локального компьютера, используйте командлет Unregister-PSSessionConfiguration. Например, следующая команда удаляет конфигурацию сеанса документе newconfig с компьютера.

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

Дополнительные сведения см. в разделе Unregister-PSSessionConfiguration.

Восстановление конфигурации сеанса

Чтобы восстановить конфигурацию сеанса по умолчанию, которая была случайно удалена (отменена), используйте командлет Enable-PSRemoting.

Командлет Enable-PSRemoting воссоздает все конфигурации сеансов по умолчанию, которые не существуют на компьютере. Он не перезаписывает или не изменяет значения свойств существующих конфигураций сеанса.

Чтобы восстановить исходные значения свойств конфигурации сеанса по умолчанию, используйте Unregister-PSSessionConfiguration, чтобы удалить конфигурацию сеанса, а затем используйте командлет Enable-PSRemoting, чтобы создать его заново.

Выбор конфигурации сеанса

Чтобы выбрать определенную конфигурацию сеанса для сеанса, используйте параметр ConfigurationName командлета New-PSSession, введите-PSSession или Invoke-Command.

Например, эта команда использует командлет New-PSSession для запуска PSSession на компьютере Server01. Команда использует параметр ConfigurationName для выбора конфигурации WithProfile на компьютере Server01.

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

Эта команда будет выполнена успешно только в том случае, если текущий пользователь имеет разрешение на использование конфигурации сеанса WithProfile или если вы можете указать учетные данные пользователя, имеющего необходимые разрешения.

Можно также использовать переменную предпочтения $PSSessionConfigurationName, чтобы изменить конфигурацию сеанса по умолчанию на компьютере. Дополнительные сведения о переменной настройки $PSSessionConfigurationName см. в разделе about_Preference_Variables.

## <a name="keywords"></a>СЛОВАМИ

about_Endpoints about_SessionConfigurations

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Preference_Variables](about_Preference_Variables.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Session_Configuration_Files](about_Session_Configuration_Files.md)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[Enable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[Get-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[New-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[Set-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[Test-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[Unregister-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)
