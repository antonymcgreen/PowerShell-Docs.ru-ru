---
external help file: ISE-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226857"
---
# Import-IseSnippet

## Краткий обзор
Импортирует фрагменты кода интегрированной среды сценариев в текущий сеанс.

## SYNTAX

### Фромфолдер (по умолчанию)

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### фроммодуле

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

`Import-IseSnippet`Командлет импортирует многократно используемые текстовые фрагменты из модуля или каталога в текущий сеанс. Фрагменты кода немедленно доступны для использования в интегрированной среде сценариев Windows PowerShell. Этот командлет работает только в интегрированной среде сценариев (ISE) Windows PowerShell.

Чтобы просмотреть и использовать импортированные фрагменты, в меню " **Правка** " интегрированной среды сценариев Windows PowerShell нажмите кнопку " **начать фрагменты** " или нажмите клавиши <kbd>CTRL</kbd> + <kbd>J</kbd>.

Импортированные фрагменты кода доступны только в текущем сеансе. Чтобы импортировать фрагменты во все сеансы интегрированной среды сценариев Windows PowerShell, добавьте `Import-IseSnippet` команду в профиль Windows PowerShell или скопируйте файлы фрагментов в каталог локальных фрагментов `$home\Documents\WindowsPowershell\Snippets` .

Чтобы импортировать фрагменты кода, они должны быть правильно отформатированы во фрагментах кода XML для интегрированной среды сценариев Windows PowerShell и сохранены в файлах Snippet.ps1XML. Чтобы создать подходящие фрагменты кода, используйте `New-IseSnippet` командлет. `New-IseSnippet` создает `<SnippetTitle>.Snippets.ps1xml` файл в `$home\Documents\WindowsPowerShell\Snippets` каталоге. Можно переместить или скопировать фрагменты кода в каталог Snippets модуля Windows PowerShell или в любой другой каталог.

`Get-IseSnippet`Командлет, который получает созданные пользователем фрагменты в каталоге локальных фрагментов, не получает импортированные фрагменты.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Импорт фрагментов из каталога

В этом примере фрагменты кода импортируются из `\\Server01\Public\Snippets` каталога в текущий сеанс. Он использует параметр **рекурсии** для получения фрагментов из всех подкаталогов каталога фрагментов кода.

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### Пример 2. Импорт фрагментов кода из модуля

В этом примере выполняется импорт фрагментов кода из модуля **сниппетмодуле** . Команда использует параметр **ListAvailable** для импорта фрагментов, даже если модуль **сниппетмодуле** не импортируется в сеанс пользователя при выполнении команды.

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### Пример 3. Поиск фрагментов в модулях

Этот пример получает фрагменты во всех установленных модулях в переменной среды PSModulePath.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### Пример 4. импорт всех фрагментов модулей

В этом примере выполняется импорт всех фрагментов кода из всех установленных модулей в текущий сеанс. Как правило, выполнять такую команду не требуется, так как модули с фрагментами кода будут использовать `Import-IseSnippet` командлет для импорта при импорте модуля.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### Пример 5. копирование всех фрагментов модулей

В этом примере файлы фрагментов кода копируются из всех установленных модулей в Каталог фрагментов текущего пользователя. В отличие от импортированных фрагменты кода, влияющие только на текущий сеанс, скопированные фрагменты доступны в каждом сеансе интегрированной среды сценариев Windows PowerShell.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## PARAMETERS

### -ListAvailable

Указывает, что этот командлет получает фрагменты кода из модулей, установленных на компьютере, даже если модули не импортируются в текущий сеанс. Если этот параметр не указан и модуль, указанный в параметре **module** , не импортируется в текущий сеанс, попытка получить фрагменты кода из модуля завершается ошибкой.

Этот параметр активен, только если в команде также используется параметр **Module**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module

Импортирует фрагменты кода из указанного модуля в текущий сеанс. Подстановочные знаки не поддерживаются.

Этот параметр импортирует фрагменты кода из файлов Snippet.ps1XML во вложенном каталоге фрагментов кода в пути к модулю, например `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` .

Этот параметр предназначен для использования авторами модулей в сценарии запуска, например, в сценарии, указанном в ключе **ScriptsToProcess** манифеста модуля. Фрагменты кода в модуле не импортируются автоматически вместе с модулем, но `Import-IseSnippet` для их импорта можно использовать команду.

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к каталогу фрагментов кода, в котором этот командлет импортирует фрагменты кода.

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Recurse

Указывает, что этот командлет импортирует фрагменты кода из всех подкаталогов значения параметра **path** .

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Этот командлет не принимает входные данные по конвейеру.

## Выходные данные

### Нет

Этот командлет не создает никакие выходные данные.

## ПРИМЕЧАНИЯ

- Командлет нельзя использовать `Get-IseSnippet` для получения импортированных фрагментов кода. `Get-IseSnippet` Возвращает только фрагменты кода в `$home\Documents\WindowsPowerShell\Snippets` каталоге.
- `Import-IseSnippet` использует статический метод **Load** объектов **Microsoft. PowerShell. host. ISE. ISESnippetCollection** . Также можно использовать метод **Load** фрагментов кода в объектной модели интегрированной среды сценариев Windows PowerShell: `$psISE.CurrentPowerShellTab.Snippets.Load()`
- `New-IseSnippet`Командлет сохраняет новые созданные пользователем фрагменты в неподписанных файлах. ps1xml. Таким образом, Windows PowerShell не может загрузить их в сеанс, для которого действует политика выполнения **AllSigned** или **Restricted**. В сеансе **Restricted** или **AllSigned** можно создать, получить и импортировать созданные пользователем неподписанные фрагменты кода, но их нельзя использовать в сеансе.

  Чтобы использовать неподписанные пользовательские фрагменты кода, `Import-IseSnippet` возвращаемые командлетом, измените политику выполнения, а затем перезапустите интегрированную среду сценариев Windows PowerShell.

  Дополнительные сведения о политиках выполнения Windows PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## Связанные ссылки

[Get-IseSnippet](Get-IseSnippet.md)

[New-IseSnippet](New-IseSnippet.md)
