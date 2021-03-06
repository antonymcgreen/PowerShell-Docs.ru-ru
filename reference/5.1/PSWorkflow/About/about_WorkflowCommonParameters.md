---
description: В этом разделе описываются параметры, допустимые для всех команд рабочего процесса Windows PowerShell. Поскольку обработчик Windows PowerShell добавляет их в рабочие процессы, эти параметры можно использовать в любом рабочем процессе, и они автоматически включаются в создаваемых рабочих процессах.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflowcommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WorkflowCommonParameters
ms.openlocfilehash: c371666d4f58386848e7ef715b7c804dc1e8f28e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387793"
---
# <a name="about-workflowcommonparameters"></a>О Воркфловкоммонпараметерс

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

В этом разделе описываются параметры, допустимые для всех команд рабочего процесса Windows PowerShell. Поскольку обработчик Windows PowerShell добавляет их в рабочие процессы, эти параметры можно использовать в любом рабочем процессе, и они автоматически включаются в создаваемых рабочих процессах.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Общие параметры рабочего процесса Windows PowerShell — это набор параметров командлета, которые можно использовать со всеми рабочими процессами и действиями Windows PowerShell. Они добавляются обработчиком рабочих процессов Windows PowerShell, а не автором рабочего процесса, и автоматически становятся доступными в рабочих процессах и действиях. Однако рабочие процессы, вложенные в глубину трех уровней, не поддерживают общие параметры, включая общие параметры рабочего процесса.

Все параметры рабочего процесса являются необязательными и называются (не являются позиционированными). Они не принимают входные данные из конвейера.

Большинство общих параметров рабочего процесса имеют префикс PS, например `PSComputerName` и `PSCredential` . Параметры с префиксом PS настраивают подключение и среду выполнения для конечных компьютеров, также называемых "удаленными узлами".

Многие общие параметры рабочего процесса, такие как `PSAllowRedirection` и `AsJob` , имеют имена, аналогичные параметрам, используемым в удаленном взаимодействии Windows PowerShell и фоновых заданиях. Эти параметры работают так же, как и параметры удаленного взаимодействия с аналогичным именем, поэтому вы можете использовать знания, разработанные в удаленном взаимодействии и задания для управления рабочими процессами.

Рабочие процессы представлены в Windows PowerShell 3,0.

### <a name="parameter-descriptions"></a>ОПИСАНИЯ ПАРАМЕТРОВ

В этом разделе описываются общие параметры рабочего процесса.

#### <a name="-asjob-switchparameter"></a>— AsJob \<SwitchParameter\>

Запускает рабочий процесс в качестве задания рабочего процесса. Команда рабочего процесса немедленно возвращает объект, представляющий родительское задание. Родительское задание содержит дочерние задания, выполняемые на каждом из целевых компьютеров. Для управления заданием используйте командлеты Job. Чтобы получить результаты задания, используйте командлет [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job).

#### <a name="-jobname-string"></a>-JobName \<String\>

Указывает понятное имя для задания рабочего процесса. По умолчанию задания называются Job\<n\>, где \<n\> — порядковый номер.

При использовании параметра JobName в команде рабочего процесса Рабочий процесс выполняется как задание, а команда рабочего процесса возвращает объект задания, даже если параметр не включен `AsJob` в команду.

Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделе [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

#### <a name="-psallowredirection-switchparameter"></a>-Псалловредиректион \<SwitchParameter\>

Разрешает перенаправление подключения к конечным компьютерам.

При использовании `PSConnectionURI` параметра удаленное назначение может вернуть инструкцию для перенаправления на другой URI. По умолчанию Windows PowerShell не перенаправляет соединения, но можно использовать параметр, `PSAllowRedirection` чтобы разрешить перенаправление подключения к целевому компьютеру.

Кроме того, можно ограничить число перенаправлений подключения, задав `MaximumConnectionRedirectionCount` свойство для `$PSSessionOption` переменной предпочтения или `MaximumConnectionRedirectionCount` свойство значения свойства объекта `PSSessionOption parameter` . Значение по умолчанию — 5. Дополнительные сведения см. в описании `PSSessionOption` параметра и [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

#### <a name="-psapplicationname-string"></a>-Псаппликатионнаме \<String\>

Указывает сегмент имени приложения универсального кода ресурса (URI) соединения, используемого для подключения к конечным компьютерам. Используйте этот параметр, чтобы указать имя приложения, если параметр не используется `ConnectionURI` в команде.

Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере. Если привилегированная переменная не определена, значение по умолчанию — WSMAN. Это значение подходит для большинства случаев Дополнительные сведения см. в разделе [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение. Значение этого параметра должно соответствовать значению `URLPrefix` свойства прослушивателя на удаленном компьютере.

#### <a name="-psauthentication-authenticationmechanism"></a>-Псаусентикатион \<AuthenticationMechanism\>

Указывает механизм, используемый для проверки подлинности учетных данных пользователя при подключении к конечным компьютерам.

Допустимые значения:

- **Default**
- **Основной**
- **CredSSP**
- **Digest** (дайджест)
- **Kerberos**
- **Новое**
- **NegotiateWithImplicitCredential**

Значение по умолчанию ― **Default**.

Сведения о значениях этого параметра см. в описании `System.Management.Automation.Runspaces.AuthenticationMechanism` перечисления в пакете SDK для PowerShell.

> [!WARNING]
> Проверка подлинности CredSSP, при применении которой учетные данные пользователя передаются на удаленный компьютер, предназначена для команд, требующих проверки подлинности для нескольких ресурсов, например для доступа к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

#### <a name="-psauthenticationlevel-authenticationlevel"></a>-Псаусентикатионлевел \<AuthenticationLevel\>

Задает уровень проверки подлинности для подключений к конечным компьютерам.
Значение по умолчанию ― **Default**.

Допустимые значения:

|Имя |Описание |
|---------|---------|
|**Без изменений** | уровень проверки подлинности совпадает с предыдущей командой. |
|**Default** | Проверка подлинности Windows. |
|**None** | Проверка подлинности COM не используется.   |
|**Подключить** | Проверка подлинности COM на уровне подключения.|
|**Call** | Проверка подлинности COM на уровне вызова.   |
|**Пакетов** | Проверка подлинности COM на уровне пакета.|
|**паккетинтегрити** | Проверка подлинности COM на уровне целостности пакета.  |
|**паккетприваци** | Проверка подлинности COM на уровне конфиденциальности пакета. |

#### <a name="-pscertificatethumbprint-string"></a>-Псцертификатесумбпринт \<String\>

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут быть сопоставлены только с локальными учетными записями пользователей; они не работают с учетными записями домена.

Чтобы получить сертификат, используйте [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) или [Get-ChildItem] (.. /.. /Микрософт.повершелл.манажемент/жет-чилдитем.МД) командлеты на диске CERT: Windows PowerShell.

#### <a name="-pscomputername-string"></a>-PSComputerName \<String[]\>

Указывает список компьютеров, являющихся целевыми узлами рабочего процесса.
Команды или действия в рабочем процессе выполняются на компьютерах, указанных с помощью этого параметра. По умолчанию это локальный компьютер.

Введите имя NETBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями-запятыми. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Чтобы включить локальный компьютер в значение `PSComputerName` параметра, откройте Windows PowerShell с параметром "Запуск от имени администратора".

Если этот параметр не указан в команде или имеет значение `$null` или является пустой строкой, целевой объект рабочего процесса является локальным компьютером, а удаленное взаимодействие Windows PowerShell не используется для выполнения команды.

Чтобы использовать IP-адрес в значении `ComputerName` параметра, команда должна включать `PSCredential` параметр. Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере. Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе *"Добавление компьютера в список надежных узлов"* в [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

#### <a name="-psconfigurationname-string"></a>-Псконфигуратионнаме \<String\>

Указывает конфигурации сеанса, используемые для настройки сеансов на целевых компьютерах. Введите конфигурацию сеанса на конечных компьютерах (не на компьютере сервера рабочих процессов). Значение по умолчанию — `Microsoft.PowerShell.Workflow`.

#### <a name="-psconnectionretrycount-uint"></a>-Псконнектионретрикаунт \<UInt\>

Указывает максимальное число попыток подключения к каждому целевому компьютеру, если первая попытка соединения завершается неудачно. Введите число от 1 до 4 294 967 295 (UInt. MaxValue). Значение по умолчанию, равное нулю (0), не представляет повторных попыток.

#### <a name="-psconnectionretryintervalsec-uint"></a>-Псконнектионретринтервалсек \<UInt\>

Указывает задержку между попытками повтора подключения в секундах. Значение по умолчанию равно нулю (0). Этот параметр допустим только в том случае, если значение Псконнектионретрикаунт равно по меньшей мере 1.

#### <a name="-psconnectionuri-systemuri"></a>-Псконнектионури \<System.Uri\>

Указывает универсальный код ресурса (URI), определяющий конечную точку подключения для рабочего процесса на целевом компьютере. Значение URI должно быть указано полностью.

Строка имеет следующий формат:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Значение по умолчанию — `http://localhost:5985/WSMAN`.

Если не указать `PSConnectionURI` , можно использовать `PSUseSSL` `PSComputerName` Параметры,, `PSPort` и `PSApplicationName` для указания `PSConnectionURI` значений.

Допустимые значения для сегмента транспорта URI: **http** и **HTTPS**.
Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS. Чтобы использовать порты по умолчанию для удаленного взаимодействия Windows PowerShell, укажите порт 5985 для протокола HTTP и 5986 для протокола HTTPS.

#### <a name="-pscredential-pscredential"></a>-PSCredential \<PSCredential\>

Указывает учетную запись пользователя, имеющую разрешение на запуск рабочего процесса на целевом компьютере. По умолчанию используется текущий пользователь. Этот параметр допустим только в том случае, если параметр PSComputerName включен в команду.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите переменную, содержащую `PSCredential` объект, например, `Get-Credential` возвращаемый командлетом. Если ввести только имя пользователя, появится приглашение ввести пароль.

#### <a name="-pselapsedtimeoutsec-uint32"></a>-PSElapsedTimeoutSec \<UInt32\>

Определяет, как долго рабочий процесс и все связанные с ним ресурсы будут поддерживаться в системе. По истечении времени ожидания рабочий процесс удаляется, даже если он еще обрабатывается. Введите значение от 10 до 4 294 967 295. Значение по умолчанию 0 (ноль) означает, что время ожидания не истекло.

#### <a name="-psparametercollection-hashtable"></a>-Пспараметерколлектион \<Hashtable[]\>

Указывает различные значения общих параметров рабочего процесса для разных целевых компьютеров.

Введите разделенный запятыми список хэш-таблиц с одной хэш-таблицей для каждого целевого компьютера. В каждой хэш-таблице первым ключом является, `PSComputerName` а значением — имя целевого компьютера. В имени компьютера разрешены подстановочные знаки. Для остальных ключей хэш-таблицы ключ является именем параметра, а значение — значением параметра.

Пример:

```powershell
-PSParameterCollection @{PSComputerName="*"; PSElapsedTimeoutSec=20},
@{PSComputerName="Server02"},
@{PSComputerName="Server03"},
@{PSComputerName="Server01"; PSElapsedTimeoutSec=10}
```

В приведенном выше примере все соединения будут иметь PSElapsedTimeoutSec по умолчанию 20 секунд, за исключением Server01, который переопределяет значение по умолчанию, указав собственное время ожидания 10 секунд.

#### <a name="-pspersist-boolean"></a>-Псперсист \<Boolean\>

Добавляет контрольные точки в рабочий процесс в дополнение к любым контрольным точкам, указанным в рабочем процессе.

Этот параметр не может подавлять контрольные точки в рабочем процессе, например указанные с помощью `PSPersist` общего параметра действия, `Checkpoint-Workflow` действия или `$PSPersistPreference` переменной.

"Checkpoint" или "точка сохранения" — это моментальный снимок состояния рабочего процесса и данных, которые фиксируются во время выполнения рабочего процесса и сохраняются в хранилище сохраняемости на диске или в базе данных SQL. Рабочий процесс Windows PowerShell использует сохраненные данные для возобновления приостановленного или прерванного рабочего процесса из последней точки сохранения, а не для перезапуска рабочего процесса.

Допустимые значения:

- ( *По умолчанию* ) Если опустить этот параметр, в начало и конец рабочего процесса добавляется контрольная точка, а также любые контрольные точки, указанные в рабочем процессе.

- `$True`. Добавляет контрольную точку в начало и конец рабочего процесса и контрольную точку после каждого действия в дополнение к любым контрольным точкам, указанным в рабочем процессе.

- `$False`. Контрольные точки не добавляются. Контрольные точки берутся только при указании в рабочем процессе.

#### <a name="-psport-int32"></a>-Пспорт \<Int32\>

Указывает сетевой порт на целевых компьютерах. Порты по умолчанию: 5985 (порт службы удаленного управления Windows для HTTP) и 5986 (порт службы удаленного управления Windows для HTTPS).

Не используйте параметр Пспорт, если не требуется. Порт, заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах. Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.

#### <a name="-psprivatemetadata-hashtable"></a>-Псприватеметадата \<Hashtable\>

Предоставляет настраиваемые сведения для заданий рабочего процесса. Введите хэш-таблицу. Ключи и значения настраиваются для каждого рабочего процесса. Сведения о закрытых метаданных рабочего процесса см. в разделе справки по рабочему процессу.

Этот параметр не обрабатывается обработчиком рабочих процессов Windows PowerShell.
Вместо этого обработчик передает хэш-таблицу непосредственно в рабочий процесс.

#### <a name="-psrunningtimeoutsec-uint32"></a>-Псруннингтимеаутсек \<UInt32\>

Задает время выполнения рабочего процесса в секундах, исключая время приостановки рабочего процесса. Если выполнение рабочего процесса не завершено по истечении времени, обработчик рабочих процессов Windows PowerShell принудительно останавливает выполнение рабочего процесса.

#### <a name="-pssessionoption-pssessionoption"></a>-PSSessionOption \<PSSessionOption\>

Задает дополнительные параметры для сеансов целевых компьютеров. Введите `PSSessionOption` объект, например, созданный с помощью `New-PSSessionOption` командлета.

Значения по умолчанию для параметров сеанса определяются значением `$PSSessionOption` привилегированной переменной, если оно задано. В противном случае сеанс использует значения, указанные в конфигурации сеанса.

Описание параметров сеанса, включая значения по умолчанию, см. в разделе справки для `New-PSSessionOption` командлета (.. /.. /Микрософт.повершелл.коре/Нев-пссессионоптион.МД). Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

#### <a name="-psusessl-switchparameter"></a>-Псусессл \<SwitchParameter\>

Использует протокол SSL (SSL) для установления соединения с конечным компьютером. По умолчанию SSL не используется.

Протокол WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети. UseSSL является дополнительной защитой, которая отправляет данные по HTTPS вместо HTTP. Если вы используете этот параметр, но SSL недоступен для порт, указанному в команде, она завершается ошибкой.

## <a name="see-also"></a>СМ. ТАКЖЕ

- [about_ActivityCommonParameters](about_ActivityCommonParameters.md)
- [about_Workflows](about_Workflows.md)
- [Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)
- [New-PSWorkflowExecutionOption](xref:PSWorkflow.New-PSWorkflowExecutionOption)
- [New-PSWorkflowSession](xref:PSWorkflow.New-PSWorkflowSession)
