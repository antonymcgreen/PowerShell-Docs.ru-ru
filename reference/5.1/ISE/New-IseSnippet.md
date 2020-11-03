---
external help file: ISE-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226854"
---
# New-IseSnippet

## Краткий обзор
Создает фрагмент кода интегрированной среды сценариев Windows PowerShell.

## SYNTAX

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`New-ISESnippet`Командлет создает многократно используемый текст "Snippet" для интегрированной среды сценариев Windows PowerShell. Фрагменты кода можно использовать для добавления текста в области сценариев или команд интегрированной среды сценариев Windows PowerShell. Этот командлет доступен только в интегрированной среде сценариев Windows PowerShell.

Начиная с Windows PowerShell 3.0, интегрированная среда сценариев Windows PowerShell содержит набор встроенных фрагментов кода. `New-ISESnippet`Командлет позволяет создавать собственные фрагменты кода для добавления во встроенную коллекцию. Можно просмотреть, изменить, добавить, удалить и совместно использовать файлы фрагментов кода и включать их в модули Windows PowerShell. Чтобы просмотреть фрагменты в интегрированной среде сценариев Windows PowerShell, в меню **Правка** выберите команду **начать фрагменты** или нажмите клавиши <kbd>CTRL</kbd> + <kbd>J</kbd>.

`New-ISESnippet`Командлет создает `<Title>.Snippets.ps1xml` файл в `$home\Documents\WindowsPowerShell\Snippets` каталоге с указанным заголовком. Чтобы включить файл фрагмента кода в модуль, который вы создаете, добавьте этот файл в подкаталог Snippets вашего модуля.

В сеансе, в котором политика выполнения **ограничена** или **AllSigned** , нельзя использовать созданные пользователем фрагменты кода.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Создание Comment-Based фрагмента справки

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

Эта команда создает фрагмент Comment-BasedHelp для интегрированной среды сценариев Windows PowerShell. Он создает файл с именем `Comment-BasedHelp.snippets.ps1xml` в каталоге фрагментов пользователя `$home\Documents\WindowsPowerShell\Snippets` .

### Пример 2. Создание обязательного фрагмента кода

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

В этом примере создается фрагмент кода с именем " **обязательный** " для интегрированной среды сценариев Windows PowerShell. Первая команда сохраняет текст фрагмента в `$M` переменной. Вторая команда использует `New-ISESnippet` командлет для создания фрагмента кода. Команда использует параметр **Force** для перезаписи предыдущего фрагмента с тем же именем.

### Пример 3. копирование обязательного фрагмента из папки в папку назначения

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

Эта команда использует `Copy-Item` командлет для копирования **обязательного** фрагмента из папки, в которой `New-ISESnippet` он размещается в общей папке Server\Share.

## PARAMETERS

### -Author

Указывает автора фрагмента кода. Поле автора отображается в файле фрагмента кода, но не отображается при выборе имени фрагмента в интегрированной среде сценариев Windows PowerShell.

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

### -Каретоффсет

Задает символ текста фрагмента, на который этот командлет помещает курсор. Введите целое число, представляющее позицию курсора (значение 1 представляет первый символ текста). Значение по умолчанию — 0 (ноль) — помещает курсор непосредственно перед первым символом в тексте. Этот параметр создает отступ для текста фрагмента.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Задает описание фрагмента кода. Значение описания отображается при выборе имени фрагмента в интегрированной среде сценариев Windows PowerShell. Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет перезаписывает файлы фрагментов кода с тем же именем в том же расположении. По умолчанию не `New-ISESnippet` перезаписывает файлы.

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

### — Текст

Указывает текстовое значение, которое добавляется при выборе фрагмента кода. Текст фрагмента отображается при выборе имени фрагмента в интегрированной среде сценариев Windows PowerShell. Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Указывает заголовок или имя фрагмента. Заголовок также выступает в качестве имени файла фрагмента. Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Этот командлет не принимает входные данные по конвейеру.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

`New-IseSnippet` сохраняет новые созданные пользователем фрагменты в неподписанных файлах. ps1xml. Таким образом, Windows PowerShell не может добавить их в сеанс, для которого действует политика выполнения **AllSigned** или **Restricted**. В сеансе **Restricted** или **AllSigned** можно создать, получить и импортировать созданные пользователем неподписанные фрагменты кода, но их нельзя использовать в сеансе.

При использовании `New-IseSnippet` командлета в **ограниченном** или **AllSigned** сеансе создается фрагмент, но при попытке Windows PowerShell добавить в сеанс только что созданный фрагмент кода появляется сообщение об ошибке. Чтобы использовать новый фрагмент кода (и другие созданные пользователем неподписанные фрагменты), измените политику выполнения и перезагрузите интегрированную среду сценариев Windows PowerShell.

Дополнительные сведения о политиках выполнения Windows PowerShell см. в разделе about_Execution_Policies.

- Чтобы изменить фрагмент, измените файл фрагмента. Файлы фрагментов кода можно изменить на панели скриптов ИНТЕГРИРОВАНной среды сценариев Windows PowerShell.
- Чтобы удалить добавленный фрагмент, удалите файл фрагмента.
- Нельзя удалить встроенный фрагмент, но можно скрыть все встроенные фрагменты с помощью $psise. Команда Options. Шовдефаултсниппетс = $false ".
- Можно создать фрагмент кода с тем же именем, что и у встроенного фрагмента. Оба фрагмента отображаются в меню фрагментов интегрированной среды сценариев Windows PowerShell.

## Связанные ссылки

[Get-IseSnippet](Get-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
