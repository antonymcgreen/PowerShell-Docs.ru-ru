---
description: Файлы конфигурации для PowerShell Core, замена конфигурации реестра.
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 7190484832958e778a21e6d2cc91771587bffdbf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604430"
---
# <a name="about-powershell-config"></a>О конфигурации PowerShell

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Файлы конфигурации для PowerShell Core, замена конфигурации реестра.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

`powershell.config.json`Файл содержит параметры конфигурации для PowerShell Core. PowerShell загружает эту конфигурацию при запуске. Параметры также можно изменить во время выполнения. Ранее эти параметры хранились в реестре Windows для PowerShell, но теперь содержатся в файле для включения настройки в macOS и Linux.

> [!WARNING]
> Если `powershell.config.json` файл содержит недопустимый JSON PowerShell, невозможно запустить интерактивный сеанс.
> В этом случае необходимо исправить файл конфигурации.

> [!NOTE]
> Нераспознанные ключи или недопустимые значения в файле конфигурации будут игнорироваться без уведомления.

### <a name="allusers-shared-configuration"></a>Конфигурация AllUsers (общая)

`powershell.config.json`Файл в `$PSHOME` каталоге определяет конфигурацию всех сеансов PowerShell Core, выполняемых из этой установки PowerShell Core.

> [!NOTE]
> `$PSHOME`Расположение определяется в том же каталоге, что и исполняемая System.Management.Automation.dll сборка. Это относится и к размещенным экземплярам пакета SDK для PowerShell.

### <a name="currentuser-per-user-configurations"></a>Конфигурации CurrentUser (на пользователя)

Вы также можете настроить PowerShell для отдельных пользователей, поместив файл в каталог конфигурации области пользователя. Каталог конфигурации пользователя можно найти на разных платформах с помощью команды `Split-Path $PROFILE.CurrentUserCurrentHost` .

## <a name="general-configuration-settings"></a>Общие параметры конфигурации

### <a name="executionpolicy"></a>ExecutionPolicy

> [!IMPORTANT]
> Эта конфигурация применяется только на платформах Windows.

Настраивает политику выполнения для сеансов PowerShell, определяя, какие скрипты можно запускать. По умолчанию PowerShell использует существующую политику выполнения.

Для конфигураций AllUsers этот параметр задает политику выполнения **LocalMachine** .
Для конфигураций CurrentUser этот параметр задает политику выполнения **CurrentUser** .

> [!NOTE]
> [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)Командлет изменяет этот параметр в файле конфигурации ALLUSERS при вызове с параметром `-Scope LocalMachine` и изменяет его в файле конфигурации CurrentUser при вызове с помощью `-Scope CurrentUser` .

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

Где:

- `<shell-id>` Указывает идентификатор текущего узла PowerShell.
  Для обычной среды PowerShell Core это `Microsoft.PowerShell` .
  В любом сеансе PowerShell его можно обнаружить с помощью `$ShellId` .
- `<execution-policy>` Указывает на допустимое имя политики выполнения.

В следующем примере для политики выполнения PowerShell задается значение `RemoteSigned` .

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

В Windows эквивалентные разделы реестра можно найти в `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` разделах `HKEY_LOCAL_MACHINE` и `HKEY_CURRENT_USER` .

### <a name="psmodulepath"></a>PSModulePath

Переопределяет компонент PSModulePath для этого сеанса PowerShell. Если конфигурация предназначена для текущего пользователя, задает путь к модулю CurrentUser. Если конфигурация предназначена для всех пользователей, задает путь к модулю Аллусер.

> [!WARNING]
> Настройка пути к модулю AllUsers или CurrentUser не приведет к изменению расположения установки с областью действия для модулей PowerShellGet, таких как [Install-Module](/powershell/module/powershellget/install-module).
> Эти командлеты всегда используют пути модулей *по умолчанию* .

Если значение не задано, будет использоваться значение по умолчанию для соответствующего компонента пути к модулю. Дополнительные сведения об этих значениях по умолчанию см. в разделе [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) .

Этот параметр позволяет использовать переменные среды, внедряя их между `%` символами, например, так `"%HOME%\Documents\PowerShell\Modules"` же, как и команда cmd. Этот синтаксис также применим в Linux и macOS. Примеры см. ниже.

```Schema
"PSModulePath": "<ps-module-path>"
```

Где:

- `<ps-module-path>` абсолютный путь к каталогу модуля. Для всех пользовательских конфигураций это каталог общего модуля AllUsers. Для текущих пользовательских конфигураций это каталог модулей CurrentUser.

В этом примере показана конфигурация PSModulePath для среды Windows:

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

В этом примере показана конфигурация PSModulePath для среды macOS или Linux:

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

В этом примере показано, как внедрить переменную среды в конфигурацию PSModulePath. Обратите внимание, что `HOME` при использовании переменной среды и `/` разделителя каталогов это будет работать в Windows, MacOS и Linux.

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

В этом примере показано, как внедрить переменную среды в конфигурацию PSModulePath, которая будет работать только в macOS и Linux:

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> Переменные PowerShell не могут быть внедрены в конфигурации PSModulePath.
> В конфигурациях PSModulePath в Linux и macOS учитывается регистр. Конфигурация PSModulePath должна использовать допустимые разделители каталогов для платформы. В macOS и Linux это означает `/` . В Windows обе `/` и `\` будут работать.

### <a name="experimentalfeatures"></a>експерименталфеатурес

Имена экспериментальных функций, которые необходимо включить в PowerShell.
По умолчанию экспериментальные функции не включены.
Значение по умолчанию — пустой массив.

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

Где:

- `<experimental-feature-name>` имя экспериментальной функции, которую необходимо включить.

В следующем примере включаются экспериментальные функции **псимплиЦитремотинг** и **Псусеаббревиатионекспансион** при запуске PowerShell.

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

Дополнительные сведения о экспериментальных функциях см. в разделе [POWERSHELL RFC 29][RFC0029].

## <a name="non-windows-logging-configuration"></a>Конфигурация ведения журнала не Windows

> [!IMPORTANT]
> Параметры конфигурации в этом разделе применимы только к macOS и Linux.
> Ведение журнала для Windows осуществляется с помощью Просмотр событий Windows.

Ведение журнала PowerShell в macOS и Linux можно настроить в файле конфигурации PowerShell. Полное описание ведения журнала PowerShell для систем, отличных от Windows, см. в статье [о ведении журнала](./about_Logging_Non-Windows.md).

### <a name="logidentity"></a>логидентити

> [!IMPORTANT]
> Этот параметр можно использовать только в macOS и Linux.

Задает имя удостоверения, используемое для записи в системный журнал. Значение по умолчанию — "PowerShell".

```Schema
"LogIdentity": "<log-identity>"
```

Где:

- `<log-identity>` — Это строковое удостоверение, которое PowerShell должно использовать для записи в системный журнал.

> [!NOTE]
> Вы можете использовать разные значения **логидентити** для каждого установленного экземпляра PowerShell.

В этом примере мы настроим **логидентити** для предварительной версии PowerShell.

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a>LogLevel

> [!IMPORTANT]
> Этот параметр можно использовать только в macOS и Linux.

Задает минимальный уровень серьезности, при котором PowerShell должен вести журнал.

```Schema
"LogLevel": "<log-level>|default"
```

Где:

- `<log-level>` может принимать одно из следующих значений:
  - Всегда
  - Критически важно
  - Ошибка
  - Предупреждение
  - Informational
  - Подробный
  - Отладка

> [!NOTE]
> Задание уровня ведения журнала включает все уровни журнала, расположенные выше.

При выборе значения **по умолчанию** для этого параметра будет использоваться значение по умолчанию.
Значение по умолчанию — **информационное**.

В следующем примере задается значение **verbose**.

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a>логчаннелс

> [!IMPORTANT]
> Этот параметр можно использовать только в macOS и Linux.

Определяет, какие каналы ведения журнала включены.

```Schema
"LogChannels": "<log-channel>,..."
```

Где:

- `<log-channel>` может принимать одно из следующих значений:
  - Операционные — записывает основные сведения о действиях PowerShell
  - Аналитическая — журналы более подробные диагностические сведения

Значение по умолчанию — " **работает**". Чтобы включить оба канала, включите оба значения в одну строку с разделителями-запятыми. Пример:

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a>логкэйвордс

> [!IMPORTANT]
> Этот параметр можно использовать только в macOS и Linux.

Определяет, какие части PowerShell регистрируются в журнале. По умолчанию все ключевые слова журнала включены. Чтобы включить несколько ключевых слов, перечислите значения в одной строке с разделителями-запятыми.

```Schema
"LogKeywords": "<log-keyword>,..."
```

Где:

- `<log-keyword>` может принимать одно из следующих значений:
  - Пространство выполнения — управление пространством выполнения
  - Конвейер — операции конвейера
  - Обработка протокола связи с протоколом, например PSRP
  - Транспорт — поддержка транспортного уровня, например SSH
  - Хост-функции узла PowerShell, например взаимодействие с консолью
  - Командлеты — встроенные командлеты PowerShell
  - Сериализатор — логика сериализации
  - Сеанс — состояние сеанса PowerShell
  - Манажедплугин — подключаемый модуль WSMan

> [!NOTE]
> Обычно рекомендуется оставить это значение неустановленным, если вы не пытаетесь диагностировать определенное поведение в известной части PowerShell.
> Изменение этого значения уменьшает только объем записываемых данных.

В этом примере ограничивается ведение журнала операциями с пространством выполнения, логикой конвейера и командлетом. Все остальные журналы будут пропущены.

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a>Дополнительные примеры конфигураций

### <a name="example-windows-configuration"></a>Пример конфигурации Windows

Для этой конфигурации заданы дополнительные параметры:

- Политика выполнения для этой установки PowerShell `AllSigned`
- Путь к модулю CurrentUser задается как каталог модуля на общем диске
- `PSImplicitRemotingBatching`Экспериментальная функция включена

> [!NOTE]
> `ExecutionPolicy`Параметры и `PSModulePath` здесь будут работать только на платформе Windows, так как путь к модулю использует `\` `;` символы-разделители и не является политикой выполнения `Unrestricted` (единственная допустимая политика на платформах, подобных Unix).

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a>Пример конфигурации, отличной от Windows

Эта конфигурация задает ряд параметров, которые работают только в macOS или Linux:

- Путь к модулю CurrentUser задается в пользовательском каталоге модуля в `$HOME`
- Включен экспериментальный компонент **псимплиЦитремотингбатчинг**
- В качестве уровня ведения журнала PowerShell задано **подробное** протоколирование.
- Эта установка PowerShell выполняет запись в журналы, используя удостоверение **Home-PowerShell** .

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a>См. также

[Общие сведения о политиках выполнения](./about_Execution_Policies.md)

[Сведения об автоматических переменных](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md

