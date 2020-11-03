---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: 33df0697420249c8a35c792ca71f80c96efaafb7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228981"
---
# Get-TypeData

## Краткий обзор
Получает данные расширенного типа в текущем сеансе.

## Синтаксис

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## Описание

`Get-TypeData`Командлет получает данные расширенного типа в текущем сеансе. Сюда относятся данные типа, которые были добавлены в сеанс по `Types.ps1xml` файлам и динамическим типам данных, добавленным с помощью параметра `Update-TypeData` командлета.

Можно использовать данные расширенного типа, которые `Get-TypeData` возвращают, чтобы проверить данные типа в сеансе и отправить их `Update-TypeData` `Remove-TypeData` командлетам и.

Расширенные данные типа добавляют свойства и методы в объекты в PowerShell. Вы можете использовать добавленные свойства и методы таким же образом, как свойства и методы, определенные в типе объекта. Однако при написании сценариев имейте в виду, что добавленные свойства и методы могут отсутствовать в каждом сеансе PowerShell.

Дополнительные сведения о `Types.ps1xml` файлах см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md). Дополнительные сведения о динамических данных типа, `Update-TypeData` добавляемых командлетом, см `Update-TypeData` . в разделе.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. получение всех данных расширенного типа

Этот пример получает все данные расширенного типа в текущем сеансе.

 ```powershell
Get-TypeData
```

### Пример 2. получение типов по имени

Этот пример возвращает все типы в текущем сеансе, имена которых содержат события.

 ```powershell
"*Eventing*" | Get-TypeData
```

```Output
TypeName                                                  Members
--------                                                  -------
System.Diagnostics.Eventing.Reader.EventLogConfiguration  {}System.Diagnostics.Eventing.Reader.EventLogRecord
                                                          {}System.Diagnostics.Eventing.Reader.ProviderMetadata
                                                          {[ProviderName, System.Management.Automation.Runspaces.AliasProper...
```

### Пример 3. получение блока скрипта, который создает значение свойства

В этом примере получается блок скрипта, который создает значение свойства **EventID** объектов **EventLogEntry** .

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### Пример 4. получение блока сценария, определяющего свойство для указанного объекта

Этот пример получает блок скрипта, который определяет свойство **DateTime** объектов **System. DateTime** в PowerShell.

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

Команда использует `Get-TypeData` командлет для получения данных расширенного типа для типа **System.** данных. Команда получает свойство **Members** объекта **TypeData** .

Свойство **Members** содержит хэш-таблицу свойств и методов, определенных расширенными данными типа. Каждый ключ в хэш-таблице Members — это имя свойства или метода, а каждое значение — это определение значения свойства или метода.

Команда получает ключ **DateTime** в **элементах** и значение свойства **жетскриптблокк** .

В выходных данных показан блок скрипта, который создает значение свойства **DateTime** каждого объекта **System. DateTime** в PowerShell.

## Параметры

### -TypeName

Указывает данные типа как массив только для типов с указанными именами. По умолчанию `Get-TypeData` получает все типы в сеансе.

Введите имена типов или шаблоны имен. Полные имена или шаблоны имен с подстановочными знаками обязательны, даже для типов в пространстве имен System. Поддерживаются подстановочные знаки, и имя параметра **TypeName** является необязательным. Также можно передавать имена типов в `Get-TypeData` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Можно передать имена типов в `Get-TypeData` .

## Выходные данные

### System. Management. Automation. пространства выполнения. TypeData

## Примечания

`Get-TypeData` Возвращает только данные расширенного типа в текущем сеансе. Командлет не получает расширенный тип данных, который находится на компьютере, но не был добавлен к текущему сеансу, например расширенные типы, определенные в модулях, но не импортированные в текущий сеанс.

## Связанные ссылки

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Remove-TypeData](Remove-TypeData.md)

[Update-TypeData](Update-TypeData.md)
