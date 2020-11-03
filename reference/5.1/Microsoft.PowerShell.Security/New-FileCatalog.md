---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 139ebf10cd0097d55eac521cd81016f8f168d2bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227774"
---
# New-FileCatalog

## Краткий обзор

`New-FileCatalog` создает файл каталога хэшей файлов, который можно использовать для проверки подлинности файла.

## SYNTAX

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`New-FileCatalog` создает [файл каталога Windows](/windows-hardware/drivers/install/catalog-files) для набора папок и файлов.
Этот файл каталога содержит хэши для всех файлов в указанных путях.
Затем пользователи могут распространить каталог вместе с файлами, чтобы пользователи могли проверить, были ли сделаны изменения в папках с момента создания каталога.

Поддерживаются каталоги версий 1 и 2. В версии 1 для создания хэшей файлов используется алгоритм хэширования SHA1 (не рекомендуется), а в версии 2 используется SHA256.
Каталог версии 2 не поддерживается в Windows Server 2008 R2 и Windows 7.
На платформах Windows 8, Windows Server 2012 и более поздней версии рекомендуется использовать каталог версии 2.

## Примеры

### Пример 1. Создание каталога файлов для `Microsoft.PowerShell.Utility`

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## PARAMETERS

### -Каталогфилепас

Путь к файлу или папке, в которую следует поместить файл каталога (. cat).
Если указан путь к папке, будет использоваться имя файла по умолчанию `catalog.cat` .

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

### -Каталогверсион

Принимает `1.0` или `2.0` в качестве возможных значений для указания версии каталога.
`1.0` следует избегать по возможности, если это возможно, так как в нем используется небезопасный алгоритм хэширования SHA-1, а `2.0` используется алгоритм Secure SHA-256, но `1.0` это единственный поддерживаемый алгоритм в Windows 7 и Server 2008R2.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

Конвейер принимает строку, которая используется в качестве имени файла каталога.

## Выходные данные

### System. IO. FileInfo

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Test-FileCatalog](Test-FileCatalog.md)

[PowerShellGet](/powerShell/module/powershellget)
