---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228374"
---
# Get-ItemProperty

## Краткий обзор
Получает свойства указанного элемента.

## SYNTAX

### Путь (по умолчанию)

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`Get-ItemProperty`Командлет возвращает свойства указанных элементов.
Например, с помощью этого командлета можно получить значение свойства LastAccessTime объекта File.
Этот командлет также можно использовать для просмотра записей реестра и их значений.

## Примеры

### Пример 1. Получение сведений о конкретном каталоге

Эта команда возвращает сведения о каталоге C:\Windows.

```powershell
Get-ItemProperty C:\Windows
```

### Пример 2. получение свойств указанного файла

Эта команда возвращает свойства файла "C:\Test\Weather.xls".
Результат передается `Format-List` командлету для вывода выходных данных в виде списка.

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### Пример 3. Отображение имени значения и данных записей реестра в подразделе реестра

Эта команда отображает имя значения и данные каждой из записей реестра, содержащихся в подразделе реестра CurrentVersion.
Обратите внимание, что команда требует наличия диска PowerShell с именем `HKLM:` , сопоставленного с кустом реестра "HKEY_LOCAL_MACHINE".
Диск с таким именем и сопоставлением доступен в PowerShell по умолчанию.
Путь к указанному подразделу реестра может быть задан и другим способом. Необходимо ввести путь, начиная с имени поставщика и двоеточия, как показано ниже:

"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### Пример 4. Получение имени значения и данных записи реестра в подразделе реестра

Эта команда возвращает имя значения и данные записи реестра "ProgramFilesDir" в подразделе реестра "CurrentVersion".
Команда использует параметр **path** для указания подраздела, а параметр Name — для указания имени значения записи.

В команде используется символ обратного или грависом ( \` ), знак продолжения PowerShell, чтобы продолжить выполнение команды во второй строке.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### Пример 5. Получение имен значений и данных записей реестра в разделе реестра

Эта команда возвращает имена значений и данные записей реестра в разделе реестра "PowerShellEngine".
Результаты отображаются в следующем примере вывода.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### Пример 6. получение, форматирование и отображение результатов значений и данных реестра

В этом примере показано, как отформатировать выходные данные `Get-ItemProperty` команды в списке, чтобы упростить просмотр значений и данных реестра, а также упростить их интерпретацию.

Первая команда использует `Get-ItemProperty` командлет для получения записей реестра в подразделе **Microsoft. PowerShell** .
В этом подразделе хранятся параметры оболочки по умолчанию для PowerShell.
Результаты отображаются в следующем примере вывода.

Выходные данные показывают наличие двух записей реестра: Path и ExecutionPolicy.
Если раздел реестра содержит меньше пяти записей, его содержимое по умолчанию отображается в виде таблицы, однако, нередко просматривать записи удобнее в виде списка.

Вторая команда использует ту же `Get-ItemProperty` команду.
Однако на этот раз команда использует оператор конвейера ( `|` ) для отправки результатов команды в `Format-List` командлет.
`Format-List`Команда использует параметр Property со значением "*" (все) для вывода всех свойств объектов в списке.
Результаты отображаются в следующем примере вывода.

В результате отображаются записи реестра Path и ExecutionPolicy, а также несколько менее знакомых свойств объекта раздела реестра.
Другие свойства с префиксом PS являются свойствами пользовательских объектов PowerShell, таких как объекты, представляющие разделы реестра.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## PARAMETERS

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например "User01" или "Domain01\User01", или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.
Если ввести имя пользователя, будет предложено ввести пароль.

> [!WARNING]
> Этот параметр не поддерживается поставщиками, которые устанавливаются вместе с Windows PowerShell.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает из операции.
Значение этого параметра определяет параметр **Path** .
Введите путь к элементу или шаблон, например. «*.txt».
Можно использовать подстановочные знаки.

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

### -Filter

Задает фильтр в формате или на языке поставщика.
Значение этого параметра определяет параметр **Path** .

Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.
Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.
Значение этого параметра определяет параметр **Path** .
Введите путь к элементу или шаблон, например. «*.txt».
Можно использовать подстановочные знаки.

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

### -LiteralPath

Указывает путь к текущему расположению свойства.
В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имена свойств, которые нужно извлечь.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к элементам.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction

Включает команду в активную транзакцию.
Этот параметр доступен только при выполнении транзакции.
Для получения дополнительных сведений см. фрагмент кода ниже.
Этот параметр доступен только при выполнении транзакции.
Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

Можно передать строку, содержащую путь, в `Get-ItemProperty` .

## Выходные данные

### System. Boolean, System. String, System. DateTime

`Get-ItemProperty` Возвращает объект для каждого свойства элемента, которое он получает.
Тип объекта зависит от извлекаемого объекта.
Например в случае диска файловой системы командлет возвращает файл или папку.

## ПРИМЕЧАНИЯ

`Get-ItemProperty`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы получить список поставщиков, доступных в вашем сеансе, введите " `Get-PSProvider` ". Дополнительные сведения см. в разделе about_Providers.

## Связанные ссылки

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)
