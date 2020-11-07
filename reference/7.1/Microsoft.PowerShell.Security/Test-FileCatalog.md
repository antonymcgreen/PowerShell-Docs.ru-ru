---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 4ea34f547e296567fc0ad728d9279392615836d3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346400"
---
# Test-FileCatalog

## Краткий обзор
`Test-FileCatalog` проверяет, совпадают ли хэши, содержащиеся в файле каталога (. cat), с хэшами реальных файлов, чтобы проверить их подлинность.

Этот командлет поддерживается только в Windows.

## SYNTAX

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Test-FileCatalog` проверяет подлинность файлов, сравнивая хэши файлов каталога (. cat) с хэшами фактических файлов на диске. Если обнаруживает несоответствия, возвращается состояние ValidationFailed. Все эти данные можно получить с помощью параметра -Detailed. Он также отображает состояние подписывания каталога в свойстве Signature, которое эквивалентно вызову `Get-AuthenticodeSignature` командлета для файла каталога. Также можно исключить любые файлы из проверки, указав их в параметре -FilesToSkip.

Этот командлет поддерживается только в Windows.

## Примеры

### Пример 1. Создание и Проверка каталога файлов

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### Пример 2. Проверка каталога файлов с подробным выходом

```powershell
Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## PARAMETERS

### -Каталогфилепас

Путь к файлу каталога (. cat), который содержит хэши, используемые для проверки.

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

### -Detailed

Возвращает дополнительные сведения о более подробном `CatalogInformation` объекте, содержащем проверенные файлы, ожидаемые или фактические хэши, а также подпись Authenticode файла каталога, если он подписан.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilesToSkip

Массив путей, которые не должны проверяться в ходе проверки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Папка или массив файлов, которые должны быть проверены по отношению к файлу каталога.

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

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. IO. DirectoryInfo [], System. String []

Конвейер принимает массив строк или `DirectoryInfo` объектов, представляющих пути к файлам, которые необходимо проверить.

## Выходные данные

### System. Management. Automation. Каталогвалидатионстатус

Возвращаемый по умолчанию тип, содержащий значение `Valid` либо `ValidationFailed` .

### System. Management. Automation. Каталогинформатион

Более подробный объект, возвращаемый при использовании, `-Detailed` который может использоваться для анализа конкретных файлов, которые могут или не прошли проверку, какие хэши ожидались и не были найдены, а также алгоритм, используемый в каталоге.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

## Связанные ссылки

[New-FileCatalog](New-FileCatalog.md)

[PowerShellGet](/powershell/module/PowerShellGet)
