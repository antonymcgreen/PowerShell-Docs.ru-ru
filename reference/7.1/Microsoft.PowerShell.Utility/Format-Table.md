---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 1a90bfada7a21da24cd41ae2ceb8920f13c17c5d
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230397"
---
# Format-Table

## Краткий обзор
Форматирует выходные данные в виде таблицы.

## SYNTAX

### Все

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

`Format-Table`Командлет форматирует выходные данные команды в виде таблицы с выбранными свойствами объекта в каждом столбце. Тип объекта определяет макет и свойства по умолчанию, отображаемые в каждом столбце. Для выбора свойств, которые необходимо отобразить, можно использовать параметр **Property** .

PowerShell использует модули форматирования по умолчанию для определения способа отображения типов объектов. Файлы можно использовать `.ps1xml` для создания пользовательских представлений, отображающих выходную таблицу с указанными свойствами. После создания пользовательского представления используйте параметр **View** , чтобы отобразить таблицу с пользовательским представлением. Дополнительные сведения о представлениях см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

Хэш-таблицу можно использовать для добавления вычисляемых свойств к объекту перед его отображением и указаниям заголовков столбцов в таблице. Чтобы добавить вычисляемое свойство, используйте параметр **Property** или **GroupBy** . Дополнительные сведения о хэш-таблицах см. [здесь](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

## Примеры

### Пример 1. форматирование узла PowerShell

В этом примере отображаются сведения о хост-программе для PowerShell в таблице.

```powershell
Get-Host | Format-Table -AutoSize
```

`Get-Host`Командлет получает объекты **System. Management. Automation. internal. host. интерналхост** , представляющие узел. Объекты отправляются по конвейеру в `Format-Table` и отображаются в таблице. Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.

### Пример 2. форматирование процессов по Басеприорити

В этом примере процессы отображаются в группах, имеющих одно и то же свойство **басеприорити** .

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

`Get-Process`Командлет возвращает объекты, представляющие каждый процесс на компьютере, и отправляет их по конвейеру `Sort-Object` . Объекты сортируются в порядке их свойства **басеприорити** .

Отсортированные объекты отправляются по конвейеру в `Format-Table` . Параметр **GroupBy** упорядочивает данные процесса по группам на основе их значения свойства **басеприорити** . Параметр **переноса** гарантирует, что данные не усекаются.

### Пример 3. форматирование процессов по дате начала

В этом примере отображаются сведения о процессах, запущенных на компьютере. Объекты сортируются и `Format-Table` используют представление для группировки объектов по дате начала.

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

`Get-Process` Возвращает объекты **System. Diagnostics. Process** , представляющие процессы, запущенные на компьютере. Объекты отправляются по конвейеру в `Sort-Object` и сортируются на основе свойства **StartTime** .

Отсортированные объекты отправляются по конвейеру в `Format-Table` . Параметр **View** указывает представление **StartTime** , определенное в `DotNetTypes.format.ps1xml` файле PowerShell для объектов **System. Diagnostics. Process** . Представление **StartTime** преобразует время начала каждого процесса в короткий формат, а затем группирует процессы по дате начала.

`DotNetTypes.format.ps1xml`Файл содержит представление с **приоритетом** для процессов. Вы можете создавать собственные `format.ps1xml` файлы с настраиваемыми представлениями.

### Пример 4. Использование пользовательского представления для вывода таблицы

В этом примере в пользовательском представлении отображается содержимое каталога. Пользовательское представление добавляет столбец **CreationTime** в выходные данные таблицы для объектов **System. IO. DirectoryInfo** и **System. IO. FileInfo** , созданных `Get-ChildItem` .

Пользовательское представление в этом примере было создано из представления, определенного в исходном коде PowerShell. Дополнительные сведения о представлениях и коде, используемом для создания представления этого примера, см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

`Get-ChildItem` Возвращает содержимое текущего каталога, `C:\Test` . Объекты **System. IO. DirectoryInfo** и **System. IO. FileInfo** отправляются по конвейеру.
`Format-Table` использует параметр **View** для указания пользовательского представления **мигЦивиев** , включающего столбец **CreationTime** .

Выход по умолчанию `Format-Table` для `Get-ChildItem` не включает столбец **CreationTime** .

### Пример 5. Использование свойств для вывода таблицы

В этом примере используется параметр **Property** для отображения всех служб компьютера в таблице из двух столбцов, в которой показаны свойства **Name** и **DependentServices** .

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

`Get-Service` Получает все службы на компьютере и отправляет объекты **System. ServiceProcess. ServiceController** по конвейеру. `Format-Table` использует параметр **Property** , чтобы указать, что свойства **Name** и **DependentServices** отображаются в таблице.

**Name** и **DependentServices** — это два свойства типа объекта. Для просмотра всех свойств: `Get-Service | Get-Member -MemberType Properties` .

### Пример 6. форматирование процесса и вычисление его времени выполнения

В этом примере отображается таблица с именем процесса и общим временем выполнения для процессов **блокнота** локального компьютера. Общее время выполнения рассчитывается для каждого процесса путем вычитания времени начала из текущего времени.

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

`Get-Process` Получает все процессы в **блокноте** локального компьютера и отправляет объекты по конвейеру. `Format-Table` Отображает таблицу с двумя столбцами: **processName** , `Get-Process` свойство и **тоталруннингтиме** , вычисляемое свойство.

Свойство **тоталруннингтиме** задается хэш-таблицей с двумя ключами, **меткой** и **выражением** . Ключ **метки** указывает имя свойства. Ключ **выражения** задает вычисление. Выражение получает свойство **StartTime** каждого объекта Process и вычитает его из результата выполнения `Get-Date` команды, которая получает текущие дату и время.

### Пример 7. форматирование процессов в блокноте

В этом примере используется `Get-CimInstance` для получения времени выполнения всех процессов **Notepad** на локальном компьютере. `Get-CimInstance`С помощью параметра **ComputerName** можно получить сведения с удаленных компьютеров.

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

`Get-CimInstance` Возвращает экземпляры класса **WIN32_PROCESS** WMI, описывающие все процессы локального компьютера с именем **notepad.exe** . Объекты процесса хранятся в `$Processes` переменной.

Объекты процесса в `$Processes` переменной отправляются по конвейеру в `Format-Table` , который отображает свойство **processName** и новое вычисляемое свойство, **Общее время выполнения** .

Команда присваивает имя нового вычисляемого свойства, **общего времени выполнения** , с ключом **метки** . Блок сценария ключа **выражения** вычисляет время выполнения процесса путем вычитания даты создания процессов из текущей даты. `Get-Date`Командлет возвращает текущую дату. Дата создания вычитается из текущей даты. Результатом является значение **общего времени выполнения** .

### Пример 8. Устранение ошибок формата

В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday

InvalidArgument: Failed to evaluate expression " $_ / $null ".
```

## PARAMETERS

### -AutoSize

Указывает, что командлет корректирует размер столбца и число столбцов в зависимости от ширины данных. По умолчанию размер и количество столбцов определяются представлением.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayError

Указывает, что командлет отображает ошибки в командной строке. Этот параметр может использоваться в качестве вспомогательного средства отладки при форматировании выражений в `Format-Table` команде и необходимости в устранении неполадок выражений.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Expand

Задает формат объекта коллекции и объектов в коллекции. Этот параметр предназначен для форматирования объектов, поддерживающих интерфейс [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections)). Значение по умолчанию — **енумонли** .
Для этого параметра допустимы следующие значения:

- **Енумонли** : отображает свойства объектов в коллекции.
- **Кореонли** : отображает свойства объекта коллекции.
- **Оба** : отображает свойства объекта коллекции и свойства объектов в коллекции.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что командлет направляет командлет для вывода всех сведений об ошибке. Используйте с параметром **DisplayError** или **ShowError** . По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupBy

Указывает отсортированные выходные данные в отдельных таблицах на основе значения свойства. Например, с помощью **GroupBy** можно перечислить службы в отдельных таблицах на основе их состояния.

Введите выражение или свойство. Параметр **GroupBy** ждет, что объекты сортируются.
Используйте `Sort-Object` командлет перед использованием `Format-Table` для группирования объектов.

Значением параметра **GroupBy** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Имя (или метка) — `<string>`
- Выражение — `<string>` или `<script block>`
- FormatString `<string>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Хидетаблехеадерс

Исключает из таблицы заголовки столбцов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает объекты для форматирования. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Property

Задает свойства объекта, которые будут включены в вывод, и порядок их вывода. Введите одно или несколько имен свойств, разделенных запятыми, или используйте хэш-таблицу для вывода вычисляемого свойства. Разрешено использовать подстановочные знаки.

Если этот параметр не задан, свойства, отображаемые на экране, зависят от свойств первого объекта. Например, если первый объект имеет **свойство** a и **пропертиб** , но последующие объекты имеют **свойство** a, **пропертиб** и **пропертик** , то будут отображены только заголовки **Property** a и **пропертиб** .

Параметр **Property** является необязательным. Нельзя использовать **Свойства** и параметры **представления** в одной команде.

Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Имя (или метка) `<string>`
- Выражение — `<string>` или `<script block>`
- FormatString `<string>`
- Ширина- `<int32>` -должен быть больше `0`
- Alignment — значение может быть `Left` , `Center` или `Right`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Репеасеадер

Повторяет отображение заголовка таблицы после заполнения каждого экрана. Повторяющийся заголовок полезен, когда выходные данные передаются на пейджер, например `less` или в `more` подкачку с помощью средства чтения с экрана.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowError

Этот параметр отправляет ошибки через конвейер. Этот параметр может использоваться в качестве вспомогательного средства отладки при форматировании выражений в `Format-Table` команде и необходимости в устранении неполадок выражений.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -View

Начиная с PowerShell 6, представления по умолчанию определяются в `C#` исходном коде PowerShell. `*.format.ps1xml`Файлы из powershell 5,1 и более ранних версий не существуют в PowerShell 6 и более поздних версиях.

Параметр **View** позволяет указать альтернативный формат или пользовательское представление для таблицы. Можно использовать представления PowerShell по умолчанию или создать пользовательские представления. Дополнительные сведения о создании пользовательского представления см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

Альтернативное и пользовательское представления для параметра **представления** должны использовать формат таблицы, в противном случае — `Format-Table` сбой. Если альтернативное представление является списком, используйте `Format-List` командлет. Если альтернативное представление не является списком или таблицей, используйте `Format-Custom` командлет.

Нельзя использовать **Свойства** и параметры **представления** в одной команде.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wrap

Переносит текст, не помещающийся по ширине столбца, на следующую строку. По умолчанию текст, не уместившийся по ширине столбца, усекается.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Вы можете отправить любой объект, расположенный по конвейеру, в `Format-Table` .

## Выходные данные

### Microsoft.PowerShell.Commands.Internal.Format

`Format-Table` Возвращает объекты форматирования, представляющие таблицу.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[Export-FormatData](Export-FormatData.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Wide](Format-Wide.md)

[Get-FormatData;](Get-FormatData.md)

[Get-Member](Get-Member.md)

[Get-CimInstance](../CimCmdlets/Get-CimInstance.md)

[Update-FormatData](Update-FormatData.md)
