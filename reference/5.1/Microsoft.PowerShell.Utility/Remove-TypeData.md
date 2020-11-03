---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 5ba104eb3183916891d9fbf560dac2ecc4a9f6b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227533"
---
# Remove-TypeData

## Краткий обзор
Удаляет расширенные типы из текущего сеанса.

## Синтаксис

### Ремоветипедатасет (по умолчанию)

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ремоветипесет

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ремовефилесет

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Remove-TypeData`Командлет удаляет данные расширенного типа из текущего сеанса. Действие этого командлета распространяется только на текущий сеанс и на сеансы, созданные в его рамках.

Вы можете добавить свойства и методы в объекты в PowerShell, определив их в `Update-TypeData` командах и `Types.ps1xml` файлах. `Remove-TypeData` удаляет эти расширенные свойства и методы из текущего сеанса. `Remove-TypeData` не удаляет `Types.ps1xml` файлы и не удаляет какие либо расширенные определения типов из `Types.ps1xml` файлов. Дополнительные сведения о `Types.ps1xml` файлах см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Удаление данных типа для указанного типа

В этом примере удаляются все **данные типа из** сеанса, включая данные типа, добавленные `Types.ps1xml` в файл, и данные динамического типа, которые были добавлены в сеанс с помощью `Update-TypeData` командлета.

```powershell
Remove-TypeData -TypeName System.Array
```

### Пример 2. Удаление расширенного типа данных из сеанса

В этом примере показан результат удаления расширенных данных типа из сеанса. Первый `Get-TypeData` получает данные расширенного типа для типа **System. DateTime** . Выходные данные показывают, что для всех объектов **System. DateTime** в PowerShell было добавлено свойство **DateTime** . `Get-Date`Командлет возвращает объект **System. DateTime** . Команда использует точечную нотацию для получения значения свойства **DateTime** объекта **System. DateTime** , `Get-Date` возвращающего значение.

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

Следующий `Get-TypeData` командлет для получения всех данных расширенного типа для типа **System. DateTime** и каналов, которые должны быть `Remove-TypeData` удалены в командлете для удаления данных расширенного типа. Последний `Get-Date` командлет показывает результат удаления расширенных данных типа для типа **System. DateTime** . Так как свойство **System. DateTime** больше не существует, команда для получения его значения возвращает значение Nothing.

### Пример 3. Удаление расширенных типов для модулей

В этом примере удаляются все данные расширенного типа для объектов модуля. При передаче объекта в `Remove-TypeData` `Remove-TypeData` возвращает имя типа объекта и удаляет все данные типа для всех объектов этого типа.

```powershell
Get-Module | Remove-TypeData
```

### Пример 4. Удаление расширенных типов из указанных модулей

В этом примере используется параметр **path** `Remove-TypeData` командлета для удаления расширенных типов, определенных в `Types.ps1xml` файлах, добавленных модулями **PSScheduledJob** и **PSWorkflow** . Эта команда не влияет на данные динамического типа, добавленные с помощью `Update-TypeData` командлета. Эта команда завершается успешно, только если модули импортированы в текущий сеанс.

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

Дополнительные сведения о модулях см. в разделе [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

### Пример 5. Удаление расширенных типов из удаленного сеанса

Этот пример удаляет расширенные типы из удаленного сеанса. Команда использует `Invoke-Command` командлет для удаления данных расширенного типа для всех типов CIM в сеансах в `$S` переменной.

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## Параметры

### -Path

Указывает массив файлов, которые этот командлет удаляет из данных расширенного типа сеанса. Этот параметр обязателен.

Введите пути и имена файлов одного или нескольких `Types.ps1xml` файлов. Подстановочные знаки не поддерживаются. Если путь не указан, расположением по умолчанию является текущий каталог.

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeData

Указывает данные типа, которые этот командлет удаляет из сеанса. Этот параметр обязателен. Введите переменную, содержащую объекты **TypeData** ( **System. Management. Automation. пространства выполнения. TypeData** ) или команду, которая получает объекты **TypeData** , такие как `Get-TypeData` команда. Вы также можете передать объекты **TypeData** в `Remove-TypeData` .

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TypeName

Указывает типы, для которых этот командлет удаляет все данные расширенного типа. Для типов в пространстве имен System вводятся краткие имена. В остальных случаях требуется полное имя типа. Подстановочные знаки не поддерживаются.

Можно передать имена типов в `Remove-TypeData` . При передаче объекта в `Remove-TypeData` `Remove-TypeData` возвращает имя типа объекта и удаляет все данные типа для типа объекта.

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
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

### System. Management. Automation. пространства выполнения. TypeData

Объект **TypeData** , например, `Get-TypeData` возвращаемый командлетом, можно передать в `Remove-TypeData` .

### System.String

Имена типов можно передать в `Remove-TypeData` . При передаче объекта в `Remove-TypeData` `Remove-TypeData` возвращает имя типа объекта и удаляет все данные типа для типа объекта.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## Примечания

`Remove-TypeData` может удалять только данные расширенного типа в текущем сеансе. Он не может удалять данные расширенных типов, которые находятся на компьютере, но не добавлены в текущий сеанс, например расширенные типы, определенные в модулях, которые не импортированы в текущий сеанс.

## Связанные ссылки

[Get-TypeData](Get-TypeData.md)

[Update-TypeData](Update-TypeData.md)
