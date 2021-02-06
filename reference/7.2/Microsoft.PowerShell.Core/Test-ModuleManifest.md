---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: c86a7253335b91011d2eb225bc53d1c5cc671aff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601089"
---
# Test-ModuleManifest

## Краткий обзор
Проверяет, точно ли описывает файл манифеста модуля его содержимое.

## SYNTAX

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Test-ModuleManifest** проверяет, находятся ли файлы, перечисленные в файле манифеста модуля (. PSD1), в указанных путях.

Этот командлет помогает разработчикам модулей тестировать файлы манифестов.
Пользователи модулей также могут использовать этот командлет в сценариях и командах для обнаружения ошибок перед выполнением скриптов, зависящих от модуля.

Командлет **Test-ModuleManifest** возвращает объект, представляющий модуль.
Это тот же тип объекта, который Get-Module возвращает.
Если какой-либо файл отсутствует в местоположении, указанном в манифесте, выдается ошибка для каждого отсутствующего файла.

## Примеры

### Пример 1. Тестирование манифеста

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

Эта команда проверяет манифест модуля TestModule.psd1.

### Пример 2. Тестирование манифеста с помощью конвейера

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

Эта команда использует конвейерный оператор (|) для отправки строки пути в **Test-ModuleManifest**.

В выходных данных команды видно, что тест закончился ошибкой, так как не найден файл TestTypes.ps1xml, указанный в манифесте.

### Пример 3. Написание функции для тестирования манифеста модуля

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

Эта функция похожа на **Test-ModuleManifest**, но возвращает логическое значение.
Функция возвращает $True, если манифест прошел проверку и $False иным образом.

Функция использует командлет Get-ChildItem Alias = dir для получения манифеста модуля, указанного $path переменной.
Команда использует конвейерный оператор (|) для передачи объекта File в **Test-ModuleManifest**.

Командлет **Test-ModuleManifest** использует общий параметр *ErrorAction* со значением SilentlyContinue, чтобы подавить отображение ошибок, формируемых командой.
Он также сохраняет объект **PSModuleInfo** , возвращаемый командлетом **Test-ModuleManifest** , в переменную $a.
Поэтому объект не отображается.

Затем в отдельной команде функция отображает значение $?
Автоматическая переменная.
Если предыдущая команда не создает ошибку, команда отображает $True и $False в противном случае.

Эту функцию можно использовать в условных инструкциях, например тех, которые могут предшествовать команде **Import-Module** , или команде, которая использует этот модуль.

## PARAMETERS

### -Path

Указывает путь и имя файла манифеста.
Введите необязательный путь и имя файла манифеста модуля с расширением имени файла PSD1.
Местоположением по умолчанию является текущий каталог.
Подстановочные знаки поддерживаются, но должны разрешаться в один файл манифеста модуля.
Это обязательный параметр.
Можно также передать путь в командлет **Test-ModuleManifest** по конвейеру.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Путь к манифесту модуля можно передать в этот командлет по конвейеру.

## Выходные данные

### System.Management.Automation.PSModuleInfo

Этот командлет возвращает объект **PSModuleInfo** , представляющий модуль.
Объект возвращается даже при наличии ошибок в манифесте.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[New-Module](New-Module.md)

[New-ModuleManifest](New-ModuleManifest.md)

[Remove-Module](Remove-Module.md)

[about_Modules](About/about_Modules.md)

