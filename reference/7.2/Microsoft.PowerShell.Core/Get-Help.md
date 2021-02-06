---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 82721b3d079c795e0ce6fcae1fba0eab93344b52
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605530"
---
# Get-Help

## Краткий обзор
Отображает сведения о командах и концепциях PowerShell.

## SYNTAX

### AllUsersView (по умолчанию)

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### DetailedView

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Detailed
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Примеры

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Examples
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Параметры

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Parameter <String[]>
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Миграция по сети

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Online [<CommonParameters>]
```

### ShowWindow

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -ShowWindow [<CommonParameters>]
```

## DESCRIPTION

`Get-Help`Командлет отображает сведения об основных понятиях и командах PowerShell, включая командлеты, функции, команды модель CIM (CIM), рабочие процессы, поставщики, псевдонимы и скрипты.

Чтобы получить справку по командлету PowerShell, введите, `Get-Help` за которым следует имя командлета, например: `Get-Help Get-Process` .

Основные статьи справки в PowerShell начинаются с **about_**, например **about_Comparison_Operators**. Чтобы просмотреть все **about_** статьи, введите `Get-Help about_*` . Чтобы просмотреть определенную статью, введите `Get-Help about_<article-name>` , например `Get-Help about_Comparison_Operators` .

Чтобы получить справку для поставщика PowerShell, введите, `Get-Help` за которым следует имя поставщика. Например, чтобы получить справку для поставщика сертификатов, введите `Get-Help Certificate` .

Можно также ввести `help` или `man` , который отображает один экран текста за раз. Или, `<cmdlet-name> -?` , то же, что и `Get-Help` , но работает только для командлетов.

`Get-Help` Возвращает содержимое справки, которое отображается в файлах справки на компьютере. Без файлов справки `Get-Help` отображает только основные сведения о командлетах. К некоторым модулям PowerShell относятся файлы справки. Начиная с версии PowerShell 3,0 модули, которые входят в состав операционной системы Windows, не включают файлы справки. Чтобы скачать или обновить файлы справки для модуля в PowerShell 3,0, используйте `Update-Help` командлет.

Можно также просмотреть справочные документы по PowerShell в Интернете в Документация Майкрософт. Чтобы получить оперативную версию файла справки, используйте параметр **Online** , например: `Get-Help Get-Process -Online` . Сведения о том, как прочитать всю документацию по PowerShell, см. в документации по Документация Майкрософт [PowerShell](/powershell).

Если ввести `Get-Help` , за которым следует точное имя статьи справки, или слово, уникальное для статьи справки, `Get-Help` отображает содержимое статьи. Если указать точное имя псевдонима команды, `Get-Help` выводит справку по исходной команде. Если ввести слово или слово, которое отображается в нескольких заголовках справочной статьи, `Get-Help` отображается список соответствующих заголовков. При вводе любого текста, который не отображается в заголовках статей справки, `Get-Help` отображается список статей, содержащих этот текст в их содержимом.

`Get-Help` может получить статьи справки для всех поддерживаемых языков и языковых стандартов. `Get-Help` сначала ищет файлы справки в наборе языкового стандарта для Windows, затем в родительском языковом стандарте, например в **PT** для **pt-br**, а затем в резервном языковом стандарте. Начиная с версии PowerShell 3,0, если `Get-Help` не удается найти справку по резервному языку, он ищет статьи справки на английском языке, **en-US**, прежде чем возвращает сообщение об ошибке или отображает автоматически созданную справку.

Сведения о символах, `Get-Help` отображаемых на схеме синтаксиса команды, см. в разделе [about_Command_Syntax](./About/about_Command_Syntax.md).
Дополнительные сведения об атрибутах параметров, таких как **Required** и **Disposition**, см. в разделе [about_Parameters](./About/about_Parameters.md).

>[!NOTE]
> В PowerShell 3,0 и PowerShell 4,0 `Get-Help` не удается найти **сведения о** статьях в модулях, если модуль не импортирован в текущий сеанс. Это известная проблема. Чтобы получить **сведения о** статьях в модуле, импортируйте модуль либо с помощью `Import-Module` командлета, либо путем запуска командлета, который включается в модуль.

## Примеры

### Пример 1. Отображение основных справочных сведений о командлете

В этих примерах отображаются основные справочные сведения о `Format-Table` командлете.

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

`Get-Help <cmdlet-name>` — Это простейший синтаксис командлета по умолчанию `Get-Help` . Параметр **Name** можно опустить.

Синтаксис `<cmdlet-name> -?` работает только для командлетов.

### Пример 2. Отображение основных сведений по одной странице за раз

В этих примерах отображаются основные справочные сведения о `Format-Table` командлете по одной странице за раз.

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

`help` — Это функция, которая выполняет `Get-Help` командлет внутренне и отображает результат по одной странице за раз.

`man` псевдоним для `help` функции.

`Get-Help Format-Table` отправляет объект вниз по конвейеру. `Out-Host -Paging` Получает выходные данные из конвейера и отображает их по одной странице за раз. Дополнительные сведения см. в разделе [Out-Host](Out-Host.md).

### Пример 3. Отображение дополнительных сведений для командлета

В этих примерах отображаются более подробные справочные сведения о `Format-Table` командлете.

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

**Подробный** параметр отображает подробное представление статьи справки, включающее описание параметров и примеры.

Параметр **Full** отображает полное представление статьи справки, включающее описания параметров, примеры, типы входных и выходных объектов, а также дополнительные примечания.

Параметры **Detailed** и **Full** действуют только для команд, в которых есть файлы справки, установленные на компьютере. Параметры не вступают в силу для концептуальных (**about_**) справочных статей.

### Пример 4. Отображение выбранных частей командлета с помощью параметров

В этих примерах отображаются выбранные части `Format-Table` справки по командлетам.

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

Параметр " **примеры** " отображает разделы **имени** файла справки и **кратких** сведений, а также все примеры. Нельзя указать пример числа, так как параметр **examples** является параметром Switch.

Параметр **Parameter** отображает только описания указанных параметров. Если указать только `*` подстановочный знак звездочки (), будут выведены описания всех параметров.
Если **параметр** указывает имя параметра, например **GroupBy**, отображается информация об этом параметре.

Эти параметры не действуют для концептуальных (**about_**) статей справки.

### Пример 5. отображение интерактивной версии справки

В этом примере отображается интерактивная версия статьи справки для `Format-Table` командлета в веб-браузере по умолчанию.

```powershell
Get-Help Format-Table -Online
```

### Пример 6. Отображение справки по справочной системе

`Get-Help`Командлет без параметров отображает сведения о справочной системе PowerShell.

```powershell
Get-Help
```

### Пример 7. Отображение доступных справочных статей

В этом примере отображается список всех справочных статей, доступных на компьютере.

```powershell
Get-Help *
```

### Пример 8. Отображение списка концептуальных статей

В этом примере отображается список концептуальных статей, входящих в состав справки по PowerShell. Все эти статьи начинаются с символов **about_**. Чтобы отобразить определенный файл справки, введите `Get-Help \<about_article-name\>` , например, `Get-Help about_Signing` .

Отображаются только основные статьи с файлами справки, установленными на компьютере. Сведения о загрузке и установке файлов справки в PowerShell 3,0 см. в разделе [Update-Help](Update-Help.md).

```powershell
Get-Help about_*
```

### Пример 9. Поиск слова в справке по командлету

В этом примере показано, как выполнить поиск слова в статье справки по командлетам.

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

`Get-Help` использует параметр **Full** для получения справочных сведений для `Add-Member` . Объект **MamlCommandHelpInfo** отправляется по конвейеру. `Out-String` использует параметр **Stream** для преобразования объекта в строку. `Select-String` использует параметр **pattern** для поиска **Clixml** в строке.

### Пример 10. Отображение списка статей, содержащих слово

В этом примере отображается список статей, включающих **удаленное взаимодействие** по словам.

При вводе слова, которое не отображается в заголовке статьи, `Get-Help` отображается список статей, содержащих это слово.

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### Пример 11. Отображение справки, относящейся к поставщику

В этом примере показаны два способа получения справки, относящейся к поставщику `Get-Item` . Эти команды позволяют получить справку, в которой объясняется, как использовать `Get-Item` командлет в узле **коллекции** данных поставщика SQL Server PowerShell.

В первом примере используется параметр `Get-Help` **path** для указания пути поставщика SQL Server.
Так как путь поставщика указан, можно выполнить команду из любого расположения пути.

Во втором примере используется `Set-Location` для перехода к пути поставщика SQL Server. В этом расположении параметр **path** не требуется для `Get-Help` получения справки, относящейся к поставщику.

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### Пример 12. Отображение справки для сценария

В этом примере возвращается Справка для `MyScript.ps1 script` . Сведения о том, как написать справку по функциям и сценариям, см. в разделе [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## PARAMETERS

### -Category

Выводит справку только для элементов, относящихся к указанной категории, и их псевдонимы. Концептуальные статьи находятся в категории **HelpFile** .

Для этого параметра допустимы следующие значения:

- Псевдоним
- Командлет
- Поставщик
- Общие сведения
- ВОПРОСЫ И ОТВЕТЫ
- Глоссарий
- HelpFile
- ScriptCommand
- Компонент
- Фильтр
- екстерналскрипт
- Все
- дефаулселп
- Рабочий процесс
- DscResource
- Class
- Конфигурация

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Component

Отображает команды с указанным значением компонента, например **Exchange**. Введите название компонента.
Можно использовать подстановочные знаки. Этот параметр не влияет на отображение концептуальной справки (**about_**).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Detailed

Добавляет описания параметров и и примеры к основным справочным сведениям. Этот параметр эффективен, только если файлы справки установлены на компьютере. Он не влияет на отображение концептуальной справки (**about_**).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Examples

Выводит только имя, краткий обзор и параметры. Чтобы отобразить только примеры, введите `(Get-Help \<cmdlet-name\>).Examples` .

Этот параметр эффективен, только если файлы справки установлены на компьютере. Он не влияет на отображение концептуальной справки (**about_**).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full

Отображает всю статью справки для командлета. **Полная** включает описания параметров и атрибуты, примеры, типы входных и выходных объектов, а также дополнительные примечания.

Этот параметр эффективен, только если файлы справки установлены на компьютере. Он не влияет на отображение концептуальной справки (**about_**).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Functionality

Выводит справку по элементам с указанными функциями. Введите функцию. Можно использовать подстановочные знаки. Этот параметр не влияет на отображение концептуальной справки (**about_**).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Возвращает справку по указанной команде или понятию. Введите имя командлета, функции, поставщика, скрипта или рабочего процесса, например `Get-Member` , имя концептуальной статьи, например `about_Objects` , или псевдоним, например `ls` . Подстановочные знаки допускаются в именах командлетов и поставщиков, но нельзя использовать подстановочные знаки для поиска имен справочных статей по функциям и сценариев.

Чтобы получить справку для скрипта, который не находится по пути, указанному в `$env:Path` переменной среды, введите путь и имя файла скрипта.

Если ввести точное имя статьи справки, `Get-Help` отобразится ее содержимое.

Если ввести слово или слово, которое отображается в нескольких заголовках справочной статьи, `Get-Help` отображается список соответствующих заголовков.

При вводе любого текста, который не соответствует заголовкам статей справки, `Get-Help` отображается список статей, содержащих этот текст в их содержимом.

Названия концептуальных статей, например `about_Objects` , должны быть указаны на английском языке даже в версиях PowerShell, отличных от английского.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Online

Отображает интерактивную версию статьи справки в браузере по умолчанию. Этот параметр допустим только для статей справки по командлетам, функциям, рабочим процессам и сценариям.  `Get-Help` В удаленном сеансе нельзя использовать параметр Online.

Сведения о поддержке этой функции в справочных статьях, которые вы пишете, см. в разделах [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), [поддержка справки в Интернете](/powershell/scripting/developer/module/supporting-online-help)и [написание справки по командлетам PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter

Выводит только подробное описание указанных параметров. Разрешено использовать подстановочные знаки. Этот параметр не влияет на отображение концептуальной справки (**about_**).

```yaml
Type: System.String[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Возвращает справку с описанием того, как командлет работает по указанному пути к поставщику. Введите путь к поставщику PowerShell.

Этот параметр возвращает настраиваемую версию статьи справки по командлету, в которой объясняется, как работает командлет в указанном пути поставщика PowerShell. Этот параметр действует только для справки о командлете поставщика и только в том случае, если поставщик содержит пользовательскую версию статьи справки командлета поставщика в файле справки. Для использования этого параметра установите файл справки для модуля, включающего поставщик.

Чтобы просмотреть справку по пользовательскому командлету для пути к поставщику, перейдите по пути поставщика и введите `Get-Help` команду или в любом расположении пути, чтобы указать путь к поставщику, с помощью параметра **path** в `Get-Help` . Можно также найти справку по настраиваемому командлету в Интернете в разделе справки по поставщику статьи справки.

Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](./About/about_Providers.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Role

Выводит справку, настроенную для указанной роли пользователя. Введите роль. Можно использовать подстановочные знаки.

Введите роль, которую пользователь имеет в организации. Для некоторых командлетов в файлах справки содержится разный текст в зависимости от значения этого параметра. Этот параметр не влияет на справку по основным командлетам.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowWindow

Выводит раздел справки в окне для более удобного чтения. Окно содержит **функцию поиска и** окно **параметров** , которые позволяют задать параметры для экрана, включая параметры для вывода только выбранных разделов раздела справки.

Параметр **ShowWindow** поддерживает разделы справки для команд (командлеты, функции, команды CIM, скрипты) и концептуальные **сведения о** статьях. Он не поддерживает справку по поставщикам.

Этот параметр был повторно введен в PowerShell 7,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShowWindow
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

Вы не можете отправить объекты по конвейеру в `Get-Help` .

## Выходные данные

### ExtendedCmdletHelpInfo

При выполнении `Get-Help` команды, не имеющей файла справки, `Get-Help` возвращается объект **екстендедкмдлеселпинфо** , представляющий автоматически созданную справку.

### System.String

Если вы получаете общую справочную статью, `Get-Help` возвращает ее в виде строки.

### MamlCommandHelpInfo

При получении команды, имеющей файл справки, `Get-Help` возвращает объект **MamlCommandHelpInfo** .

## ПРИМЕЧАНИЯ

PowerShell 3,0 не включает файлы справки. Чтобы скачать и установить файлы справки, которые `Get-Help` выполняют чтение, используйте `Update-Help` командлет. С помощью `Update-Help` командлета можно скачать и установить файлы справки для основных команд, которые входят в состав PowerShell, а также для всех устанавливаемых модулей. С его помощью можно также обновлять файлы справки на компьютере, чтобы они всегда были актуальны.

Кроме того, вы можете ознакомиться с справочными статьями, посвященными командам PowerShell Online, начиная с [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

`Get-Help` Отображает справку в наборе языкового стандарта для операционной системы Windows или на резервном языке для этого языкового стандарта. Если у вас нет файлов справки для основного или резервного языкового стандарта, `Get-Help` ведет себя так, как если бы на компьютере не было файлов справки. Чтобы получить справку для другого языкового стандарта, измените параметры с помощью **области** и **языка** на панели управления. В Windows 10 **Параметры**, **время & язык**.

Полный обзор справки включает таблицу сведений о параметрах. В таблице содержатся указанные ниже поля.

- **Обязательно**. Показывает, является ли параметр необходимым (true) или необязательным (false).

- **Расположение**. Указывает, является ли параметр именованным или позиционированным (числовым). Позиционные параметры должны появляться в указанном месте команды.

- **С именем** указывает, что имя параметра является обязательным, но параметр может находиться в любом месте команды.

- **Numeric** указывает, что имя параметра является необязательным, но если имя не указано, параметр должен находиться в месте, указанном в номере. Например, `2` указывает, что если имя параметра не указано, параметр должен быть вторым или единственным безымянным параметром в команде. Если используется имя параметра, параметр может располагаться в любом месте команды.

- **Значение по умолчанию**. Значение параметра или поведение по умолчанию, используемое PowerShell, если параметр не включен в команду.

- Принимает входные данные конвейера. Указывает, можно ли (true) или нет (false) отправку объектов в параметр через конвейер. **По имени свойства** означает, что конвейерный объект должен иметь свойство, имя которого совпадает с именем параметра.

- **Принимает подстановочные знаки**. Указывает, может ли значение параметра содержать подстановочные знаки, например звездочку ( `*` ) или вопросительный знак ( `?` ).

## Связанные ссылки

[about_Command_Syntax](About/about_Command_Syntax.md)

[about_Comment_Based_Help](./About/about_Comment_Based_Help.md)

[Get-Command](Get-Command.md)

[Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help)

[Update-Help](Update-Help.md)

[Написание разделов справки на основе комментариев](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[Написание справки для командлетов PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)

