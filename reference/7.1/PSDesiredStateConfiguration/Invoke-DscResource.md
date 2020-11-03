---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 8425c3e68573fe214ec5de465c8492e0bf99b309
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "93230433"
---
# Invoke-DscResource

## Краткий обзор
Выполняет метод указанного ресурса настройки требуемого состояния PowerShell (DSC).

## SYNTAX

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

Командлет `Invoke-DscResource` выполняет метод указанного ресурса Desired State Configuration (DSC) среды PowerShell.

Этот командлет вызывает ресурс DSC напрямую, не создавая документ конфигурации. С помощью этого командлета продукты управления конфигурацией могут управлять Windows или Linux с помощью ресурсов DSC. Этот командлет также позволяет отлаживать ресурсы, когда модуль DSC работает с включенной отладкой.

> [!NOTE]
> `Invoke-DscResource` — Это экспериментальная функция в PowerShell 7. Чтобы использовать командлет, его необходимо включить с помощью следующей команды.
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## Примеры

### Пример 1. вызов метода Set ресурса путем указания его обязательных свойств

В этом примере вызывается метод **Set** ресурса с именем **ресурс windowsprocess** и предоставляются обязательные свойства **path** и **arguments** для запуска указанного процесса Windows.

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### Пример 2. вызов метода теста ресурса для указанного модуля

В этом примере вызывается метод **теста** ресурса с именем **ресурс windowsprocess** , который находится в модуле с именем **PSDesiredStateConfiguration** .

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## PARAMETERS

### -Method

Указывает метод ресурса, который вызывает этот командлет. Допустимые значения для этого параметра: **Get** , **Set** и **Test** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleName

Указывает имя модуля, из которого этот командлет вызывает указанный ресурс.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имя запускаемого ресурса DSC.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Property

Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

### Microsoft. PowerShell. Commands. ModuleSpecification

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

- Ранее ресурсы Windows PowerShell 5,1 работали в контексте системы, если только они не указаны в контексте пользователя с помощью ключа **PsDscRunAsCredential** . В PowerShell 7,0 ресурсы выполняются в контексте пользователя, а **PsDscRunAsCredential** больше не поддерживается. Предыдущие конфигурации, использующие этот ключ, вызовут исключение.

- Начиная с PowerShell 7, `Invoke-DscResource` больше не поддерживает вызов ресурсов DSC WMI. Сюда входят ресурсы **файл** и **журнал** в **PSDesiredStateConfiguration** .

## Связанные ссылки

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscResource](Get-DscResource.md)
