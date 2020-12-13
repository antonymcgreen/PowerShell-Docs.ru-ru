---
ms.date: 09/07/2018
ms.topic: reference
title: Утвержденные команды для PowerShell
description: Утвержденные команды для PowerShell
ms.openlocfilehash: fc1ff989ae86862e0f9cc24d8bcba2ff02ef68cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355108"
---
# <a name="approved-verbs-for-powershell-commands"></a>Утвержденные команды для PowerShell

В PowerShell для имен командлетов и производных классов .NET используются пары из глагола и существительного.
Глагол указывает на действие, выполняемое командлетом. Существительное указывает на объект, с которым выполняется действие. Например, командлет `Get-Command` извлекает все команды, зарегистрированные в PowerShell.

> [!NOTE]
> PowerShell использует термин _глагол_ для обозначения слова, которое подразумевает действие, даже если это слово не является глаголом в лингвистическом смысле. Например, термин _New_ считается в PowerShell глаголом, так как подразумевает действие, хотя в переводе это слово означает "новый" и не является глаголом.

У каждой утвержденной команды есть соответствующий _префикс псевдонима_. Мы используем префикс псевдонима в псевдонимах для команд, использующих эту команду. Например, префикс псевдонима для `Import` — `ip`, а для `Import-Module` — `ipmo`. Это рекомендация, а не правило. В частности, эту рекомендацию не нужно учитывать для псевдонимов команд, копирующих хорошо известные команды из других сред.

## <a name="verb-naming-recommendations"></a>Рекомендации по именованию команд

Следующие рекомендации помогут выбрать подходящую команду для командлета, чтобы обеспечить согласованность между создаваемыми вами командлетами, командлетами, предоставляемыми PowerShell, и командлетами, разработанными другими пользователями.

- Используйте одно из стандартных имен команд, предоставленных PowerShell.
- Используйте команду, чтобы описать общую область действия, и параметры для уточнения действия командлета.
- Не используйте синоним утвержденной команды. Например, всегда используйте `Remove`, а не `Delete` или `Eliminate`.
- Используйте команду только в той форме, которая указана в этом разделе. Например, используйте `Get`, но не `Getting` или `Gets`.
- Не используйте следующие зарезервированные команды или псевдонимы. Язык PowerShell и лишь некоторые из его командлетов используют эти команды в исключительных обстоятельствах.
  - ForEach (foreach)
  - [Format](/dotnet/api/System.Management.Automation.VerbsCommon.Format) (f): упорядочивает объекты в указанной форме или макете
  - [Group](/dotnet/api/System.Management.Automation.VerbsData.Group) (gp): упорядочивает или связывает один или несколько ресурсов
  - [Ping](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Ping) (pi)
  - Sort (sr)
  - Tee (te)
  - Where (wh)

Полный список команд можно получить с помощью командлета `Get-Verb`.

## <a name="similar-verbs-for-different-actions"></a>Похожие команды для различных действий

Следующие похожие команды представляют различные действия.

### <a name="new-vs-set"></a>New и Присвойте параметру

Чтобы создать новый ресурс, используйте команду `New`. Используйте команду `Set`, чтобы изменить существующий ресурс, при необходимости создав его, если он не существует, например командлет `Set-Variable`.

### <a name="find-vs-search"></a>Find и Поиск

Используйте команду `Find` для поиска объекта. Используйте команду `Search`, чтобы создать ссылку на ресурс в контейнере.

### <a name="get-vs-read"></a>Get и Чтение

Используйте команду `Get` для получения сведений о ресурсе (например, файле) или объекта, с помощью которого можно получить доступ к ресурсу в будущем. Используйте команду `Read`, чтобы открыть ресурс или извлечь сведения, содержащиеся в нем.

### <a name="invoke-vs-start"></a>Invoke и Запуск

Используйте команду `Invoke` для выполнения синхронных операций, таких как выполнение команды и ожидание ее завершения. Для запуска асинхронных операций, таких как выполнение автономного процесса, используется команда `Start`.

### <a name="ping-vs-test"></a>Ping и Тест

Используйте команду `Test`.

## <a name="common-verbs"></a>Распространенные команды

PowerShell использует класс перечисления [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon) для определения общих действий, которые могут применяться практически к любому командлету. В следующей таблице перечислено большинство определенных команд.

|Команда (псевдоним)|Действие|Неподходящие синонимы|
|--------------------|------------|--------------|
|[Add](/dotnet/api/System.Management.Automation.VerbsCommon.Add) (a)|Добавляет ресурс в контейнер или прикрепляет один элемент к другому. Например, командлет `Add-Content` добавляет содержимое в файл. Эта команда образует пару с командой `Remove`.|Append, Attach, Concatenate, Insert|
|[Clear](/dotnet/api/System.Management.Automation.VerbsCommon.Clear) (cl)|Удаляет все ресурсы из контейнера, но не удаляет сам контейнер. Например, командлет `Clear-Content` удаляет содержимое файла, но не удаляет файл.|Flush, Erase, Release, Unmark, Unset, Nullify|
|[Close](/dotnet/api/System.Management.Automation.VerbsCommon.Close) (cs)|Изменяет состояние ресурса, чтобы сделать его недоступным или непригодным для использования. Эта команда образует пару с командой `Open.`.||
|[Copy](/dotnet/api/System.Management.Automation.VerbsCommon.Copy) (cp)|Копирует ресурс в другое имя или другой контейнер. Например, командлет `Copy-Item` копирует элемент (такой, как файл) из одного расположения в хранилище данных в другое расположение.|Duplicate, Clone, Replicate, Sync|
|[Enter](/dotnet/api/System.Management.Automation.VerbsCommon.Enter) (et)|Указывает действие, которое позволяет пользователю переместиться в ресурс. Например, командлет `Enter-PSSession` помещает пользователя в интерактивный сеанс. Эта команда образует пару с командой `Exit`.|Push, Into|
|[Exit](/dotnet/api/System.Management.Automation.VerbsCommon.Exit) (ex)|Переходит к последнему использованному окружению или контексту. Например, командлет `Exit-PSSession` помещает пользователя в сеанс, который использовался для запуска интерактивного сеанса. Эта команда образует пару с командой `Enter`.|Pop, Out|
|[Find](/dotnet/api/System.Management.Automation.VerbsCommon.Find) (fd)|Ищет в контейнере объект, который является неизвестным, подразумеваемым, необязательным или указанным.|Поиск|
|[Get](/dotnet/api/System.Management.Automation.VerbsCommon.Get) (g)|Указывает действие, которое извлекает ресурс. Эта команда образует пару с командой `Set`.|Read, Open, Cat, Type, Dir, Obtain, Dump, Acquire, Examine, Find, Search|
|[Hide](/dotnet/api/System.Management.Automation.VerbsCommon.Hide) (h)|Делает ресурс недоступным для обнаружения. Например, командлет, имя которого включает команду Hide, может скрывать службу от пользователя. Эта команда образует пару с командой `Show`.|Блокировать|
|[Join](/dotnet/api/System.Management.Automation.VerbsCommon.Join) (j)|Объединяет ресурсы в один ресурс. Например, командлет `Join-Path` объединяет путь с одним из его дочерних путей для создания единого пути. Эта команда образует пару с командой `Split`.|Combine, Unite, Connect, Associate|
|[Lock](/dotnet/api/System.Management.Automation.VerbsCommon.Lock) (lk)|Защищает ресурс. Эта команда образует пару с командой `Unlock`.|Restrict, Secure|
|[Move](/dotnet/api/System.Management.Automation.VerbsCommon.Move) (m)|Перемещает ресурс из одного места в другое. Например, командлет `Move-Item` перемещает элемент из одного расположения в хранилище данных в другое расположение.|Transfer, Name, Migrate|
|[New](/dotnet/api/System.Management.Automation.VerbsCommon.New) (n)|Создает ресурс. (Команда `Set` может также использоваться при создании ресурса, включающего данные, например командлет `Set-Variable`.)|Create, Generate, Build, Make, Allocate|
|[Open](/dotnet/api/System.Management.Automation.VerbsCommon.Open) (op)|Изменяет состояние ресурса, чтобы сделать его доступным или пригодным для использования. Эта команда образует пару с командой `Close`.||
|[Optimize](/dotnet/api/System.Management.Automation.VerbsCommon.Optimize) (om)|Повышает эффективность ресурса.||
|[Pop](/dotnet/api/System.Management.Automation.VerbsCommon.Pop) (pop)|Удаляет элемент из верхней части стека. Например, командлет `Pop-Location` меняет текущее расположение на указанное в последней записи стека.||
|[Push](/dotnet/api/System.Management.Automation.VerbsCommon.Push) (pu)|Добавляет элемент в верхнюю часть стека. Например, командлет `Push-Location` помещает текущее расположение в стек.||
|[Redo](/dotnet/api/System.Management.Automation.VerbsCommon.Redo) (re)|Сбрасывает ресурс до состояния, которое было отменено.||
|[Remove](/dotnet/api/System.Management.Automation.VerbsCommon.Remove) (r)|Удаляет ресурс из контейнера. Например, командлет `Remove-Variable` удаляет переменную и ее значение. Эта команда образует пару с командой `Add`.|Clear, Cut, Dispose, Discard, Erase|
|[Rename](/dotnet/api/System.Management.Automation.VerbsCommon.Rename) (rn)|Изменяет имя ресурса. Например, командлет `Rename-Item`, используемый для доступа к сохраненным данным, изменяет имя элемента в хранилище данных.|Change|
|[Reset](/dotnet/api/System.Management.Automation.VerbsCommon.Reset) (rs)|Присваивает ресурсу исходное состояние.||
|[Resize](/dotnet/api/System.Management.Automation.VerbsCommon.Resize)(rz)|Изменяет размер ресурса.||
|[Search](/dotnet/api/System.Management.Automation.VerbsCommon.Search) (sr)|Создает ссылку на ресурс в контейнере.|Find, Locate|
|[Select](/dotnet/api/System.Management.Automation.VerbsCommon.Select) (sc)|Находит ресурс в контейнере. Например, командлет `Select-String` находит текст в строках и файлах.|Find, Locate|
|[Set](/dotnet/api/System.Management.Automation.VerbsCommon.Set) (s)|Заменяет данные существующего ресурса или создает ресурс, содержащий некоторые данные. Например, командлет `Set-Date` изменяет системное время на локальном компьютере. (Для создания ресурса можно также использовать команду `New`.) Эта команда образует пару с командой `Get`.|Write, Reset, Assign, Configure|
|[Show](/dotnet/api/System.Management.Automation.VerbsCommon.Show) (sh)|Делает ресурс видимым для пользователя. Эта команда образует пару с командой `Hide`.|Display, Produce|
|[Skip](/dotnet/api/System.Management.Automation.VerbsCommon.Skip) (sk)|Обходит один или несколько ресурсов или точек в последовательности.|Bypass, Jump|
|[Split](/dotnet/api/System.Management.Automation.VerbsCommon.Split) (sl)|Разделяет части ресурса. Например, командлет `Split-Path` возвращает различные части пути. Эта команда образует пару с командой `Join`.|Отдельные|
|[Step](/dotnet/api/System.Management.Automation.VerbsCommon.Step) (st)|Переходит к следующей точке или ресурсу в последовательности.||
|[Switch](/dotnet/api/System.Management.Automation.VerbsCommon.Switch) (sw)|Указывает действие, которое обозначает смену между двумя ресурсами, например переход между двумя расположениями, обязанностями или состояниями.||
|[Undo](/dotnet/api/System.Management.Automation.VerbsCommon.Undo) (un)|Задает для ресурса предыдущее состояние.||
|[Unlock](/dotnet/api/System.Management.Automation.VerbsCommon.Unlock) (uk)|Освобождает заблокированный ресурс. Эта команда образует пару с командой `Lock`.|Release, Unrestrict, Unsecure|
|[Watch](/dotnet/api/System.Management.Automation.VerbsCommon.Watch) (wc)|Постоянно проверяет или отслеживает изменения в ресурсе.||

## <a name="communications-verbs"></a>Команды для обмена данными

PowerShell использует класс [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications) для определения действий, которые применяются к обмену данными. В следующей таблице перечислено большинство определенных команд.

|Команда (псевдоним)|Действие|Неподходящие синонимы|
|--------------------|------------|--------------|
|[Connect](/dotnet/api/System.Management.Automation.VerbsCommunications.Connect) (cc)|Создает связь между источником и назначением. Эта команда образует пару с командой `Disconnect`.|Join, Telnet|
|[Disconnect](/dotnet/api/System.Management.Automation.VerbsCommunications.Disconnect) (dc)|Удаляет связь между источником и назначением. Эта команда образует пару с командой `Connect`.|Break, Logoff|
|[Read](/dotnet/api/System.Management.Automation.VerbsCommunications.Read) (rd)|Получает сведения из источника. Эта команда образует пару с командой `Write`.|Acquire, Prompt, Get|
|[Receive](/dotnet/api/System.Management.Automation.VerbsCommunications.Receive) (rc)|Принимает сведения, отправляемые из источника. Эта команда образует пару с командой `Send`.|Read, Accept, Peek|
|[Send](/dotnet/api/System.Management.Automation.VerbsCommunications.Send) (sd)|Доставляет сведения в место назначения. Эта команда образует пару с командой `Receive`.|Put, Broadcast, Mail, Fax|
|[Write](/dotnet/api/System.Management.Automation.VerbsCommunications.Write) (wr)|Добавляет сведения в целевой объект. Эта команда образует пару с командой `Read`.|Put, Print|

## <a name="data-verbs"></a>Команды для работы с данными

PowerShell использует класс [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData) для определения действий, которые применяются к обработке данных. В следующей таблице перечислено большинство определенных команд.

|Имя команды (псевдоним)|Действие|Неподходящие синонимы|
|-------------------------|------------|--------------|
|[Backup](/dotnet/api/System.Management.Automation.VerbsData.Backup) (ba)|Сохраняет данные путем репликации.|Save, Burn, Replicate, Sync|
|[Checkpoint](/dotnet/api/System.Management.Automation.VerbsData.Checkpoint) (ch)|Создает моментальный снимок текущего состояния данных или их конфигурации.|Поиск различий|
|[Compare](/dotnet/api/System.Management.Automation.VerbsData.Compare) (cr)|Сравнивает данные из одного ресурса с данными из другого.|Поиск различий|
|[Compress](/dotnet/api/System.Management.Automation.VerbsData.Compress) (cm)|Сжимает данные ресурса. Образует пару с командой `Expand`.|Компактный|
|[Convert](/dotnet/api/System.Management.Automation.VerbsData.Convert) (cv)|Изменяет данные из одного представления в другое, если командлет поддерживает двунаправленное преобразование или преобразование между несколькими типами данных.|Change, Resize, Resample|
|[ConvertFrom](/dotnet/api/System.Management.Automation.VerbsData.ConvertFrom) (cf)|Преобразует один первичный тип входных данных (существительное в командлете указывает входные данные) в один или несколько поддерживаемых типов выходных данных.|Export, Output, Out|
|[ConvertTo](/dotnet/api/System.Management.Automation.VerbsData.ConvertTo) (ct)|Преобразует один или несколько типов входных данных в основной тип выходных данных (существительное в командлете указывает тип выходных данных).|Import, Input, In|
|[Dismount](/dotnet/api/System.Management.Automation.VerbsData.Dismount) (dm)|Отключает именованную сущность от расположения. Эта команда образует пару с командой `Mount`.|Unmount, Unlink|
|[Edit](/dotnet/api/System.Management.Automation.VerbsData.Edit) (ed)|Изменяет существующие данные путем добавления или удаления содержимого.|Change, Update, Modify|
|[Expand](/dotnet/api/System.Management.Automation.VerbsData.Expand) (en)|Восстанавливает сжатые данные ресурса до исходного состояния. Эта команда образует пару с командой `Compress`.|Explode, Uncompress|
|[Export](/dotnet/api/System.Management.Automation.VerbsData.Export) (ep)|Инкапсулирует первичные входные данные в постоянное хранилище данных, например файл, или в формат обмена. Эта команда образует пару с командой `Import`.|Extract, Backup|
|[Import](/dotnet/api/System.Management.Automation.VerbsData.Import) (ip)|Создает ресурс на основе данных, хранящихся в постоянном хранилище данных (например, в файле) или в формате обмена. Например, командлет `Import-CSV` импортирует данные из файла с разделителями-запятыми (CSV) в объекты, которые могут использоваться другими командлетами. Эта команда образует пару с командой `Export`.|BulkLoad, Load|
|[Initialize](/dotnet/api/System.Management.Automation.VerbsData.Initialize) (in)|Подготавливает ресурс для использования и задает для него состояние по умолчанию.|Erase, Init, Renew, Rebuild, Reinitialize, Setup|
|[Limit](/dotnet/api/System.Management.Automation.VerbsData.Limit) (l)|Применяет ограничения к ресурсу.|Quota|
|[Merge](/dotnet/api/System.Management.Automation.VerbsData.Merge) (mg)|Создает один ресурс из нескольких.|Combine, Join|
|[Mount](/dotnet/api/System.Management.Automation.VerbsData.Mount) (mt)|Подключает именованную сущность к расположению. Эта команда образует пару с командой `Dismount`.|Подключение|
|[Out](/dotnet/api/System.Management.Automation.VerbsData.Out) (o)|Отправляет данные из среды. Например, командлет `Out-Printer` отправляет данные на принтер.||
|[Publish](/dotnet/api/System.Management.Automation.VerbsData.Publish) (pb)|Делает ресурс доступным для других пользователей. Эта команда образует пару с командой `Unpublish`.|Deploy, Release, Install|
|[Restore](/dotnet/api/System.Management.Automation.VerbsData.Restore) (rr)|Задает для ресурса предопределенное состояние, например состояние, заданное `Checkpoint`. Например, командлет `Restore-Computer` запускает восстановление системы на локальном компьютере.|Repair, Return, Undo, Fix|
|[Save](/dotnet/api/System.Management.Automation.VerbsData.Save) (sv)|Сохраняет данные, чтобы избежать их потери.||
|[Sync](/dotnet/api/System.Management.Automation.VerbsData.Sync) (sy)|Гарантирует, что два ресурса или более находятся в одном и том же состоянии.|Replicate, Coerce, Match|
|[Unpublish](/dotnet/api/System.Management.Automation.VerbsData.Unpublish) (ub)|Делает ресурс недоступным для других пользователей. Эта команда образует пару с командой `Publish`.|Uninstall, Revert, Hide|
|[Update](/dotnet/api/System.Management.Automation.VerbsData.Update) (ud)|Обеспечивает актуальность ресурса для поддержания его состояния, точности, согласованности или соответствия требованиям. Например, командлет `Update-FormatData` обновляет и добавляет файлы форматирования в текущую консоль PowerShell.|Refresh, Renew, Recalculate, Re-index|

## <a name="diagnostic-verbs"></a>Команды диагностики

PowerShell использует класс [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic) для определения действий, которые применяются к обработке данных. В следующей таблице перечислено большинство определенных команд.

|Команда (псевдоним)|Действие|Неподходящие синонимы|
|--------------------|------------|--------------|
|[Debug](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Debug) (db)|Изучает ресурс для диагностики проблем в работе.|Диагностика|
|[Measure](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Measure) (ms)|Определяет ресурсы, используемые указанной операцией, или получает статистику по ресурсу.|Calculate, Determine, Analyze|
|[Repair](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Repair) (rp)|Восстанавливает ресурс в пригодном для использования состоянии.|Fix, Restore|
|[Resolve](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Resolve) (rv)|Сопоставляет сокращенное представление ресурса с более полным представлением.|Expand, Determine|
|[Test](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Test) (t)|Проверяет операцию или согласованность ресурса.|Diagnose, Analyze, Salvage, Verify|
|[Trace](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Trace) (tr)|Отслеживает действия ресурса.|Track, Follow, Inspect, Dig|

## <a name="lifecycle-verbs"></a>Команды жизненного цикла

PowerShell использует класс [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) для определения действий, которые применяются к жизненному циклу ресурса. В следующей таблице перечислено большинство определенных команд.

|Команда (псевдоним)|Действие|Неподходящие синонимы|
|--------------------|------------|--------------|
|[Approve](/dotnet/api/System.Management.Automation.VerbsLifecycle.Approve) (ap)|Утверждает или одобряет состояние ресурса или процесса.||
|[Assert](/dotnet/api/System.Management.Automation.VerbsLifecycle.Assert) (as)|Подтверждает состояние ресурса.|Certify|
|[Build](/dotnet/api/System.Management.Automation.VerbsLifecycle.Build) (bd)|Создает артефакт (обычно двоичный код или документ) из набора входных файлов (обычно это исходный код или декларативные документы). Эта команда добавлена в PowerShell 6.||
|[Complete](/dotnet/api/system.management.automation.host.buffercelltype) (cp)|Завершает операцию.||
|[Confirm](/dotnet/api/System.Management.Automation.VerbsLifecycle.Confirm) (cn)|Подтверждает или проверяет состояние ресурса или процесса.|Acknowledge, Agree, Certify, Validate, Verify|
|[Deny](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deny) (dn)|Отклоняет объекты и блоки или препятствует состоянию ресурса или процесса.|Block, Object, Refuse, Reject|
|[Deploy](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deploy) (dp)|Отправляет приложение, веб-сайт или решение на удаленный целевой объект таким образом, чтобы потребитель этого решения мог получить к нему доступ после завершения развертывания. Эта команда добавлена в PowerShell 6.||
|[Disable](/dotnet/api/System.Management.Automation.VerbsLifecycle.Disable) (d)|Настраивает для ресурса недоступное или неактивное состояние. Например, командлет `Disable-PSBreakpoint` деактивирует точку останова. Эта команда образует пару с командой `Enable`.|Halt, Hide|
|[Enable](/dotnet/api/System.Management.Automation.VerbsLifecycle.Enable) (e)|Настраивает для ресурса доступное или активное состояние. Например, командлет `Enable-PSBreakpoint` активирует точку останова. Эта команда образует пару с командой `Disable`.|Start, Begin|
|[Install](/dotnet/api/System.Management.Automation.VerbsLifecycle.Install) (is)|Помещает ресурс в расположение и при необходимости инициализирует его. Эта команда образует пару с командой `Uninstall`.|Настройка|
|[Invoke](/dotnet/api/System.Management.Automation.VerbsLifecycle.Invoke) (i)|Выполняет действие, например запуск команды или метода.|Run, Start|
|[Register](/dotnet/api/System.Management.Automation.VerbsLifecycle.Register) (rg)|Создает запись для ресурса в репозитории, например в базе данных. Эта команда образует пару с командой `Unregister`.||
|[Request](/dotnet/api/System.Management.Automation.VerbsLifecycle.Request) (rq)|Запрашивает ресурс или разрешения.||
|[Restart](/dotnet/api/System.Management.Automation.VerbsLifecycle.Restart) (rt)|Останавливает операцию и запускает ее снова. Например, командлет `Restart-Service` останавливает, а затем запускает службу.|Перезапуск|
|[Resume](/dotnet/api/System.Management.Automation.VerbsLifecycle.Resume) (ru)|Запускает приостановленную операцию. Например, командлет `Resume-Service` запускает приостановленную службу. Эта команда образует пару с командой `Suspend`.||
|[Start](/dotnet/api/System.Management.Automation.VerbsLifecycle.Start) (sa)|Инициирует операцию. Например, командлет `Start-Service` запускает службу. Эта команда образует пару с командой `Stop`.|Launch, Initiate, Boot|
|[Stop](/dotnet/api/System.Management.Automation.VerbsLifecycle.Stop) (sp)|Прекращение действия. Эта команда образует пару с командой `Start`.|End, Kill, Terminate, Cancel|
|[Submit](/dotnet/api/System.Management.Automation.VerbsLifecycle.Submit) (sb)|Представляет ресурс для утверждения.|Опубликовать|
|[Suspend](/dotnet/api/System.Management.Automation.VerbsLifecycle.Suspend) (ss)|Приостанавливает действие. Например, командлет `Suspend-Service` приостанавливает службу. Эта команда образует пару с командой `Resume`.|Пауза|
|[Uninstall](/dotnet/api/System.Management.Automation.VerbsLifecycle.Uninstall) (us)|Удаляет ресурс из указанного расположения. Эта команда образует пару с командой `Install`.||
|[Unregister](/dotnet/api/System.Management.Automation.VerbsLifecycle.Unregister) (ur)|Удаляет запись для ресурса из репозитория. Эта команда образует пару с командой `Register`.|Удалить|
|[Wait](/dotnet/api/System.Management.Automation.VerbsLifecycle.Wait) (w)|Приостанавливает операцию, пока не произойдет указанное событие. Например, командлет `Wait-Job` приостанавливает операции до тех пор, пока не завершится выполнение одного или нескольких фоновых заданий.|Sleep, Pause|

## <a name="security-verbs"></a>Команды безопасности

PowerShell использует класс [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity) для определения действий, которые применяются к безопасности. В следующей таблице перечислено большинство определенных команд.

|Команда (псевдоним)|Действие|Неподходящие синонимы|
|--------------------|------------|--------------|
|[Block](/dotnet/api/System.Management.Automation.VerbsSecurity.Block) (bl)|Ограничивает доступ к ресурсу. Эта команда образует пару с командой `Unblock`.|Prevent, Limit, Deny|
|[Grant](/dotnet/api/System.Management.Automation.VerbsSecurity.Grant) (gr)|Разрешает доступ к ресурсу. Эта команда образует пару с командой `Revoke`.|Allow, Enable|
|[Protect](/dotnet/api/System.Management.Automation.VerbsSecurity.Protect) (pt)|Защищает ресурс от атак или потери. Эта команда образует пару с командой `Unprotect`.|Encrypt, Safeguard, Seal|
|[Revoke](/dotnet/api/System.Management.Automation.VerbsSecurity.Revoke) (rk)|Указывает действие, которое не разрешает доступ к ресурсу. Эта команда образует пару с командой `Grant`.|Remove, Disable|
|[Unblock](/dotnet/api/System.Management.Automation.VerbsSecurity.Unblock) (ul)|Удаляет ограничения для ресурса. Эта команда образует пару с командой `Block`.|Clear, Allow|
|[Unprotect](/dotnet/api/System.Management.Automation.VerbsSecurity.Unprotect) (up)|Удаляет меры защиты для ресурса, которые были добавлены, чтобы предотвратить атаку или потерю. Эта команда образует пару с командой `Protect`.|Decrypt, Unseal|

## <a name="other-verbs"></a>Другие команды

PowerShell использует класс [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther) для определения канонических имен команд, которые не входят в конкретную категорию, например общих команд, обмена данными, обработки данных, жизненного цикла или безопасности.

|Команда (псевдоним)|Действие|Неподходящие синонимы|
|--------------------|------------|--------------|
|[Use](/dotnet/api/System.Management.Automation.VerbsOther.Use) (u)|Использует или включает ресурс для чего-либо.||

## <a name="see-also"></a>См. также:

- [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)
- [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)
- [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)
- [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)
- [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)
- [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)
- [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)
- [Объявление командлета](./cmdlet-class-declaration.md)
- [Руководство программиста по Windows PowerShell](../prog-guide/windows-powershell-programmer-s-guide.md)
- [Пакет SDK Windows PowerShell](../windows-powershell-reference.md)
