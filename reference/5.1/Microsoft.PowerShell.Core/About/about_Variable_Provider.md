---
description: Переменная
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Variable Provider
ms.openlocfilehash: ff3d457e8d057329544cf1265720fc041a804973
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232277"
---
# <a name="variable-provider"></a>Поставщик переменных

## <a name="provider-name"></a>Имя поставщика

Переменная

## <a name="drives"></a>Диски

`Variable:`

## <a name="capabilities"></a>Характеристики

**ShouldProcess**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к переменным PowerShell и их значениям.

## <a name="detailed-description"></a>Подробное описание

Поставщик **переменных** PowerShell позволяет получать, добавлять, изменять, очищать и удалять переменные PowerShell в текущей консоли.

Поставщик **переменных** PowerShell поддерживает переменные, создаваемые PowerShell, включая автоматические переменные, переменные предпочтений и создаваемые переменные.

**Переменная** Drive является плоским пространством имен, которое содержит только объекты переменных. Переменные не имеют дочерних переменных.

Поставщик **переменных** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

PowerShell также включает набор командлетов, предназначенных специально для просмотра и изменения переменных. При использовании командлетов **переменных** не нужно указывать `Variable:` диск в имени. В этой статье не рассматривается работа с командлетами **переменных** .

- [Get-Variable](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [New-Variable](xref:Microsoft.PowerShell.Utility.New-Variable)
- [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> Средство синтаксического анализа выражений PowerShell также можно использовать для создания, просмотра и изменения значений переменных без использования командлетов. При работе с переменными напрямую используйте знак доллара ( `$` ), чтобы определить имя как переменную и оператор присваивания ( `=` ) для установки и изменения его значения. Например, `$p = Get-Process` создает `p` переменную и сохраняет результаты `Get-Process` команды в ней.

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Переменные могут быть одного из нескольких разных типов. Большинство переменных будут экземплярами `PSVariable` класса. Ниже перечислены другие переменные и их типы.

- `?`Переменная является экземпляром `QuestionMarkVariable` класса.
- `null`Переменная является экземпляром `NullVariable` класса.
- Переменные максимального числа — это экземпляры `SessionStateCapacityVariable` класса.
- `LocalVariable` экземпляры содержат сведения о текущем выполнении, например:
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a>Навигация по переменным дискам

Поставщик **переменных** предоставляет хранилище данных на `Variable:` диске. Для работы с переменными можно изменить расположение на `Variable:` диск ( `Set-Location Variable:` ) или работать с любого другого диска PowerShell. Чтобы сослаться на переменную из другого расположения, используйте имя диска ( `Variable:` ) в пути.

```powershell
Set-Location Variable:
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите:

```powershell
Set-Location C:
```

Вы также можете работать с поставщиком **переменных** с любого другого диска PowerShell. Чтобы сослаться на переменную из другого расположения, используйте имя диска `Variable:` в пути.

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="displaying-the-value-of-variables"></a>Отображение значения переменных

### <a name="get-all-variables-in-the-current-session"></a>Получение всех переменных в текущем сеансе

Эта команда возвращает список всех переменных и их значений в текущем сеансе. Эту команду можно использовать на любом диске PowerShell.

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a>Получение переменной с помощью пути к поставщику

Эта команда извлекает значение переменных, используя путь к поставщику с префиксом доллара ( `$` ). Это действует так же, как и префикс имени переменной с символом доллара ( `$` ).

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a>Получение переменных с помощью подстановочных знаков

Эта команда возвращает переменные с именами, которые начинаются на "max". Эту команду можно использовать на любом диске PowerShell.

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a>Получить значение? Переменная

Эта команда использует `-LiteralPath` параметр командлета [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) для получения значения `?` переменной в пределах `Variable:` диска. `?`Является подстановочным знаком в путях, но не `Get-ChildItem` пытается разрешить подстановочные знаки в значениях `-LiteralPath` параметра.

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a>Получить переменные только для чтения и константы

Эта команда возвращает переменные, которые имеют значения `ReadOnly` или `Constant` для своего свойства **Options** .

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a>Создание переменных

### <a name="create-a-new-variable"></a>Создание новой переменной

Эта команда создает `services` переменную и сохраняет результаты `Get-Service` команды в ней. Так как текущее расположение находится в `Variable:` диске, значением `-Path` параметра является точка ( `.` ), которая представляет текущее расположение.

Круглые скобки вокруг `Get-Service` команды гарантируют, что команда выполняется перед созданием переменной. Если круглые скобки отсутствуют, значением новой переменной станет строка "Get-Service".

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a>Создание переменной с помощью абсолютного пути

Эта команда создает `services` переменную и сохраняет результат `Get-Service` команды в ней.

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 Чтобы создать переменную без значения, опустите оператор присваивания.

## <a name="changing-variables"></a>Изменение переменных

### <a name="rename-a-variable"></a>Переименование переменной

Эта команда использует `Rename-Item` командлет, чтобы изменить имя `a` переменной на `processes` .

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a>Изменение значения переменной

Эта команда использует `Set-Item` командлет, чтобы изменить значение `ErrorActionPreference` переменной на "останавливаться".

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a>Копирование переменной

Эта команда использует `Copy-Item` командлет, чтобы скопировать `processes` переменную в `old_processes` . При этом создается новая переменная с именем `old_processes` , имеющая то же значение, что и `processes` переменная.

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a>Удаление переменной

Эта команда удаляет `serv` переменную из текущего сеанса. Эту команду можно использовать на любом диске PowerShell.

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a>Удаление переменных с помощью параметра-Force

Эта команда удаляет все переменные из текущего сеанса, за исключением переменных, у которых свойство **Options** имеет значение `Constant` . Без `-Force` параметра команда не удаляет переменные, у которых свойство **Options** имеет значение `ReadOnly` .

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a>Присвоение переменной значения NULL

Эта команда использует `Clear-Item` командлет, чтобы изменить значение `processes` переменной на null.

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a>Использование конвейера

Командлеты поставщика принимают входные данные конвейера. Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.
Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.

## <a name="getting-help"></a>Получение справки

Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.

Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a>См. также статью

[about_Variables](../About/about_Variables.md)

[about_Automatic_Variables](../About/about_Automatic_Variables.md)

[about_Providers](../About/about_Providers.md)
