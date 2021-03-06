---
description: Описание обновляемой справочной системы в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: e49881b9f051cc176cae72f43ac6c7040c03f0c8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231870"
---
# <a name="about-updatable-help"></a>Сведения об обновляемой справке

## <a name="short-description"></a>Краткое описание
Описание обновляемой справочной системы в PowerShell.

## <a name="long-description"></a>Подробное описание

PowerShell предоставляет несколько различных способов доступа к наиболее актуальным разделам справки по командлетам и концепциям PowerShell.

Обновляемая справочная система, представленная в PowerShell 3,0, предназначена для того, чтобы всегда иметь новейшие разделы справки на локальном компьютере, чтобы вы могли прочитать их в командной строке. Это позволяет легко загружать и устанавливать файлы справки, а также обновлять их каждый раз, когда становятся доступны новые файлы справки.

Чтобы обеспечить обновленную справку для нескольких компьютеров предприятия и компьютеров, которые не имеют доступа к Интернету, обновляемая Справка позволяет загружать файлы справки в каталог файловой системы или общую папку, а затем устанавливать файлы справки из общей папки.

В PowerShell 4,0 свойство **HelpInfoUri** сохраняется при удаленном взаимодействии Windows PowerShell, что позволяет `Save-Help` работать с модулями, которые установлены на удаленном компьютере, но не обязательно устанавливаются на локальном компьютере. Объект **PSModuleInfo** можно сохранить на диске или съемном носителе (например, на USB-накопителе), запустив `Export-Clixml` на компьютере без доступа к Интернету, импортировав объект **PSModuleInfo** на компьютере, который имеет доступ к Интернету, а затем запуская `Save-Help` объект **PSModuleInfo** . Сохраненную справку можно скопировать на удаленный, отключенный компьютер с помощью съемного носителя, а затем установить, запустив `Update-Help` . Эти улучшения `Save-Help` функциональности позволяют установить справку на компьютерах, которые не имеют какого либо сетевого доступа. Пример использования новых `Save-Help` функциональных возможностей см. в разделе [обновление справки из общей папки](#how-to-update-help-from-a-file-share) в этой статье.

Обновляемая Справка также поддерживает доступ в Интернет к новым темам справки и основную справку по командлетам, даже если на компьютере нет файлов справки.

PowerShell 3,0 не поставляется с файлами справки. Можно использовать функцию обновляемой справки для установки файлов справки для всех команд, включенных по умолчанию в PowerShell, и для всех модулей Windows.

## <a name="updatable-help-cmdlets"></a>Обновляемые командлеты справки

- `Update-Help`: Скачивает новейшие файлы справки из Интернета или общей папки и устанавливает их на локальный компьютер.

- `Save-Help`: Скачивает новейшие файлы справки из Интернета и сохраняет их в каталоге файловой системы или в общей папке. Чтобы установить файлы справки на компьютерах, используйте `Update-Help` .

- `Get-Help`: Отображает разделы справки в командной строке. Получение справки из файлов справки на компьютере. Отображает автоматически созданную справку для командлетов и функций, не имеющих файлов справки. Открывает разделы справки в Интернете по командлетам, функциям, сценариям и рабочим процессам в браузере по умолчанию.

## <a name="auto-generated-help-help-without-help-files"></a>Автоматически созданная Справка: Справка без файлов справки

Если у вас нет файла справки для командлета, функции или рабочего процесса на компьютере, `Get-Help` командлет отображает автоматически созданную справку и предлагает загрузить файлы справки или прочитать их в Интернете.

Автоматически созданная Справка содержит синтаксис и псевдонимы, а также комментарии, объясняющие, как использовать обновляемые командлеты справки и получать доступ к разделам справки в Интернете.

Например, следующая команда возвращает основную справку для `Get-Culture` командлета. В выходных данных отображается `Get-Help` Отображение, если на компьютере нет файлов справки.

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a>Файлы справки для модулей

Самая маленькая единица обновляемой справки — Справка по модулю. Справка по модулям включает в себя справку по всем командлетам, функциям, рабочим процессам, поставщикам, скриптам и концепциям в модуле. Можно обновить справку для всех модулей, установленных на компьютере, даже если они не импортированы в текущий сеанс.

Можно обновить справку для всего модуля, но нельзя обновить справку для отдельных командлетов.

Чтобы найти модуль, содержащий конкретный командлет, используйте следующий формат команды:

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

Например, чтобы найти модуль, содержащий `Set-ExecutionPolicy` командлет, введите:

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

Чтобы обновить справку для конкретного модуля, введите:

```powershell
Update-Help -Module <ModuleName>
```

Например, чтобы обновить справку для модуля, содержащего командлет Set-ExecutionPolicy, введите:

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a>Разрешения для обновляемой справки

Для обновления справки по модулям в каталоге `$pshome/Modules` необходимо быть членом группы администраторов на компьютере.

Если вы не являетесь членом группы "Администраторы", обновление справки для этих модулей невозможно; но если у вас есть доступ к Интернету, можно просмотреть справку в Интернете.

Для обновления справки по модулям в каталоге `$home/Documents/PowerShell/Modules` или модулях в других подкаталогах `$home` каталога не требуются специальные разрешения.

`Update-Help` `Save-Help` Командлеты и имеют параметр **уседефаулткредентиалс** , предоставляющий явные учетные данные текущего пользователя. Этот параметр предназначен для доступа к защищенным Интернет-расположениям.

`Update-Help` `Save-Help` Командлеты и также имеют параметр **Credential** , позволяющий выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере. Параметр **Credential** допустим только при использовании параметров SourcePath или **LiteralPath** `Update-Help` и параметров **DestinationPath** или **LiteralPath** параметра `Save-Help` .

## <a name="how-to-install-and-update-help-files"></a>Установка и обновление файлов справки

Чтобы загрузить и установить файлы справки в первый раз или обновить файлы справки на компьютере, используйте `Update-Help` командлет.

`Update-Help`Командлет выполняет всю твердую работу, включая следующие задачи.

- Определяет, какие модули поддерживают обновляемую справку.
- Находит расположение в Интернете, в котором каждый модуль хранит свои обновляемые файлы справки.
- Сравнение файлов справки для каждого модуля на компьютере с последними файлами справки, доступными для каждого модуля.
- Скачивает новые файлы из Интернета.
- Распаковывает пакет файла справки.
- Проверяет, являются ли файлы допустимыми файлами справки.
- Устанавливает файлы справки в подкаталоге, зависящем от языка, в каталоге Module.

Для доступа к новым разделам справки используйте `Get-Help` командлет. Перезапускать PowerShell не требуется.

Чтобы установить или обновить справку для всех модулей на компьютере, поддерживающем обновляемую справку, введите:

```powershell
Update-Help
```

Чтобы обновить справку для определенных модулей, добавьте параметр **module** в `Update-Help` . В имени модуля допускаются подстановочные знаки.

Например, чтобы обновить справку для модуля ServerManager, введите:

```powershell
Update-Help -Module ServerManager
```

Без параметров `Update-Help` обновления помогают для всех модулей в сеансе и для всех установленных модулей, поддерживающих обновляемую справку. Для включения необходимо установить модули в каталогах, указанных в значении переменной среды PSModulePath. Это также модули, возвращаемые командой "Get-Help-ListAvailable".

Если параметр **module** имеет значение `*` (ALL), то `Update-Help` пытается обновить справку для всех установленных модулей, включая модули, которые не поддерживают обновляемую справку. Эта команда обычно создает много ошибок, так как командлет встречает модули, которые не поддерживают обновляемую справку.

## <a name="how-to-update-help-from-a-file-share"></a>Обновление справки из общей папки

Для поддержки компьютеров, не подключенных к Интернету, а также для управления или оптимизации обновления справки на предприятии используйте `Save-Help` командлет. `Save-Help`Командлет загружает файлы справки из Интернета и сохраняет их в указанном каталоге файловой системы.

`Save-Help` Сравнивает файлы справки в указанном каталоге с последними файлами справки, доступными для каждого модуля. Если в каталоге нет файлов справки или более новых файлов справки для модуля, `Save-Help` командлет загружает новые файлы из Интернета. Однако он не распаковывает и не устанавливает файлы справки.

Чтобы установить или обновить файлы справки на компьютере из файлов справки, сохраненных в каталоге файловой системы, используйте параметр **SourcePath** `Update-Help` командлета. `Update-Help`Командлет определяет самые новые файлы справки, распаковывает их и проверяет, а также устанавливает их в подкаталоги, зависящие от языка, в каталогах модулей.

Например, чтобы сохранить справку для всех установленных модулей в `\\Server\Share` каталоге, введите:

```powershell
Save-Help -DestinationPath \\Server\Share
```

Затем, чтобы обновить справку из `\\Server\Share` каталога, введите:

```powershell
Update-Help -SourcePath \\Server\Share
```

В следующих примерах показано использование `Save-Help` для сохранения справки по модулям, которые не установлены на локальном компьютере. В этом примере администратор выполняет команду, `Save-Help` чтобы сохранить справку для модуля DhcpServer с клиентского компьютера, подключенного к Интернету, не устанавливая на локальном компьютере роль модуля DhcpServer или DHCP-сервера.

Вариант 1. выполните команду, `Invoke-Command` чтобы получить объект **PSModuleInfo** для удаленного модуля, сохраните его в переменной, `$m` а затем выполните `Save-Help` в объекте **PSModuleInfo** , указав переменную в `$m` качестве имени модуля.

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Вариант 2. Откройте сеанс PSSession, предназначенный для компьютера, на котором выполняется модуль DHCP-сервера, чтобы получить объект **PSModuleInfo** для модуля, сохраните его в переменной `$m` , а затем выполните `Save-Help` для объекта, сохраненного в `$m` переменной.

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Вариант 3. Откройте сеанс CIM, предназначенный для компьютера, на котором работает модуль DHCP-сервера, чтобы получить объект **PSModuleInfo** для модуля, сохраните его в переменной `$m` , а затем выполните `Save-Help` для объекта, сохраненного в `$m` переменной.

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

В следующем примере администратор устанавливает справку для модуля DHCP-сервера на компьютере, который не имеет доступа к сети.

Сначала выполните команду, `Export-Clixml` чтобы экспортировать объект **PSModuleInfo** в общую папку или на съемный носитель.

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

Затем необходимо передать съемный носитель на компьютер с доступом к Интернету, а затем импортировать объект **PSModuleInfo** с помощью `Import-Clixml` . Выполните команду `Save-Help` , чтобы сохранить справку для импортированного объекта **PSModuleInfo** модуля DhcpServer.

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

Наконец, выполните транспортный носитель обратно на компьютер без доступа к сети, а затем установите справку, выполнив команду `Update-Help` .

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

Без параметров `Save-Help` загружает справку по всем модулям в сеансе и ко всем установленным модулям, поддерживающим обновляемую справку. Для включения необходимо установить модули в каталогах, указанных в значении `$env:PSModulePath` переменной среды, на локальном компьютере или на удаленном компьютере, для которого требуется сохранить справку. Это также модули, возвращаемые при выполнении `Get-Help -ListAvailable` команды.

## <a name="how-to-update-help-files-in-different-languages"></a>Обновление файлов справки на разных языках

По умолчанию `Update-Help` `Save-Help` командлеты и загружают справку по языку и региональным параметрам пользовательского интерфейса, установленным для Windows на локальном компьютере. Если файлы справки для указанных модулей недоступны в локальном пользовательском интерфейсе, `Update-Help` и `Save-Help` для поиска лучшего поддерживаемого языка используются правила резервирования на языке Windows.

Однако можно использовать параметры **UICulture** `Update-Help` `Save-Help` командлетов и для загрузки и установки файлов справки в любых культурах пользовательского интерфейса, в которых они доступны.

Например, чтобы сохранить самые новые файлы справки для всех модулей в сеансе на японском языке (ja-JP) и французском (fr-FR), введите:

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

Если файлы справки для модулей недоступны на указанных языках, `Update-Help` `Save-Help` командлеты и возвращают сообщение об ошибке, в котором перечислены языки, на которых доступна справка для каждого модуля, чтобы можно было выбрать альтернативный вариант, который наилучшим образом соответствует вашим потребностям.

> [!NOTE]
> В настоящее время обновляемое содержимое справки публикуется только на английском языке (EN-US). В некоторых системах, отличных от Windows, для явного запроса содержимого необходимо использовать параметр **UICulture** `en-US` .

## <a name="how-to-use-online-help"></a>Использование справки в Интернете

Если вы не можете или не хотите обновлять файлы справки на локальном компьютере, вы по-прежнему можете получать самые новые файлы справки в Интернете.

Чтобы открыть раздел справки в Интернете для любого командлета или функции, используйте параметр **Online** `Get-Help` командлета.

Например, следующая команда открывает раздел справки в Интернете для `Get-Job` командлета в браузере по умолчанию:

```powershell
Get-Help Get-Job -Online
```

Чтобы получить справку в Интернете для скрипта, используйте параметр **Online** и полный путь к скрипту.

Параметр **Online** не работает с разделами About. Разделы о PowerShell, в том числе разделы справки по языку PowerShell, см. в статье [о темах в PowerShell](about.md).

## <a name="how-to-minimize-or-prevent-internet-downloads"></a>Как выполнить минимальную или невозможность загрузки из Интернета

Чтобы сократить загрузку из Интернета и предоставить обновляемую справку пользователям, которые не подключены к Интернету, используйте `Save-Help` командлет. Загрузите справку из Интернета и сохраните ее в сетевую папку. Затем создайте параметр групповая политика или запланированное задание, которое запускает `Update-Help` команду на всех компьютерах. Задайте в качестве значения параметра **SourcePath** `Update-Help` командлета сетевую папку.

Чтобы запретить пользователям, имеющим доступ к Интернету, загрузку обновляемой справки из Интернета, используйте параметр **задать путь к источнику по умолчанию для параметра обновить-Help** групповая политика.

Этот групповая политика неявно добавляет параметр **SourcePath** с указанной папкой FileSystem в каждую `Update-Help` команду на каждом затронутом компьютере. Пользователи могут явно использовать параметр **SourcePath** , чтобы указать другое расположение файловой системы, но не может исключить параметр **SourcePath** и загрузить справку из Интернета.

> [!NOTE]
> В разделе **Конфигурация компьютера** и **Конфигурация пользователя** появится параметр **задать исходный путь по умолчанию для групповой политики обновления-справки** . Однако действует только параметр политики в разделе **Конфигурация компьютера** . Параметр политики в разделе **Конфигурация пользователя** игнорируется.

Дополнительные сведения см. в статье [О параметрах групповой политики](about_Group_Policy_Settings.md).

## <a name="how-to-update-help-for-non-standard-modules"></a>Обновление справки по нестандартным модулям

Чтобы обновить или сохранить справку для модуля, который не возвращается параметром **ListAvailable** `Get-Module` командлета, импортируйте модуль в текущий сеанс перед выполнением `Update-Help` `Save-Help` команды или. На удаленном компьютере перед выполнением `Save-Help` команды Импортируйте модуль в текущий сеанс или `Invoke-Command` блок сценария, подключенный к удаленному компьютеру.

Если модуль находится в текущем сеансе, выполните `Update-Help` `Save-Help` командлеты или без параметров или используйте параметр **module** , чтобы указать имя модуля.

Параметры **модуля** `Update-Help` `Save-Help` командлетов и принимают только имя модуля. Они не принимают путь к файлу модуля.

Эта методика используется для обновления или сохранения справки для любого модуля, который не возвращается параметром **ListAvailable** `Get-Module` командлета, например модуля, установленного в расположении, отсутствующем в `$env:PSModulePath` переменной среды, или неверно сформированном модуле (каталог модуля не содержит по крайней мере одного файла, базовое имя которого совпадает с именем каталога).

## <a name="how-to-support-updatable-help"></a>Поддержка обновляемой справки

При создании модуля можно поддерживать интерактивную справку и обновляемую справку для модулей. Дополнительные сведения см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/help/supporting-updatable-help) и [поддержка справки в Интернете](/powershell/scripting/developer/module/supporting-online-help) в документация Майкрософт.

Обновляемая Справка недоступна для оснасток PowerShell или справки на основе комментариев.

## <a name="remarks"></a>Remarks

`Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).

## <a name="see-also"></a>См. также статью

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)
