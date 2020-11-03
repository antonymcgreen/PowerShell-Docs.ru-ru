---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: f5000ec88defda441d5f31f6ead5d8c37412857b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228826"
---
# Get-PSDrive

## Краткий обзор
Получает диски в текущем сеансе.

## SYNTAX

### Имя (по умолчанию)

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

### литералнаме

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-PSDrive`Командлет возвращает диски в текущем сеансе. Можно получить определенный диск или все диски в сеансе.

Этот командлет получает следующие типы дисков:

- Логические диски Windows на компьютере, включая диски, сопоставленные с сетевыми общими папками.
- Диски, предоставляемые поставщиками PowerShell (например, Certificate:, функция: и псевдонимы дисков), а также диски HKLM: и HKCU:, предоставляемые поставщиком реестра Windows PowerShell.
- Указанные сеансом временные диски и постоянные сопоставленные сетевые диски, созданные с помощью командлета New-PSDrive.

Начиная с Windows PowerShell 3,0, параметр **Persist** `New-PSDrive` командлета может создавать сопоставленные сетевые диски, сохраненные на локальном компьютере и доступные в других сеансах. Дополнительные сведения см. в разделе New-PSDrive.

Кроме того, начиная с Windows PowerShell 3.0, когда внешний диск подключается к компьютеру, Windows PowerShell автоматически добавляет в файловую систему объект PSDrive, представляющий новый диск.
Перезапускать Windows PowerShell не нужно. Аналогичным образом, когда внешний диск отключается от компьютера, Windows PowerShell автоматически удаляет объект PSDrive, представляющий удаленный диск.

## Примеры

### Пример 1. Получение дисков в текущем сеансе

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

Эта команда получает диски в текущем сеансе.

В выходных данных отображается жесткий диск (C:), дисковод компакт-дисков (D:), а также диски, предоставляемые поставщиками Windows PowerShell (псевдоним:, CERT:, env:, функция:, HKCU:, HKLM: и переменная:).

### Пример 2. получение диска на компьютере

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

Эта команда получает диск D: на компьютере. Обратите внимание, что за буквой диска в команде не следует двоеточие.

### Пример 3. получение всех дисков, поддерживаемых поставщиком файловой системы Windows PowerShell

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

Эта команда получает все диски, которые поддерживаются поставщиком FileSystem оболочки Windows PowerShell. Сюда входят фиксированные диски, логические разделы, сопоставленные сетевые диски и временные диски, созданные с помощью командлета New-PSDrive.

### Пример 4. Проверьте, используется ли диск в качестве имени диска Windows PowerShell.

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

Эта команда проверяет, используется ли диск X в качестве имени диска Windows PowerShell.
Если это не так, команда использует `New-PSDrive` командлет для создания временного диска, сопоставленного с ключом реестра HKLM: \ Software.

### Пример 5. Сравнение типов системных дисков

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

В этом примере сравниваются типы дисков файловой системы, отображаемые в, `Get-PSDrive` отображаемые с помощью других методов. В этом примере демонстрируются различные способы отображения дисков в Windows PowerShell и показано, что диски конкретного сеанса, созданные с помощью командлета New-PSDrive, доступны только в Windows PowerShell.

Первая команда использует `Get-PSDrive` для получения всех дисков файловой системы в сеансе. Это относится к фиксированным дискам (C: и D:), подключенному сетевому диску (G:) , созданного с помощью параметра **Persist** среды `New-PSDrive` , и диска PowerShell (T:) , который был создан с помощью `New-PSDrive` без параметра **Persist** .

Команда **net use** отображает сопоставленные сетевые диски Windows. в этом случае отображается только диск G. Он не отображает диск X:, созданный `New-PSDrive` . Он показывает, что диск G: также сопоставлен с \\ \\ музыкой \\ гратефулдеад.

Третья команда использует метод **GetDrives** класса **System.IO.DriveInfo** Microsoft .NET Framework. Эта команда получает диски файловой системы Windows, включая диск G:, но не получает диски, созданные `New-PSDrive` .

Четвертая команда использует `Get-CimInstance` командлет для получения экземпляров класса **Win32_LogicalDisk** . Он возвращает диски A:, C:, D:, E: и G:, но не диски, созданные `New-PSDrive` .

Последняя команда использует `Get-CimInstance` командлет для вывода экземпляров класса **Win32_NetworkConnection** . Как и при **использовании команды net use** , она возвращает только постоянный диск G:, созданный `New-PSDrive` .

## PARAMETERS

### -Литералнаме

Задает имя диска.

Значение параметра **LiteralName** используется точно так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если имя включает escape-символы, заключите их в одинарные кавычки. Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает в виде массива строк имя или имя дисков, которые этот командлет получает в операции.
Введите имя диска или букву без двоеточия (:).

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSProvider

Указывает в качестве массива строк поставщик Windows PowerShell. Этот командлет возвращает только диски, поддерживаемые этим поставщиком. Введите имя поставщика, например FileSystem, Registry или Certificate.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope

Указывает область, в которой этот командлет получает диски.

Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Сценарий
- число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель). По умолчанию используется значение Local.

Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### System.Management.Automation.PSDРивеинфо

Этот командлет возвращает объекты, представляющие диски в сеансе.

## ПРИМЕЧАНИЯ

* Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы получить список поставщиков, доступных в вашем сеансе, используйте `Get-PSProvider` командлет. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
* Сопоставленные сетевые диски, созданные с помощью параметра **Persist** командлета New-PSDrive, относятся к учетной записи пользователя. Подключенные сетевые диски, созданные в сеансах с параметром Запуск от имени администратора или с учетными данными другого пользователя, не отображаются в сеансах, запущенных без явных учетных данных или с учетными данными текущего пользователя.

## Связанные ссылки

[New-PSDrive](New-PSDrive.md)

[Remove-PSDrive](Remove-PSDrive.md)

[Get-PSProvider](Get-PSProvider.md)
