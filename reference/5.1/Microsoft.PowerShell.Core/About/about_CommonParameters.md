---
description: Описывает параметры, которые можно использовать с любым командлетом.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 898f0897638523291751ce75db1c6a6b4628e778
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860699"
---
# <a name="about-commonparameters"></a>О Общиепараметры

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описывает параметры, которые можно использовать с любым командлетом.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Общие параметры — это набор параметров командлета, которые можно использовать с любым командлетом. Они реализуются с помощью PowerShell, а не разработчика командлетов и автоматически доступны любому командлету.

Общие параметры можно использовать с любыми командлетами, но они могут не влиять на все командлеты. Например, если командлет не создает подробные выходные данные, использование параметра **verbose** Common не оказывает никакого влияния.

Общие параметры также доступны для расширенных функций, использующих атрибут **CmdletBinding** или **Parameter** .

Несколько общих параметров переопределяют системные значения по умолчанию или настройки, заданные с помощью переменных предпочтений PowerShell. В отличие от привилегированных переменных, общие параметры влияют только на те команды, в которых они используются.

Дополнительные сведения см. в разделе [about_Preference_Variables](./about_Preference_Variables.md).

В следующем списке отображаются общие параметры. Их псевдонимы перечислены в скобках.

- **Debug** (db)
- **ErrorAction** (EA)
- **ErrorVariable** (EV)
- **InformationAction** (инфа)
- **InformationVariable** (IV)
- **Переменная** (OV)
- **Буфер** (OB)
- **PipelineVariable** (ПС)
- **Verbose** (VB)
- **WarningAction** (штат Вашингтон)
- **WarningVariable** (WV)

Параметры **действия** — это значения типа **действие** .
**Действие** — это перечисление со следующими значениями:

| name             | Значение |
|------------------|-------|
| Приостановить          | 5     |
| Игнорировать           | 4     |
| Inquire          | 3     |
| Продолжить         | 2     |
| Стоп             | 1     |
| SilentlyContinue | 0     |

Можно использовать имя или значение с параметром.

Помимо общих параметров, многие командлеты предлагают параметры устранения рисков. Командлеты, которые подразумевают риск для системы или для пользовательских данных, обычно предлагают эти параметры.

Параметры устранения рисков:

- **WhatIf** (Wi-in)
- **Подтверждение** (CF)

### <a name="common-parameter-descriptions"></a>ОБЩИЕ ОПИСАНИЯ ПАРАМЕТРОВ

#### <a name="debug"></a>Отладка

Отображает сведения на уровне программиста об операции, выполняемой командой. Этот параметр работает только в том случае, если команда создает сообщение отладки. Например, этот параметр работает, если команда содержит `Write-Debug` командлет.

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

По умолчанию сообщения отладки не отображаются, так как значение `$DebugPreference` переменной — **SilentlyContinue**.

В интерактивном режиме параметр **Debug** переопределяет значение `$DebugPreference` переменной для текущей команды, устанавливая для параметра значение "запрос" `$DebugPreference` . 

В неинтерактивном режиме параметр **Debug** переопределяет значение `$DebugPreference` переменной для текущей команды, устанавливая `$DebugPreference` для значение **Continue**.

`-Debug:$true` имеет тот же результат, что и `-Debug` . Используйте, `-Debug:$false` чтобы подавлять отображение отладочных сообщений `$DebugPreference` , если не **SilentlyContinue**, что является значением по умолчанию.

#### <a name="erroraction"></a>ErrorAction

Определяет реакцию командлета на неустранимую ошибку команды.
Этот параметр работает только в том случае, если команда создает неустранимую ошибку, например из `Write-Error` командлета.

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

Параметр **ErrorAction** переопределяет значение `$ErrorActionPreference` переменной для текущей команды. Так как значение переменной по умолчанию `$ErrorActionPreference` **продолжится**, отображаются сообщения об ошибках и выполнение продолжается, если не используется параметр **ErrorAction** .

Параметр **ErrorAction** не влияет на завершающие ошибки (такие как отсутствующие данные, недопустимые параметры или недостаточные разрешения), препятствующие успешному выполнению команды.

`-ErrorAction:Continue` Отобразите сообщение об ошибке и продолжит выполнение команды. Значение по умолчанию — `Continue`.

`-ErrorAction:Ignore` Подавляет сообщение об ошибке и возобновляет выполнение команды. В отличие от **SilentlyContinue**, **Ignore** не добавляет сообщение об ошибке в `$Error` автоматическую переменную. Значение **Ignore** введено в PowerShell 3,0.

`-ErrorAction:Inquire` Отображает сообщение об ошибке и запрашивает подтверждение перед продолжением выполнения. Это значение используется редко.

`-ErrorAction:SilentlyContinue` Подавляет сообщение об ошибке и возобновляет выполнение команды.

`-ErrorAction:Stop` Отображает сообщение об ошибке и останавливает выполнение команды.

`-ErrorAction:Suspend` доступно только для рабочих процессов, которые не поддерживаются в PowerShell 6 и более поздних версиях.

> [!NOTE]
> Параметр **ErrorAction** переопределяет, но не заменяет значение `$ErrorAction` привилегированной переменной, если параметр используется в команде для выполнения скрипта или функции.

#### <a name="errorvariable"></a>ErrorVariable

**ErrorVariable** хранит сообщения об ошибках команды в указанной переменной и в `$Error` автоматической переменной. Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md)

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

По умолчанию новые сообщения об ошибках переписывают сообщения об ошибках, которые уже хранятся в переменной. Чтобы добавить сообщение об ошибке в содержимое переменной, введите знак плюс ( `+` ) перед именем переменной.

Например, следующая команда создает `$a` переменную, а затем сохраняет в ней ошибки:

```powershell
Get-Process -Id 6 -ErrorVariable a
```

Следующая команда добавляет любые сообщения об ошибках в `$a` переменную:

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

Следующая команда отображает содержимое `$a` :

```powershell
$a
```

Этот параметр можно использовать для создания переменной, которая содержит только сообщения об ошибках из конкретных команд и не влияет на поведение `$Error` автоматической переменной. `$Error`Автоматическая переменная содержит сообщения об ошибках всех команд в сеансе. Можно использовать нотацию массива, например `$a[0]` или, `$error[1,2]` для обращения к конкретным ошибкам, хранящимся в переменных.

> [!NOTE]
> Пользовательская переменная ошибки содержит все ошибки, сформированные командой, включая ошибки вызовов вложенных функций или скриптов.

#### <a name="informationaction"></a>InformationAction

Представлено в PowerShell 5,0. В команде или сценарии, в которой они используются, общий параметр **InformationAction** переопределяет значение `$InformationPreference` привилегированной переменной, которая по умолчанию имеет значение **SilentlyContinue**. При использовании `Write-Information` в скрипте с **InformationAction** `Write-Information` значения отображаются в зависимости от значения параметра **InformationAction** . Дополнительные сведения о `$InformationPreference` см. в разделе [about_Preference_Variables](./about_Preference_Variables.md).

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

`-InformationAction:Stop` Останавливает команду или скрипт при возникновении `Write-Information` команды.

`-InformationAction:Ignore` подавляет информационное сообщение и возобновляет выполнение команды. В отличие от **SilentlyContinue**, **Ignore** полностью забыл информационное сообщение. оно не добавляет информационное сообщение в информационный поток.

`-InformationAction:Inquire` отображает информационное сообщение, указанное в `Write-Information` команде, а затем спрашивает, нужно ли продолжить.

`-InformationAction:Continue` отображает информационное сообщение и продолжит выполнение.

`-InformationAction:Suspend` не поддерживается в PowerShell Core, так как он доступен только для рабочих процессов.

`-InformationAction:SilentlyContinue` не действует, так как информационное сообщение не отображается (по умолчанию), и сценарий продолжается без прерывания.

> [!NOTE]
> Параметр **InformationAction** переопределяет, но не заменяет значение `$InformationAction` привилегированной переменной, если параметр используется в команде для выполнения скрипта или функции.

#### <a name="informationvariable"></a>InformationVariable

Представлено в PowerShell 5,0. В команде или сценарии, в которой они используются, общий параметр **InformationVariable** сохраняет в переменной строку, указанную путем добавления `Write-Information` команды. `Write-Information` значения отображаются в зависимости от значения общего параметра **InformationAction** . Если не добавить общий параметр **InformationAction** , `Write-Information` строки будут показаны в зависимости от значения `$InformationPreference` привилегированной переменной. Дополнительные сведения о `$InformationPreference` см. в разделе [about_Preference_Variables](./about_Preference_Variables.md).

> [!NOTE]
> Информационная переменная содержит все информационные сообщения, созданные командой, включая информационные сообщения от вызовов вложенных функций или скриптов.

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a>OutBuffer

Определяет количество объектов, которые должны накапливаться в буфере перед отправкой объектов через конвейер. Если опустить этот параметр, то объекты будут отправляться по мере их создания.

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Этот параметр управления ресурсами предназначен для опытных пользователей. При использовании этого параметра PowerShell отправляет данные в следующий командлет в пакетах `OutBuffer + 1` .

В следующем примере в качестве альтернативы отображаются `ForEach-Object` блоки Process, использующие `Write-Host` командлет. Отображаемые варианты в пакетах — 2 или `OutBuffer + 1` .

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a>OutVariable

Сохраняет выходные объекты из команды в указанной переменной в дополнение к отправке выходных данных в конвейере.

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Чтобы добавить выходные данные в переменную, вместо того, чтобы заменять выходные данные, которые могут быть уже сохранены, введите знак плюса ( `+` ) перед именем переменной.

Например, следующая команда создает `$out` переменную и сохраняет в ней объект Process:

```powershell
Get-Process PowerShell -OutVariable out
```

Следующая команда добавляет объект Process в `$out` переменную:

```powershell
Get-Process iexplore -OutVariable +out
```

Следующая команда отображает содержимое `$out` переменной:

```powershell
$out
```

> [!NOTE]
> Переменная, созданная параметром **переменной** , имеет значение `[System.Collections.ArrayList]` .

#### <a name="pipelinevariable"></a>PipelineVariable

**PipelineVariable** сохраняет значение текущего конвейера как переменную для любой именованной команды в том виде, в каком она проходит через конвейер.

>[!NOTE]
> Расширенные функции могут иметь до трех блоков Script: `begin` , `process` и `end` . При использовании параметра **PipelineVariable** с расширенными функциями только значения из первого определенного блока скрипта присваиваются переменной при выполнении функции. Дополнительные сведения см. в разделе [Расширенные функции](./about_functions_advanced.md).
> PowerShell 7,2 исправляет это поведение.

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Допустимые значения — строки, такие же, как и для имен переменных.

Ниже приведен пример того, как работает **PipelineVariable** . В этом примере параметр **PipelineVariable** добавляется в `Foreach-Object` команду для сохранения результатов выполнения команды в переменных. Диапазон чисел от 1 до 10 передается в первую `Foreach-Object` команду, результаты которых хранятся в переменной с именем **Left**.

Результаты первой `Foreach-Object` команды передаются во вторую `Foreach-Object` команду, которая фильтрует объекты, возвращаемые первой `Foreach-Object` командой. Результаты второй команды хранятся в переменной с именем **right**.

В третьей `Foreach-Object` команде результаты первых двух `Foreach-Object` команд, представленных переменными **слева** и **справа**, обрабатываются с помощью оператора умножения. Команда указывает, что необходимо умножить объекты, хранящиеся в **левой** и **правой** переменных, и указать, что результаты должны отображаться как «левый диапазон член * правый диапазон Member = продукт».

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a>Подробный

Отображает подробные сведения об операции, выполненной командой. Эти сведения похожи на сведения в трассировке или в журнале транзакций. Этот параметр работает, только если команда создает подробное сообщение. Например, этот параметр работает, если команда содержит `Write-Verbose` командлет.

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

Параметр **verbose** переопределяет значение `$VerbosePreference` переменной для текущей команды. Так как значение переменной по умолчанию `$VerbosePreference` — **SilentlyContinue**, подробные сообщения не отображаются по умолчанию.

`-Verbose:$true` имеет тот же результат, что и `-Verbose`

`-Verbose:$false` подавляет отображение подробных сообщений. Используйте этот параметр, если значение `$VerbosePreference` не **SilentlyContinue** (по умолчанию).

#### <a name="warningaction"></a>WarningAction

Определяет реакцию командлета на предупреждение от команды. Значение **Continue** является значением по умолчанию. Этот параметр работает, только если команда создает предупреждающее сообщение. Например, этот параметр работает, если команда содержит `Write-Warning` командлет.

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

Параметр **WarningAction** переопределяет значение `$WarningPreference` переменной для текущей команды. Так как значение переменной по умолчанию `$WarningPreference` — **Continue**, отображаются предупреждения и выполнение продолжается, если не используется параметр **WarningAction** .

`-WarningAction:Continue` Отображает предупреждающие сообщения и возобновляет выполнение команды. Значение по умолчанию — `Continue`.

`-WarningAction:Inquire` отображает предупреждающее сообщение и запрашивает подтверждение перед продолжением выполнения. Это значение используется редко.

`-WarningAction:SilentlyContinue` подавляет предупреждающее сообщение и возобновляет выполнение команды.

`-WarningAction:Stop` отображает предупреждающее сообщение и прекращает выполнение команды.

> [!NOTE]
> Параметр **WarningAction** переопределяет, но не заменяет значение `$WarningAction` привилегированной переменной, если параметр используется в команде для выполнения скрипта или функции.

#### <a name="warningvariable"></a>WarningVariable

Хранит предупреждения о команде в указанной переменной.

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Все созданные предупреждения сохраняются в переменной, даже если они не отображаются для пользователя.

Чтобы добавить предупреждения в содержимое переменной, вместо того, чтобы заменять все предупреждения, которые могут быть уже сохранены, введите знак плюс ( `+` ) перед именем переменной.

Например, следующая команда создает `$a` переменную, а затем сохраняет в ней все предупреждения:

```powershell
Get-Process -Id 6 -WarningVariable a
```

Следующая команда добавляет все предупреждения в `$a` переменную:

```powershell
Get-Process -Id 2 -WarningVariable +a
```

Следующая команда отображает содержимое `$a` :

```powershell
$a
```

Этот параметр можно использовать для создания переменной, содержащей только предупреждения из конкретных команд. Можно использовать нотацию массива, например `$a[0]` или, `$warning[1,2]` для ссылки на конкретные предупреждения, хранящиеся в переменной.

> [!NOTE]
> Переменная предупреждения содержит все предупреждения, созданные командой, включая предупреждения о вызовах вложенных функций или скриптов.
### <a name="risk-management-parameter-descriptions"></a>Описания параметров управления рисками

#### <a name="whatif"></a>WhatIf

Отображает сообщение, описывающее результат выполнения команды, а не выполнение команды.

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

Параметр **WhatIf** переопределяет значение `$WhatIfPreference` переменной для текущей команды. Так как значение переменной по умолчанию `$WhatIfPreference` равно 0 (отключено), поведение **WhatIf** не выполняется без параметра **WhatIf** . Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md)

`-WhatIf:$true` имеет тот же результат, что и `-WhatIf` .

`-WhatIf:$false` подавляет автоматическое поведение WhatIf, которое возникает, когда значение `$WhatIfPreference` переменной равно 1.

Например, следующая команда использует `-WhatIf` параметр в `Remove-Item` команде:

```powershell
Remove-Item Date.csv -WhatIf
```

Вместо удаления элемента в PowerShell перечислены выполняемые операции и элементы, которые были бы затронуты. Эта команда создает следующие выходные данные:

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a>Подтвердить

Выводит приглашение для подтверждения перед выполнением команды.

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

Параметр **Confirm** переопределяет значение `$ConfirmPreference` переменной для текущей команды. Значение по умолчанию — true. Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md)

`-Confirm:$true` имеет тот же результат, что и `-Confirm` .

`-Confirm:$false` подавляет автоматическое подтверждение, которое происходит, если значение `$ConfirmPreference` меньше или равно предполагаемому риску командлета.

Например, следующая команда использует параметр **Confirm** с `Remove-Item` командой. Перед удалением элемента в PowerShell будут перечислены выполняемые операции и элементы, которые будут затронуты, и запрашивается утверждение.

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

Ниже приведены параметры подтверждения ответа.

|Ответ       |Результат                                                     |
|---------------|-----------------------------------------------------------|
|Да (Y)        |Выполните действие.                                        |
|Да для всех (A) |Выполнение всех действий и подавление последующих запросов на подтверждение|
|               |для этой команды.                                          |
|Нет (N):        |Не выполняйте действие.                                 |
|Нет для всех (L): |Не выполнять никаких действий и подавлять последующие подтверждения |
|               |запросы для этой команды.                                  |
|Приостановка:   |Приостановите команду и создайте временный сеанс.          |
|Справка (?)       |Отображает справку по этим параметрам.                            |

Параметр **Suspend** помещает команду в удержание и создает временный вложенный сеанс, в котором можно работать, пока вы не будете готовы выбрать параметр **подтверждения** . Командная строка для вложенного сеанса имеет две дополнительные символы (>>), указывающие, что это дочерняя операция исходной родительской команды. Во вложенном сеансе можно выполнять команды и скрипты. Чтобы завершить вложенный сеанс и вернуться к параметрам подтверждения исходной команды, введите "Exit".

В следующем примере параметры **приостановки** используются для временной остановки команды, в то время как пользователь проверяет справку для параметра команды. После получения необходимой информации пользователь вводит "Exit" для завершения вложенного запроса, а затем выбирает ответ "Да" (y) для подтверждения запроса.

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a>СЛОВАМИ

about_Common_Parameters

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Preference_Variables](about_Preference_Variables.md)

[Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)

[Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)

[Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error)

[Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
