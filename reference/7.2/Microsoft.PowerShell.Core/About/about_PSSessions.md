---
description: Описывает сеансы PowerShell (PSSession) и объясняет, как установить постоянное подключение к удаленному компьютеру.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: edc7109f3f79376ac1d348d3c3cd65e3a8d3e69c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602843"
---
# <a name="about-pssessions"></a>О PSSession

## <a name="short-description"></a>Краткое описание
Описывает сеансы PowerShell (PSSession) и объясняет, как установить постоянное подключение к удаленному компьютеру.

## <a name="long-description"></a>Полное описание

Для выполнения команд PowerShell на удаленном компьютере можно использовать параметр **ComputerName** командлета или создать сеанс PowerShell (PSSession) и выполнить команды в PSSession.

При создании сеанса PSSession PowerShell устанавливает постоянное подключение к удаленному компьютеру. Используйте PSSession для выполнения серии связанных команд на удаленном компьютере. Команды, выполняемые в одном сеансе PSSession, могут совместно использовать данные, такие как значения переменных, псевдонимов и функций.

Можно также создать сеанс PSSession на локальном компьютере и выполнить в нем команды.
Локальный сеанс PSSession использует инфраструктуру удаленного взаимодействия PowerShell для создания и обслуживания PSSession.

Начиная с Windows PowerShell 3,0, PSSession не зависят от сеансов, в которых они созданы. Активные PSSession хранятся на удаленном компьютере (или на удаленном компьютере или на стороне сервера). В результате вы можете отключиться от сеанса PSSession и повторно подключиться к нему позже с того же компьютера или с другого компьютера.

В этом разделе объясняется, как создавать, использовать, получать и удалять PSSession. Дополнительные сведения см. в разделе [about_PSSession_Details](about_PSSession_Details.md).

Примечание. PSSession использует инфраструктуру удаленного взаимодействия PowerShell. Чтобы использовать PSSession, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.
Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).

В Windows Vista и более поздних версиях Windows для создания сеанса PSSession на локальном компьютере необходимо запустить PowerShell с параметром "Запуск от имени администратора".

## <a name="what-is-a-session"></a>Что такое сеанс?

Сеанс — это среда, в которой выполняется PowerShell.

Каждый раз при запуске PowerShell создается сеанс, а в сеансе можно выполнять команды. Можно также добавлять элементы в сеанс, например модули и оснастки, а также создавать элементы, такие как переменные, функции и псевдонимы. Эти элементы существуют только в сеансе и удаляются по окончании сеанса.

Кроме того, можно создавать управляемые пользователем сеансы, известные как "сеансы PowerShell" или "PSSession" на локальном компьютере или на удаленном компьютере. Как и сеанс по умолчанию, можно выполнять команды в PSSession, а также добавлять и создавать элементы. Однако в отличие от сеанса, который запускается автоматически, вы можете управлять создаваемыми PSSession. Вы можете получать, создавать, настраивать и удалять их, отключать и повторно подключаться к ним, а также выполнять несколько команд в одном сеансе PSSession. Сеанс PSSession остается доступным до тех пор, пока вы не удалите его или не истечет время ожидания.

Как правило, сеанс PSSession создается для выполнения последовательности связанных команд на удаленном компьютере. При создании PSSession на удаленном компьютере PowerShell устанавливает постоянное подключение к удаленному компьютеру для поддержки сеанса.

Если вы используете параметр **ComputerName** `Invoke-Command` командлета или для запуска `Enter-PSSession` удаленного сеанса, PowerShell создает временный сеанс на удаленном компьютере и закрывает сеанс, как только команда завершится, либо сразу же после завершения интерактивного сеанса. Вы не можете управлять этими временными сеансами, и их нельзя использовать для нескольких команд или единого интерактивного сеанса.

В PowerShell "текущий сеанс" — это сеанс, в котором вы работаете. "Текущий сеанс" может ссылаться на любой сеанс, включая временный сеанс или PSSession.

## <a name="why-use-a-pssession"></a>Зачем использовать PSSession?

Используйте сеанс PSSession, если требуется постоянное подключение к удаленному компьютеру.
С помощью PSSession можно выполнять ряд команд, которые совместно используют данные, такие как значения переменных, содержимое функции или определение псевдонима.

Удаленные команды можно выполнять без создания сеанса PSSession. Используйте параметр **ComputerName** командлетов с удаленным включением для выполнения одной команды или ряда несвязанных команд на одном или нескольких компьютерах.

При использовании параметра **ComputerName** в `Invoke-Command` или `Enter-PSSession` PowerShell устанавливает временное подключение к удаленному компьютеру, а затем закрывает подключение сразу после завершения команды. При закрытии соединения все создаваемые элементы данных теряются.

Другие командлеты, имеющие параметр **ComputerName** , например `Get-Eventlog` и `Get-WmiObject` , используют разные технологии удаленного взаимодействия для сбора данных. Нет — создать постоянное подключение, например PSSession.

## <a name="how-to-create-a-pssession"></a>Создание сеанса PSSession

Чтобы создать сеанс PSSession, используйте `New-PSSession` командлет. Чтобы создать сеанс PSSession на удаленном компьютере, используйте параметр **ComputerName** `New-PSSession` командлета.

Например, следующая команда создает новый сеанс PSSession на компьютере Server01.

```powershell
New-PSSession -ComputerName Server01
```

При отправке команды `New-PSSession` создает сеанс PSSession и возвращает объект, представляющий сеанс PSSession. Объект можно сохранить в переменной при создании сеанса PSSession или с помощью `Get-PSSession` команды, чтобы получить сеанс PSSession позднее.

Например, следующая команда создает новый сеанс PSSession на компьютере Server01 и сохраняет полученный объект в переменной $ps.

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a>Создание PSSession на нескольких компьютерах

Чтобы создать PSSession на нескольких компьютерах, используйте параметр **ComputerName** `New-PSSession` командлета. Введите имена удаленных компьютеров в виде списка с разделителями-запятыми.

Например, чтобы создать PSSession на компьютерах Server01, Server02 и Server03, введите:

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

`New-PSSession` создает один сеанс PSSession на каждом из удаленных компьютеров.

## <a name="how-to-get-pssessions"></a>Как получить PSSession

Чтобы получить PSSession, созданные в текущем сеансе, используйте `Get-PSSession` командлет без параметра **ComputerName** . `Get-PSSession` возвращает тот же тип объекта, который `New-PSSession` возвращает.

Следующая команда получает все PSSession, созданные в текущем сеансе.

```powershell
Get-PSSession
```

По умолчанию в PSSession отображается их идентификатор и отображаемое имя по умолчанию. При создании сеанса можно назначить альтернативное отображаемое имя.

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

Можно также сохранить PSSession в переменной. Следующая команда получает PSSession и сохраняет их в \$ переменной ps123.

```powershell
$ps123 = Get-PSSession
```

При использовании командлетов PSSession можно ссылаться на сеанс PSSession по его ИДЕНТИФИКАТОРу, по имени или ИДЕНТИФИКАТОРу экземпляра (идентификатор GUID). Следующая команда получает сеанс PSSession по его ИДЕНТИФИКАТОРу и сохраняет его в \$ переменной ps01.

```powershell
$ps01 = Get-PSSession -Id 1
```

Начиная с Windows PowerShell 3,0, PSSession хранятся на удаленном компьютере. Чтобы получить PSSession, созданные на определенных удаленных компьютерах, используйте параметр **ComputerName** `Get-PSSession` командлета. Следующая команда получает PSSession, созданный на удаленном компьютере Server01. Сюда входят PSSession, созданные в текущем сеансе и в других сеансах на локальном компьютере или на других компьютерах.

```powershell
Get-PSSession -ComputerName Server01
```

В Windows PowerShell 2,0 `Get-PSSession` возвращает только PSSession, созданные в текущем сеансе. Он не получает PSSession, которые были созданы в других сеансах или на других компьютерах, даже если сеансы подключены к и работают с командами на локальном компьютере.

## <a name="how-to-run-commands-in-a-pssession"></a>Выполнение команд в PSSession

Чтобы выполнить команду в одном или нескольких PSSession, используйте `Invoke-Command` командлет.
Используйте параметр Session, чтобы указать PSSession и параметр **ScriptBlock** для указания команды.

Например, чтобы выполнить `Get-ChildItem` команду ("Dir") в каждой из трех PSSession, сохраненных в переменной $ps 123, введите:

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a>Удаление PSSession

По завершении работы с PSSession используйте `Remove-PSSession` командлет, чтобы удалить PSSession и освободить используемые им ресурсы.

```powershell
Remove-PSSession -Session $ps
```

или

```powershell
Remove-PSSession -Id 1
```

Чтобы удалить сеанс PSSession с удаленного компьютера, используйте параметр **ComputerName** `Remove-PSSession` командлета.

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

Если не удалить PSSession, то сеанс PSSession остается доступным для использования до истечения времени ожидания.

Можно также использовать параметр **IdleTimeout** `New-PSSessionOption` командлета, чтобы установить срок действия для неактивного сеанса PSSession. Дополнительные сведения см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

## <a name="the-pssession-cmdlets"></a>Командлеты PSSession

Чтобы получить список командлетов PSSession, введите:

```powershell
Get-Help *-PSSession
```

- Connect-PSSession: подключает сеанс PSSession к текущему сеансу
- Disconnect-PSSession: отключает сеанс PSSession от текущего сеанса
- Enter-PSSession: запускает интерактивный сеанс
- Exit-PSSession: завершает интерактивный сеанс
- Get-PSSession: получает PSSession в текущем сеансе
- New-PSSession: создает новый сеанс PSSession на локальном или удаленном компьютере.
- Receive-PSSession: получение результатов команд, которые выполнялись в отключенном сеансе
- Remove-PSSession: удаляет PSSession в текущем сеансе

## <a name="for-more-information"></a>Дополнительные сведения см. в разделе

Дополнительные сведения о PSSession см. в разделе [about_PSSession_Details](about_PSSession_Details.md).

## <a name="see-also"></a>См. также:

[about_Remote](about_Remote.md)

[about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[Connect-PSSession](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[Disconnect-PSSession](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession;](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Remove-PSSession](xref:Microsoft.PowerShell.Core.Remove-PSSession)

