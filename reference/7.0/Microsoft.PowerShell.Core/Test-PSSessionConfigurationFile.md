---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: e64565cbc567ca42b190e143e065f9eddba2f311
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225574"
---
# Test-PSSessionConfigurationFile

## Краткий обзор
Проверяет ключи и значения в файле конфигурации сеанса.

## SYNTAX

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Этот командлет проверяет, что файл конфигурации сеанса содержит допустимые ключи, а значения имеют правильный тип. Для перечисляемых значений командлет проверяет правильность указанных значений.

Командлет возвращает значение, `$True` Если файл проходит все тесты, а `$False` Если нет. Чтобы найти ошибки, используйте параметр **verbose** .

`Test-PSSessionConfigurationFile` проверяет файлы конфигурации сеанса, например созданные `New-PSSessionConfigurationFile` командлетом. Сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md). Дополнительные сведения о файлах конфигурации сеансов см. в разделе [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Этот командлет появился в PowerShell 3,0.

## Примеры

### Пример 1. Тестирование файла конфигурации сеанса

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### Пример 2. Тестирование файла конфигурации сеанса конфигурации сеанса

В этом примере мы протестируем файл конфигурации, используемый в конфигурации **ограниченного** сеанса.
Значение параметра **path** является результатом выполнения `Get-PSSessionConfiguration` команды, которая получает **ограниченную** конфигурацию сеанса. Путь к файлу конфигурации сеанса хранится в значении свойства **конфигфилепас** конфигурации сеанса.

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### Пример 3. Тестирование файлов конфигурации всех сеансов

В этом примере функция проверяет все файлы конфигурации сеанса на локальном компьютере. Функция использует `Get-PSSessionConfiguration` командлет для получения всех конфигураций сеанса. В коде внутри `ForEach-Object` цикла отображается путь к файлу и проверяется каждая из конфигураций сеанса.

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

Свойство **конфигфилепас** конфигурации сеанса содержит путь к файлу конфигурации сеанса, который используется в конфигурации сеанса, если таковой имеется.

Если значение свойства **ConfigFilePath** заполнено (значение true), команда получает (печатает) значение свойства **ConfigFilePath**. Затем он использует `Test-PSSessionConfigurationFile` командлет для проверки файла в значении **конфигфилепас** . Параметр **Verbose** возвращает ошибку файла, если файл не проходит проверку.

## PARAMETERS

### -Path

Указывает путь и имя файла конфигурации сеанса (. pssc). Если опустить путь, по умолчанию используется текущая папка. Подстановочные знаки поддерживаются, но они должны разрешаться в один файл. Путь к файлу конфигурации сеанса также можно передать в `Test-PSSessionConfigurationFile` .

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

Путь к файлу конфигурации сеанса можно передать в `Test-PSSessionConfigurationFile` .

## Выходные данные

### System.Boolean

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
