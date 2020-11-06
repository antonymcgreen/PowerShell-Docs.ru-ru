---
description: PowerShell регистрирует внутренние операции из подсистемы, поставщиков и командлетов.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_non-windows?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging_Non — Windows
ms.openlocfilehash: f70e2cb2c04287e36ecdf21a97dd099fcfd23d65
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355499"
---
# <a name="about-logging-non-windows"></a><span data-ttu-id="99538-104">Сведения о ведении журнала, не относящемся к Windows</span><span class="sxs-lookup"><span data-stu-id="99538-104">About Logging Non-Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="99538-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="99538-105">Short description</span></span>
<span data-ttu-id="99538-106">PowerShell регистрирует внутренние операции из подсистемы, поставщиков и командлетов.</span><span class="sxs-lookup"><span data-stu-id="99538-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="99538-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="99538-107">Long description</span></span>

<span data-ttu-id="99538-108">PowerShell регистрирует сведения об операциях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99538-108">PowerShell logs details of PowerShell operations.</span></span> <span data-ttu-id="99538-109">Например, PowerShell будет записывать в журнал такие операции, как запуск и остановка подсистемы, запуск и остановка поставщиков.</span><span class="sxs-lookup"><span data-stu-id="99538-109">For example, PowerShell will log operations such as starting and stopping the engine and starting and stopping providers.</span></span> <span data-ttu-id="99538-110">В нем также будут регистрироваться сведения о командах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99538-110">It will also log details about PowerShell commands.</span></span>

<span data-ttu-id="99538-111">Расположение журналов PowerShell зависит от целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="99538-111">The location of PowerShell logs is dependent on the target platform.</span></span> <span data-ttu-id="99538-112">В **Linux** можно использовать журналы PowerShell в **syslog** и **rsyslog. conf** .</span><span class="sxs-lookup"><span data-stu-id="99538-112">On **Linux** , PowerShell logs to **syslog** and **rsyslog.conf** can be used.</span></span> <span data-ttu-id="99538-113">Дополнительные сведения см. в разделе локальные страницы компьютера Linux `man` .</span><span class="sxs-lookup"><span data-stu-id="99538-113">For more information, refer to the Linux computer's local `man` pages.</span></span> <span data-ttu-id="99538-114">В **macOS** используется система ведения журнала **os_log** .</span><span class="sxs-lookup"><span data-stu-id="99538-114">On **macOS** , the **os_log** logging system is used.</span></span> <span data-ttu-id="99538-115">Дополнительные сведения см. в [документации разработчика os_log](https://developer.apple.com/documentation/os/os_log).</span><span class="sxs-lookup"><span data-stu-id="99538-115">For more information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

## <a name="viewing-powershell-log-output-on-linux"></a><span data-ttu-id="99538-116">Просмотр выходных данных журнала PowerShell в Linux</span><span class="sxs-lookup"><span data-stu-id="99538-116">Viewing PowerShell log output on Linux</span></span>

<span data-ttu-id="99538-117">Журналы PowerShell переносятся в **системный журнал** в Linux, а также могут использоваться все инструменты, которые обычно используются для просмотра содержимого **syslog** .</span><span class="sxs-lookup"><span data-stu-id="99538-117">PowerShell logs to **syslog** on Linux and any of the tools commonly used to view **syslog** contents may be used.</span></span>

<span data-ttu-id="99538-118">В формате записей журнала используется следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="99538-118">The format of the log entries uses the following template:</span></span>

```
TIMESTAMP MACHINENAME powershell[PID]: (COMMITID:TID:CID)
  [EVENTID:TASK.OPCODE.LEVEL] MESSAGE
```

|<span data-ttu-id="99538-119">Поле</span><span class="sxs-lookup"><span data-stu-id="99538-119">Field</span></span>        |<span data-ttu-id="99538-120">Описание</span><span class="sxs-lookup"><span data-stu-id="99538-120">Description</span></span>                                             |
|-------------|--------------------------------------------------------|
|`TIMESTAMP`  |<span data-ttu-id="99538-121">Дата и время, когда была создана запись журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-121">A date/time when the log entry was produced.</span></span>            |
|`MACHINENAME`|<span data-ttu-id="99538-122">Имя системы, в которой был создан журнал.</span><span class="sxs-lookup"><span data-stu-id="99538-122">The name of the system where the log was produced.</span></span>      |
|`PID`        |<span data-ttu-id="99538-123">Идентификатор процесса, который написал запись журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-123">The process ID of the process that wrote the log entry.</span></span> |
|`COMMITID`   |<span data-ttu-id="99538-124">`git commit`Идентификатор или тег, используемый для создания сборки.</span><span class="sxs-lookup"><span data-stu-id="99538-124">The `git commit` ID or tag used to produce the build.</span></span>   |
|`TID`        |<span data-ttu-id="99538-125">Идентификатор потока, который написал запись журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-125">The thread ID of the thread that wrote the log entry.</span></span>   |
|`CID`        |<span data-ttu-id="99538-126">Шестнадцатеричный идентификатор канала записи журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-126">The hex channel identifier of the log entry.</span></span>            |
|             |<span data-ttu-id="99538-127">10 = рабочий, 11 = аналитика</span><span class="sxs-lookup"><span data-stu-id="99538-127">10 = Operational, 11 = Analytic</span></span>                         |
|`EVENTID`    |<span data-ttu-id="99538-128">Идентификатор события записи журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-128">The event identifier of the log entry.</span></span>                  |
|`TASK`       |<span data-ttu-id="99538-129">Идентификатор задачи для записи события</span><span class="sxs-lookup"><span data-stu-id="99538-129">The task identifier for the event entry</span></span>                 |
|`OPCODE`     |<span data-ttu-id="99538-130">Код операции для записи события</span><span class="sxs-lookup"><span data-stu-id="99538-130">The opcode for the event entry</span></span>                          |
|`LEVEL`      |<span data-ttu-id="99538-131">Уровень ведения журнала для записи события</span><span class="sxs-lookup"><span data-stu-id="99538-131">The log level for the event entry</span></span>                       |
|`MESSAGE`    |<span data-ttu-id="99538-132">Сообщение, связанное с записью события</span><span class="sxs-lookup"><span data-stu-id="99538-132">The message associated with the event entry</span></span>             |

> [!NOTE]
> <span data-ttu-id="99538-133">`EVENTID`, `TASK` , `OPCODE` и `LEVEL` являются теми же значениями, которые используются при записи в журнал событий Windows.</span><span class="sxs-lookup"><span data-stu-id="99538-133">`EVENTID`, `TASK`, `OPCODE`, and `LEVEL` are the same values as used when logging to the Windows event log.</span></span>

### <a name="filtering-powershell-log-entries-using-rsyslog"></a><span data-ttu-id="99538-134">Фильтрация записей журнала PowerShell с помощью rsyslog</span><span class="sxs-lookup"><span data-stu-id="99538-134">Filtering PowerShell log entries using rsyslog</span></span>

<span data-ttu-id="99538-135">Обычно записи журнала PowerShell записываются в системный журнал по умолчанию `location/file` . **syslog**</span><span class="sxs-lookup"><span data-stu-id="99538-135">Normally, PowerShell log entries are written to the default `location/file` for **syslog**.</span></span> <span data-ttu-id="99538-136">Однако можно перенаправить записи в пользовательский файл.</span><span class="sxs-lookup"><span data-stu-id="99538-136">However, it's possible to redirect the entries to a custom file.</span></span>

1. <span data-ttu-id="99538-137">Создайте параметр conf для конфигурации журнала PowerShell и укажите число меньше 50 (для `50-default.conf` ), например `40-powershell.conf` .</span><span class="sxs-lookup"><span data-stu-id="99538-137">Create a conf for PowerShell log configuration and provide a number that's less than 50 (for `50-default.conf`), such as `40-powershell.conf`.</span></span> <span data-ttu-id="99538-138">Файл должен находиться в папке `/etc/rsyslog.d` .</span><span class="sxs-lookup"><span data-stu-id="99538-138">The file should be placed under `/etc/rsyslog.d`.</span></span>

1. <span data-ttu-id="99538-139">Добавьте следующую запись в файл:</span><span class="sxs-lookup"><span data-stu-id="99538-139">Add the following entry to the file:</span></span>

   ```
   :syslogtag, contains, "powershell[" /var/log/powershell.log
   & stop
   ```

1. <span data-ttu-id="99538-140">Убедитесь `/etc/rsyslog.conf` , что включен новый файл.</span><span class="sxs-lookup"><span data-stu-id="99538-140">Make sure `/etc/rsyslog.conf` includes the new file.</span></span> <span data-ttu-id="99538-141">Часто он будет иметь универсальную инструкцию include, которая выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99538-141">Often, it will have a generic include statement that looks like following configuration:</span></span>

   `$IncludeConfig /etc/rsyslog.d/*.conf`

   <span data-ttu-id="99538-142">В противном случае необходимо добавить инструкцию include вручную.</span><span class="sxs-lookup"><span data-stu-id="99538-142">If it doesn't, you'll need to add an include statement manually.</span></span>

1. <span data-ttu-id="99538-143">Убедитесь, что атрибуты и разрешения заданы соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="99538-143">Make sure attributes and permissions are set appropriately.</span></span>

   ```
   -rw-r--r-- 1 root root   67 Nov 28 12:51 40-powershell.conf
   ```

1. <span data-ttu-id="99538-144">Задайте для свойства владение значение **root**.</span><span class="sxs-lookup"><span data-stu-id="99538-144">Set ownership to **root**.</span></span>

   ```
   chown root:root /etc/rsyslog.d/40-powershell.conf
   ```

1. <span data-ttu-id="99538-145">Задать разрешения на доступ: **корневой** элемент доступен для чтения и записи, **Пользователи** читают.</span><span class="sxs-lookup"><span data-stu-id="99538-145">Set access permissions: **root** has read/write, **users** have read.</span></span>

   ```
   chmod 644 /etc/rsyslog.d/40-powershell.conf
   ```

## <a name="viewing-powershell-log-output-on-macos"></a><span data-ttu-id="99538-146">Просмотр выходных данных журнала PowerShell в macOS</span><span class="sxs-lookup"><span data-stu-id="99538-146">Viewing PowerShell log output on macOS</span></span>

<span data-ttu-id="99538-147">Самый простой способ просмотра выходных данных журнала PowerShell в macOS — использовать **консольное** приложение.</span><span class="sxs-lookup"><span data-stu-id="99538-147">The easiest method for viewing PowerShell log output on macOS is using the **Console** application.</span></span>

1. <span data-ttu-id="99538-148">Найдите **консольное** приложение и запустите его.</span><span class="sxs-lookup"><span data-stu-id="99538-148">Search for the **Console** application and launch it.</span></span>
1. <span data-ttu-id="99538-149">Выберите имя компьютера в разделе **устройства**.</span><span class="sxs-lookup"><span data-stu-id="99538-149">Select the Machine name under **Devices**.</span></span>
1. <span data-ttu-id="99538-150">В поле **поиска** введите `pwsh` для основного двоичного файла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99538-150">In the **Search** field, enter `pwsh` for the PowerShell main binary.</span></span>
1. <span data-ttu-id="99538-151">Измените фильтр поиска с `Any` на `Process` .</span><span class="sxs-lookup"><span data-stu-id="99538-151">Change the search filter from `Any` to `Process`.</span></span>
1. <span data-ttu-id="99538-152">Выполните операции.</span><span class="sxs-lookup"><span data-stu-id="99538-152">Perform the operations.</span></span>
1. <span data-ttu-id="99538-153">При необходимости сохраните Поиск для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="99538-153">Optionally, save the search for future use.</span></span>

<span data-ttu-id="99538-154">Чтобы выполнить фильтрацию по определенному экземпляру процесса PowerShell в **консоли** , ПЕРЕМЕННАЯ `$pid` содержит идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="99538-154">To filter on a specific process instance of PowerShell in the **Console** , the variable `$pid` contains the process ID.</span></span>

1. <span data-ttu-id="99538-155">В поле **поиска** введите **PID** (идентификатор процесса).</span><span class="sxs-lookup"><span data-stu-id="99538-155">Enter the **pid** (Process ID) in the **Search** field.</span></span>
1. <span data-ttu-id="99538-156">Измените фильтр поиска на `PID` .</span><span class="sxs-lookup"><span data-stu-id="99538-156">Change the search filter to `PID`.</span></span>
1. <span data-ttu-id="99538-157">Выполните операции.</span><span class="sxs-lookup"><span data-stu-id="99538-157">Perform the operations.</span></span>

### <a name="viewing-powershell-log-output-from-a-command-line"></a><span data-ttu-id="99538-158">Просмотр выходных данных журнала PowerShell из командной строки</span><span class="sxs-lookup"><span data-stu-id="99538-158">Viewing PowerShell log output from a command line</span></span>

<span data-ttu-id="99538-159">`log`Команду можно использовать для просмотра записей журнала PowerShell из командной строки.</span><span class="sxs-lookup"><span data-stu-id="99538-159">The `log` command can be used to view PowerShell log entries from the command line.</span></span>

```
sudo log stream --predicate 'process == "pwsh"' --info
```

### <a name="persisting-powershell-log-output"></a><span data-ttu-id="99538-160">Сохранение выходных данных журнала PowerShell</span><span class="sxs-lookup"><span data-stu-id="99538-160">Persisting PowerShell log output</span></span>

<span data-ttu-id="99538-161">По умолчанию PowerShell использует ведение журнала только для памяти по умолчанию в macOS.</span><span class="sxs-lookup"><span data-stu-id="99538-161">By default, PowerShell uses the default memory-only logging on macOS.</span></span> <span data-ttu-id="99538-162">Это поведение можно изменить для включения сохраняемости с помощью `log config` команды.</span><span class="sxs-lookup"><span data-stu-id="99538-162">This behavior can be changed to enable persistence using the `log config` command.</span></span>

<span data-ttu-id="99538-163">Следующий скрипт включает ведение журнала на уровне информации и сохраняемость:</span><span class="sxs-lookup"><span data-stu-id="99538-163">The following script enables info level logging and persistence:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:info,level:info
```

<span data-ttu-id="99538-164">Следующая команда возвращает журнал PowerShell в состояние по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="99538-164">The following command reverts PowerShell logging to the default state:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:default,level:default
```

<span data-ttu-id="99538-165">После включения сохраняемости `log show` команда может использоваться для экспорта элементов журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-165">After persistence is enabled, the `log show` command can be used to export log items.</span></span> <span data-ttu-id="99538-166">Команда предоставляет параметры для экспорта последних N элементов, элементов с момента заданного времени или элементов за заданный промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="99538-166">The command provides options for exporting the last N items, items since a given time, or items within a given time span.</span></span>

<span data-ttu-id="99538-167">Например, следующая команда экспортирует элементы, начиная с `9am on April 5 of 2018` :</span><span class="sxs-lookup"><span data-stu-id="99538-167">For example, the following command exports items since `9am on April 5 of 2018`:</span></span>

```
log show --info --start "2018-04-05 09:00:00" --predicate "process = 'pwsh'"
```

<span data-ttu-id="99538-168">Справку по можно получить `log` , выполнив дополнительные `log show --help` сведения.</span><span class="sxs-lookup"><span data-stu-id="99538-168">You can get help for `log` by running `log show --help` for additional details.</span></span>

> [!TIP]
> <span data-ttu-id="99538-169">При выполнении любой команды журнала в командной строке или сценарии PowerShell следует использовать двойные кавычки вокруг всей строки предиката и одинарные кавычки в.</span><span class="sxs-lookup"><span data-stu-id="99538-169">When executing any of the log commands from a PowerShell prompt or script, use double quotes around the entire predicate string and single quotes within.</span></span> <span data-ttu-id="99538-170">Это позволяет избежать необходимости в экранировании символов двойных кавычек в строке предиката.</span><span class="sxs-lookup"><span data-stu-id="99538-170">This avoids the need to escape double quote characters within the predicate string.</span></span>

<span data-ttu-id="99538-171">Также можно сохранить журналы событий в более безопасном месте, например в центральном сборщике журналов событий или [SIEM][] агрегаторе.</span><span class="sxs-lookup"><span data-stu-id="99538-171">You may also want to consider saving the event logs to a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="99538-172">Вы можете настроить SIEM в Azure.</span><span class="sxs-lookup"><span data-stu-id="99538-172">You can set up SIEM in Azure.</span></span> <span data-ttu-id="99538-173">Дополнительные сведения см. в разделе [Универсальная интеграция SIEM](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="99538-173">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

## <a name="configuring-logging-on-a-non-windows-system"></a><span data-ttu-id="99538-174">Настройка ведения журнала в системе, отличной от Windows</span><span class="sxs-lookup"><span data-stu-id="99538-174">Configuring logging on a non-Windows system</span></span>

<span data-ttu-id="99538-175">В Windows ведение журнала настраивается путем создания прослушивателей трассировки событий Windows или с помощью Просмотр событий для включения аналитического ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-175">On Windows, logging is configured by creating ETW trace listeners or by using the Event Viewer to enable Analytic logging.</span></span> <span data-ttu-id="99538-176">В Linux и macOS ведение журнала настраивается с помощью файла `powershell.config.json` .</span><span class="sxs-lookup"><span data-stu-id="99538-176">On Linux and macOS, logging is configured using the file `powershell.config.json`.</span></span> <span data-ttu-id="99538-177">В оставшейся части этого раздела обсуждается настройка ведения журнала PowerShell в системе, отличной от Windows.</span><span class="sxs-lookup"><span data-stu-id="99538-177">The rest of this section will discuss configuring PowerShell logging on a non-Windows system.</span></span>

<span data-ttu-id="99538-178">По умолчанию PowerShell включает информационное ведение журнала в операционный канал.</span><span class="sxs-lookup"><span data-stu-id="99538-178">By default, PowerShell enables informational logging to the operational channel.</span></span> <span data-ttu-id="99538-179">Это означает, что все выходные данные журнала, созданные PowerShell, помеченные как работоспособные и имеющие уровень журнала (Trace) больше информационного уровня, будут занесены в журнал.</span><span class="sxs-lookup"><span data-stu-id="99538-179">What this means is any log output produced by PowerShell that is marked as operational and has a log (trace) level greater than informational will be logged.</span></span> <span data-ttu-id="99538-180">Иногда для диагностики может потребоваться дополнительный вывод журнала, например подробный вывод журнала или включение аналитического вывода журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-180">Occasionally, diagnoses may require additional log output, such as verbose log output or enabling analytic log output.</span></span>

<span data-ttu-id="99538-181">Файл `powershell.config.json` представляет собой отформатированный **JSON** -файл, находящийся в `$PSHOME` каталоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99538-181">The file `powershell.config.json` is a **JSON** formatted file residing in the PowerShell `$PSHOME` directory.</span></span> <span data-ttu-id="99538-182">Каждая установка PowerShell использует собственную копию этого файла.</span><span class="sxs-lookup"><span data-stu-id="99538-182">Each installation of PowerShell uses its own copy of this file.</span></span> <span data-ttu-id="99538-183">Для нормальной работы этот файл остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="99538-183">For normal operation, this file is left unchanged.</span></span> <span data-ttu-id="99538-184">Хотя это может быть полезно, для изменения некоторых параметров в файле для диагностики или различения нескольких версий PowerShell в одной системе или даже нескольких копиях одной и той же версии (см `LogIdentity` . в таблице ниже).</span><span class="sxs-lookup"><span data-stu-id="99538-184">Although it can be useful, to change some of the settings in the file, for diagnosis or for distinguishing between multiple PowerShell versions on the same system or even multiple copies of the same version (See `LogIdentity` in the table below).</span></span>

<span data-ttu-id="99538-185">Следующий код является примером конфигурации:</span><span class="sxs-lookup"><span data-stu-id="99538-185">The following code is an example configuration:</span></span>

```json
{
  "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned",
  "PowerShellPolicies": {
    "ScriptExecution": {
      "ExecutionPolicy": "RemoteSigned",
      "EnableScripts": true
    },
    "ScriptBlockLogging": {
      "EnableScriptBlockInvocationLogging": true,
      "EnableScriptBlockLogging": true
    },
    "ModuleLogging": {
      "EnableModuleLogging": false,
      "ModuleNames": [
        "PSReadline",
        "PowerShellGet"
      ]
    },
    "ProtectedEventLogging": {
      "EnableProtectedEventLogging": false,
      "EncryptionCertificate": [
        "Joe"
      ]
    },
    "Transcription": {
      "EnableTranscripting": true,
      "EnableInvocationHeader": true,
      "OutputDirectory": "F:\\tmp\\new"
    },
    "UpdatableHelp": {
      "DefaultSourcePath": "f:\\temp"
    },
    "ConsoleSessionConfiguration": {
      "EnableConsoleSessionConfiguration": false,
      "ConsoleSessionConfigurationName": "name"
    }
  },
  "LogLevel": "verbose"
}
```

<span data-ttu-id="99538-186">Свойства для настройки ведения журнала PowerShell перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="99538-186">The properties for configuring PowerShell logging are listed in the following table.</span></span> <span data-ttu-id="99538-187">Значения, отмеченные звездочкой (например `Operational*` ,), указывают значение по умолчанию, если в файле не указано значение.</span><span class="sxs-lookup"><span data-stu-id="99538-187">Values marked with an asterisk, such as `Operational*`, indicate the default value when no value is provided in the file.</span></span>

|<span data-ttu-id="99538-188">Свойство.</span><span class="sxs-lookup"><span data-stu-id="99538-188">Property</span></span>   |<span data-ttu-id="99538-189">Значения</span><span class="sxs-lookup"><span data-stu-id="99538-189">Values</span></span>        |<span data-ttu-id="99538-190">Описание</span><span class="sxs-lookup"><span data-stu-id="99538-190">Description</span></span>                                  |
|-----------|--------------|---------------------------------------------|
|`LogIdentity`|<span data-ttu-id="99538-191">(имя строки)</span><span class="sxs-lookup"><span data-stu-id="99538-191">(string name)</span></span> |<span data-ttu-id="99538-192">Имя, используемое при ведении журнала.</span><span class="sxs-lookup"><span data-stu-id="99538-192">The name to use when logging.</span></span> <span data-ttu-id="99538-193">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="99538-193">By default,</span></span>  |
|           |<span data-ttu-id="99538-194">оболочк</span><span class="sxs-lookup"><span data-stu-id="99538-194">powershell\*</span></span>   |<span data-ttu-id="99538-195">идентификатором является PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99538-195">powershell is the identity.</span></span> <span data-ttu-id="99538-196">Это значение может быть</span><span class="sxs-lookup"><span data-stu-id="99538-196">This value can be</span></span>|
|           |              |<span data-ttu-id="99538-197">используется для определения разницы между двумя</span><span class="sxs-lookup"><span data-stu-id="99538-197">used to tell the difference between two</span></span>      |
|           |              |<span data-ttu-id="99538-198">экземпляры установки PowerShell, такие как</span><span class="sxs-lookup"><span data-stu-id="99538-198">instances of a PowerShell installation, such</span></span> |
|           |              |<span data-ttu-id="99538-199">в качестве выпуска и бета-версии.</span><span class="sxs-lookup"><span data-stu-id="99538-199">as a release and beta version.</span></span> <span data-ttu-id="99538-200">Это значение равно</span><span class="sxs-lookup"><span data-stu-id="99538-200">This value is</span></span> |
|           |              |<span data-ttu-id="99538-201">также используется для перенаправления выходных данных журнала в</span><span class="sxs-lookup"><span data-stu-id="99538-201">also used to redirect log output to a</span></span>        |
|           |              |<span data-ttu-id="99538-202">отдельный файл в Linux.</span><span class="sxs-lookup"><span data-stu-id="99538-202">separate file on Linux.</span></span> <span data-ttu-id="99538-203">См. обсуждение</span><span class="sxs-lookup"><span data-stu-id="99538-203">See the discussion of</span></span>|
|           |              |<span data-ttu-id="99538-204">**rsyslog** выше.</span><span class="sxs-lookup"><span data-stu-id="99538-204">**rsyslog** above.</span></span>                           |
|`LogChannels`|<span data-ttu-id="99538-205">Рабочего</span><span class="sxs-lookup"><span data-stu-id="99538-205">Operational\*</span></span>  |<span data-ttu-id="99538-206">Включенные каналы.</span><span class="sxs-lookup"><span data-stu-id="99538-206">The channels to enable.</span></span> <span data-ttu-id="99538-207">Разделите значения</span><span class="sxs-lookup"><span data-stu-id="99538-207">Separate the values</span></span>|
|           |<span data-ttu-id="99538-208">Аналитический</span><span class="sxs-lookup"><span data-stu-id="99538-208">Analytic</span></span>      |<span data-ttu-id="99538-209">с запятой при указании более одного параметра.</span><span class="sxs-lookup"><span data-stu-id="99538-209">with a comma when specifying more than one.</span></span>  |
|`LogLevel`   |<span data-ttu-id="99538-210">Всегда</span><span class="sxs-lookup"><span data-stu-id="99538-210">Always</span></span>        |<span data-ttu-id="99538-211">Укажите одно значение.</span><span class="sxs-lookup"><span data-stu-id="99538-211">Specify a single value.</span></span> <span data-ttu-id="99538-212">Значение включает</span><span class="sxs-lookup"><span data-stu-id="99538-212">The value enables</span></span>  |
|           |<span data-ttu-id="99538-213">Критически важно</span><span class="sxs-lookup"><span data-stu-id="99538-213">Critical</span></span>      |<span data-ttu-id="99538-214">и все значения, приведенные выше в</span><span class="sxs-lookup"><span data-stu-id="99538-214">itself and all values above it in the</span></span>        |
|           |<span data-ttu-id="99538-215">Ошибка</span><span class="sxs-lookup"><span data-stu-id="99538-215">Error</span></span>         |<span data-ttu-id="99538-216">в списке слева.</span><span class="sxs-lookup"><span data-stu-id="99538-216">list to the left.</span></span>                            |
|           |<span data-ttu-id="99538-217">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="99538-217">Warning</span></span>       |                                             |
|           |<span data-ttu-id="99538-218">Извещен</span><span class="sxs-lookup"><span data-stu-id="99538-218">Informational\*</span></span>|                                             |
|           |<span data-ttu-id="99538-219">Подробный</span><span class="sxs-lookup"><span data-stu-id="99538-219">Verbose</span></span>       |                                             |
|           |<span data-ttu-id="99538-220">Отладка</span><span class="sxs-lookup"><span data-stu-id="99538-220">Debug</span></span>         |                                             |
|`LogKeywords`|<span data-ttu-id="99538-221">Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="99538-221">Runspace</span></span>      |<span data-ttu-id="99538-222">Ключевые слова обеспечивают возможность ограничения ведения журнала</span><span class="sxs-lookup"><span data-stu-id="99538-222">Keywords provide the ability to limit logging</span></span>|
|           |<span data-ttu-id="99538-223">Pipeline</span><span class="sxs-lookup"><span data-stu-id="99538-223">Pipeline</span></span>      |<span data-ttu-id="99538-224">для конкретных компонентов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99538-224">to specific components within PowerShell.</span></span> <span data-ttu-id="99538-225">на</span><span class="sxs-lookup"><span data-stu-id="99538-225">By</span></span> |
|           |<span data-ttu-id="99538-226">Протокол</span><span class="sxs-lookup"><span data-stu-id="99538-226">Protocol</span></span>      |<span data-ttu-id="99538-227">по умолчанию все ключевые слова включены и изменены.</span><span class="sxs-lookup"><span data-stu-id="99538-227">default, all keywords are enabled and change</span></span> |
|           |<span data-ttu-id="99538-228">Транспорт</span><span class="sxs-lookup"><span data-stu-id="99538-228">Transport</span></span>     |<span data-ttu-id="99538-229">Это значение полезно только для очень</span><span class="sxs-lookup"><span data-stu-id="99538-229">this value is only useful for very</span></span>           |
|           |<span data-ttu-id="99538-230">Узел</span><span class="sxs-lookup"><span data-stu-id="99538-230">Host</span></span>          |<span data-ttu-id="99538-231">специализированные способы устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="99538-231">specialized troubleshooting.</span></span>                |
|           |<span data-ttu-id="99538-232">Командлеты</span><span class="sxs-lookup"><span data-stu-id="99538-232">Cmdlets</span></span>       |                                             |
|           |<span data-ttu-id="99538-233">serializer</span><span class="sxs-lookup"><span data-stu-id="99538-233">Serializer</span></span>    |                                             |
|           |<span data-ttu-id="99538-234">Сеанс</span><span class="sxs-lookup"><span data-stu-id="99538-234">Session</span></span>       |                                             |
|           |<span data-ttu-id="99538-235">манажедплугин</span><span class="sxs-lookup"><span data-stu-id="99538-235">ManagedPlugin</span></span> |                                             |

## <a name="see-also"></a><span data-ttu-id="99538-236">См. также</span><span class="sxs-lookup"><span data-stu-id="99538-236">See also</span></span>

<span data-ttu-id="99538-237">Сведения о **syslog** и **rsyslog. conf** для Linux см. на локальных страницах компьютера Linux `man` .</span><span class="sxs-lookup"><span data-stu-id="99538-237">For Linux **syslog** and **rsyslog.conf** information, refer to the Linux computer's local `man` pages.</span></span>

<span data-ttu-id="99538-238">Сведения о **Os_log** macOS см. в [документации по os_log разработчиков](https://developer.apple.com/documentation/os/os_log).</span><span class="sxs-lookup"><span data-stu-id="99538-238">For macOS **os_log** information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

[<span data-ttu-id="99538-239">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="99538-239">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="99538-240">Универсальная интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="99538-240">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
