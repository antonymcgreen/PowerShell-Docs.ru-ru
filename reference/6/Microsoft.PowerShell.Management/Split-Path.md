---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: c65634a295ccca368d7b4d42eb2bf6bb18753e96
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226793"
---
# Split-Path

## Краткий обзор
Возвращает указанную часть пути.

## SYNTAX

### Родительский элемент (по умолчанию)

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### куалифиерсет

```
Split-Path [-Path] <String[]> [[-Qualifier]] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Конечный элемент

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### леафбасесет

```
Split-Path [-Path] <String[]> [-LeafBase] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Расширение

```
Split-Path [-Path] <String[]> [-Extension] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### нокуалифиерсет

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Absolute

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### литералпассет

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Split-Path** возвращает только указанную часть пути, например родительскую папку, подпапку или имя файла.
Он также может получать элементы, на которые ссылается Split Path, и определять, является ли путь относительным или абсолютным.

Этот командлет можно использовать для получения или отправки только выбранной части пути.

## Примеры

### Пример 1. получение квалификатора пути

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

Эта команда возвращает только квалификатор пути.
Квалификатор — это диск.

### Пример 2. Отображение имен файлов

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

Эта команда отображает файлы, на которые ссылается разделенный путь.
Поскольку этот путь разбивается на последний элемент, также известный как лист, команда отображает только имена файлов.

Параметр *Resolve* указывает **разделяемый путь** для отображения элементов, на которые ссылается путь разбиения, вместо отображения пути разбиения.

Как и все команды **с разделением пути** , эта команда возвращает строки.
Он не возвращает объекты **FileInfo** , представляющие файлы.

### Пример 3. получение родительского контейнера

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

Эта команда возвращает только родительские контейнеры пути.
Так как в нем не содержатся параметры для указания разбиения, **разделяемый путь** использует разворачивающееся расположение по умолчанию, которое является *родительским*.

### Пример 4. определяет, является ли путь абсолютным

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

Эта команда определяет, является ли путь относительным или абсолютным.
В этом случае, поскольку путь задается относительно текущей папки, которая представляется точкой (.), она возвращает $False.

### Пример 5. изменение расположения по указанному пути

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

Эта команда изменяет расположение на папку, содержащую профиль PowerShell.

Команда в круглых скобках использует **разделяемый путь** для возврата только родителя пути, хранящегося во встроенной $Profile переменной.
*Родительский* параметр — это параметр расположения разбиения по умолчанию.
Поэтому его можно опустить из команды.
Круглые скобки указывают PowerShell для выполнения команды в первую очередь.
Это удобный способ перехода в папку, имеющую длинное имя пути.

### Пример 6. разбиение пути с помощью конвейера

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

Эта команда использует конвейерный оператор (|) для отправки пути к **разделяемому пути**.
Заключенный в кавычки путь означает, что это единичный маркер.

## PARAMETERS

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.
> Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Extension

Указывает, что этот командлет возвращает только расширение конечного объекта.
Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `.log` .

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Absolute

Указывает, что этот командлет возвращает $True, если путь является абсолютным, и $False, если он является относительным.
Абсолютный путь имеет длину больше нуля и не использует точку (.) для указания текущего пути.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Конечный элемент

Указывает, что этот командлет возвращает только последний элемент или контейнер в пути.
Например, в пути `C:\Test\Logs\Pass1.log` возвращается только Pass1. log.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Леафбасе

Указывает, что этот командлет возвращает только базовое имя конечного объекта.
Например, в пути `C:\Test\Logs\Pass1.log` возвращается только `Pass1` .

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь для разделения.
В отличие от параметра *Path* , значение параметра *LiteralPath* используется строго в том виде, в котором оно указано.
Никакие символы не распознаются как подстановочные знаки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Квалификатор

Указывает, что этот командлет возвращает путь без квалификатора.
Для файловой системы или поставщиков реестра квалификатор —  диска в пути поставщика, например C: или HKCU:.
Например, в пути `C:\Test\Logs\Pass1.log` возвращается только \Test\Logs\Pass1.log.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Родительский элемент

Указывает, что этот командлет возвращает только родительские контейнеры элемента или контейнера, заданного путем.
Например, в пути `C:\Test\Logs\Pass1.log` возвращается к:\тест\логс.
*Родительский* параметр — это параметр расположения разбиения по умолчанию.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь для разделения.
Можно использовать подстановочные знаки.
Если путь содержит пробелы, заключите его в одинарные кавычки.
Можно также передать по конвейеру путь к этому командлету.

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Квалификатор

Указывает, что этот командлет возвращает только квалификатор указанного пути.
Для файловой системы или поставщиков реестра квалификатор —  диска в пути поставщика, например C: или HKCU:.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Разрешить

Указывает, что этот командлет отображает элементы, на которые ссылается результирующий разделяемый путь, вместо отображения элементов пути.

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

### System.String

В этот командлет можно передать по конвейеру строку, содержащую путь.

## Выходные данные

### System. String, System. Boolean

**Разделяемый путь** возвращает текстовые строки.
При указании параметра *Resolve* **Split-Path** возвращает строку, описывающую расположение элементов. Он не возвращает объекты, представляющие элементы, например, объект **FileInfo** или **RegistryKey** .

При указании параметра *Absolute* командлет **Split-Path** возвращает **логическое** значение.

## ПРИМЕЧАНИЯ

* Параметры раздельного расположения ( *квалификатор* , *родительский элемент* , *расширение* , *конечный* объект, *леафбасе* и *квалификатор* ) являются эксклюзивными. Можно использовать только один из них в каждой команде.

  Командлеты, содержащие существительное **path** (командлеты **path** ), работают с именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell.
Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате.
Используйте их в том виде, в котором будут использоваться **dirname** , **нормпас** , **реалпас** , **Join** или другие манипуляторы пути.

  Командлеты **path** можно использовать вместе с несколькими поставщиками.
К ним относятся файловая система, реестр и поставщики сертификатов.

  **Разделяемый путь** предназначен для работы с данными, предоставляемыми любым поставщиком.
Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.
Дополнительные сведения см. в разделе about_Providers.

## Связанные ссылки

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Test-Path](Test-Path.md)
