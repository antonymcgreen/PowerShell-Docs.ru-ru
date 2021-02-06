---
external help file: Microsoft.PowerShell.Utility-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 5c8e963486c0d4f5f3e7d643cb65c752720f37d1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600007"
---
# ConvertFrom-SddlString

## Краткий обзор
Преобразует строку SDDL в пользовательский объект.

## SYNTAX

### Все

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## DESCRIPTION

`ConvertFrom-SddlString`Командлет преобразует строку языка определения дескрипторов безопасности в пользовательский объект **PSCustomObject** со следующими свойствами: owner, Group, дискретионарякл, системакл и равдескриптор.

Свойства Owner, Group, Дискретионарякл и Системакл содержат доступное для чтения текстовое представление прав доступа, указанных в строке SDDL.

Этот командлет появился в PowerShell 5,0.

## Примеры

### Пример 1. Преобразование SDDL прав доступа файловой системы в PSCustomObject

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для папки C:\Windows и сохраняет его в переменной.

Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.

### Пример 2. Преобразование SDDL для прав доступа к реестру в PSCustomObject

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для ключа HKLM: \ софтваре\микрософт\ и сохраняет его в переменной.

Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.

Он использует `-Type` параметр, чтобы указать, что строка SDDL представляет дескриптор безопасности реестра.

### Пример 3. Преобразование SDDL для прав доступа к реестру в PSCustomObject с помощью ConvertFrom-SddlString с параметром и без него `-Type`

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

Первая команда использует `Get-Acl` командлет для получения дескриптора безопасности для ключа HKLM: \ софтваре\микрософт\ и сохраняет его в переменной.

Вторая команда использует `ConvertFrom-SddlString` командлет для получения текстового представления строки SDDL, содержащейся в свойстве SDDL объекта, представляющего дескриптор безопасности.

Он не использует `-Type` параметр, поэтому отображаются права доступа для файловой системы.

Третья команда использует `ConvertFrom-SddlString` командлет с `-Type` параметром, поэтому возвращенные права доступа предназначены для реестра.

## PARAMETERS

### — SDDL

Указывает строку, представляющую дескриптор безопасности в синтаксисе SDDL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type

Указывает тип прав, которые представляет строка SDDL.

Допустимые значения для этого параметра:

- филесистемригхтс
- RegistryRights
- активедиректориригхтс
- мутексригхтс
- семафореригхтс
- криптокэйригхтс
- евентваисандлеригхтс

По умолчанию командлет использует права файловой системы.

Криптокэйригхтс и Активедиректориригхтс не поддерживаются в PowerShell Core.

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку SDDL можно передать в `ConvertFrom-SddlString` .

## Выходные данные

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

## Связанные ссылки

[Язык определения дескрипторов безопасности](/windows/win32/secauthz/security-descriptor-definition-language)
