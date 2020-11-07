---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: b5758fdb9fc3e8f604b24fb9c64cad3f95047ec3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347777"
---
# Show-Command

## Краткий обзор
Отображает сведения о команде PowerShell в графическом окне.

## SYNTAX

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

`Show-Command`Командлет позволяет создать команду PowerShell в окне командной строки. Эту функцию командного окна можно использовать для запуска или возврата команды.

`Show-Command` — Это очень полезное средство обучения и обучения. `Show-Command` работает со всеми типами команд, включая командлеты, функции, рабочие процессы и команды CIM.

Без параметров `Show-Command` отображает командное окно, в котором перечислены все доступные команды во всех установленных модулях. Чтобы найти команды в модуле, выберите модуль в соответствующем раскрывающемся списке. Чтобы выбрать команду, щелкните имя команды.

Чтобы использовать командное окно, выберите команду либо с помощью имени, либо щелкнув имя команды в списке **команды** . Каждый набор параметров отображается на отдельной вкладке. Звездочки указывают обязательные параметры. Чтобы ввести значение для параметра, введите значение в текстовое поле или выберите его из раскрывающегося списка. Чтобы добавить параметр переключателя, установите флажок параметра.

Когда все будет готово, щелкните **Copy** , чтобы скопировать созданную команду в буфер обмена, или **Run** , чтобы выполнить команду. Можно также использовать параметр **PassThru** для возврата команды в главное приложение, например консоль PowerShell. Чтобы отменить выбор команды и вернуться к представлению, в котором отображаются все команды, нажмите клавишу CTRL и выберите выбранную команду.

В интегрированной среде сценариев (ISE) PowerShell `Show-Command` по умолчанию отображается вариант окна. Сведения об использовании этого командного окна см. в разделах справки PowerShell ISE.

Этот командлет был повторно введен в PowerShell 7.

Поскольку для этого командлета требуется пользовательский интерфейс, он не работает на Windows Server Core или Windows Nano Server. Этот командлет доступен только в системах Windows, поддерживающих Рабочий стол Windows.

## Примеры

### Пример 1. Открытие окна команд

В этом примере отображается представление окна по умолчанию `Show-Command` . В окне **команды** отображается список всех команд во всех модулях, установленных на компьютере.

```powershell
Show-Command
```

### Пример 2. Открытие командлета в окне "команды"

В этом примере командлет выводится `Invoke-Command` в **командном** окне. Это отображение можно использовать для выполнения `Invoke-Command` команд.

```powershell
Show-Command -Name "Invoke-Command"
```

### Пример 3. Открытие командлета с указанными параметрами

Эта команда открывает `Show-Command` окно для `Connect-PSSession` командлета.

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

Параметры **Height** и **Width** определяют размер командного окна. Параметр **еррорпопуп** отображает окно команды ошибки.

При нажатии кнопки **выполнить** `Connect-PSSession` команда выполняется так же, как и при вводе `Connect-PSSession` команды в командной строке.

### Пример 4. Указание новых значений параметров по умолчанию для командлета

В этом примере `$PSDefaultParameterValues` Автоматическая переменная используется для задания новых значений по умолчанию для параметров **Height** , **Width** и **еррорпопуп** `Show-Command` командлета.

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

Теперь при выполнении `Show-Command` команды новые значения по умолчанию применяются автоматически. Чтобы использовать эти значения по умолчанию в каждом сеансе PowerShell, добавьте `$PSDefaultParameterValues` переменную в профиль PowerShell. Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) и [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).

### Пример 5. Отправка выходных данных в представление сетки

Эта команда показывает, как использовать `Show-Command` `Out-GridView` командлеты и вместе.

```powershell
Show-Command Get-ChildItem | Out-GridView
```

Команда использует командлет, `Show-Command` чтобы открыть командное окно для `Get-ChildItem` командлета.
При нажатии кнопки **выполнить** `Get-ChildItem` команда выполняет команду и создает выходные данные. Оператор конвейера (|) отправляет выходные данные команды в `Get-ChildItem` `Out-GridView` командлет, который отображает `Get-ChildItem` выходные данные в интерактивном окне.

### Пример 6. Отображение команды, созданной в окне "команды"

В этом примере показана команда, созданная в `Show-Command` окне. Команда использует параметр **PassThru** , который возвращает `Show-Command` результаты в виде строки.

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

Например, если вы используете `Show-Command` окно для создания `Get-EventLog` команды, которая получает пять самых новых событий в журнале событий Windows PowerShell, а затем нажмите кнопку **ОК** , команда возвращает выходные данные, показанные выше. Просмотр строки команды поможет вам изучить PowerShell.

### Пример 7. Сохранение команды в переменной

В этом примере показано, как выполнить командную строку, полученную при использовании параметра **PassThru** `Show-Command` командлета. Эта стратегия позволяет видеть команду и использовать ее.

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

Первая команда использует параметр **PassThru** `Show-Command` командлета и сохраняет результаты команды в `$C` переменной. В этом случае мы используем окно, `Show-Command` чтобы создать `Get-EventLog` команду, которая получает пять самых новых событий в журнале событий Windows PowerShell. При нажатии **OK** кнопки ОК `Show-Command` возвращает командную строку, которая сохраняется в `$C` переменной.

### Пример 8. сохранение выходных данных команды в переменную

В этом примере используется параметр **еррорпопуп** для сохранения выходных данных команды в переменной.

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

Помимо отображения ошибок в окне, параметр **ErrorPopup** возвращает выходные данные команды в текущую команду вместо создания новой команды. При выполнении этой команды `Show-Command` открывается окно. Функции окна можно использовать для установки значений параметров. Чтобы выполнить команду, нажмите кнопку **выполнить** в `Show-Command` окне.

## PARAMETERS

### -Еррорпопуп

Указывает, что командлет выводит ошибки во всплывающем окне, а также отображает их в командной строке. По умолчанию, когда команда, выполняемая в `Show-Command` окне, вызывает ошибку, эта ошибка отображается только в командной строке.

Кроме того, при выполнении команды (с помощью кнопки **выполнить** в `Show-Command` окне) параметр **еррорпопуп** возвращает результаты команды текущей команде вместо выполнения команды и возврата ее выходных данных в новую команду. Эту функцию можно использовать для сохранения результатов команды в переменной.

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

### -Height

Задает высоту `Show-Command` окна в пикселях. Введите значение в диапазоне от 300 пикселей до числа пикселей разрешения экрана. Если значение слишком велико для отображения командного окна на экране, `Show-Command` выдает ошибку. Высота по умолчанию: 600 пикселей. Для `Show-Command` команды, включающей параметр **Name** , высота по умолчанию составляет 300 пикселей.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Отображает командное окно для заданной команды. Введите имя одной команды, например имя командлета, функции или команды CIM. Если этот параметр не указан, `Show-Command` отображает командное окно, в котором перечислены все команды PowerShell во всех модулях, установленных на компьютере.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Нокоммонпараметер

Указывает, что этот командлет опускает раздел общих параметров на экране команды. По умолчанию общие параметры отображаются в развертываемом разделе в нижней части командного окна.

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

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете. По умолчанию этот командлет не создает выходные данные. Чтобы выполнить командную строку, скопируйте и вставьте ее в командной строке или сохраните в переменной и используйте `Invoke-Expression` командлет для выполнения строки в переменной.

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

### -Width

Задает ширину `Show-Command` окна в пикселях. Введите значение в диапазоне от 300 пикселей до числа пикселей разрешения экрана. Если значение слишком велико для отображения командного окна на экране, `Show-Command` выдает ошибку. Ширина по умолчанию: 300 пикселей.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать входные данные в `Show-Command` .

## Выходные данные

### Нет, System. String, System. Object

При использовании параметра **PassThru** `Show-Command` возвращает командную строку. При использовании параметра **еррорпопуп** `Show-Command` возвращает выходные данные команды (любой объект). В противном случае не `Show-Command` создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

`Show-Command` не работает в удаленных сеансах.

## Связанные ссылки
