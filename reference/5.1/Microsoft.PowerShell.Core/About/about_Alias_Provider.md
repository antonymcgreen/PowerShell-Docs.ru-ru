---
description: Псевдоним
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Alias Provider
ms.openlocfilehash: 994bd183f047123502f7e152c59b0d8aeb32a1b9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232461"
---
# <a name="alias-provider"></a>Поставщик псевдонима

## <a name="provider-name"></a>Имя поставщика

Псевдоним

## <a name="drives"></a>Диски

`Alias:`

## <a name="capabilities"></a>Характеристики

**ShouldProcess**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к псевдонимам PowerShell и значениям, которые они представляют.

## <a name="detailed-description"></a>Подробное описание

Поставщик **псевдонимов** PowerShell позволяет получать, добавлять, изменять, очищать и удалять псевдонимы в PowerShell.

Псевдоним — это альтернативное имя для командлета, функции, исполняемого файла, включая скрипты. PowerShell включает набор встроенных псевдонимов. Вы можете добавить собственные псевдонимы в текущий сеанс и профиль PowerShell.

Диск **псевдонима** является плоским пространством имен, которое содержит только объекты-псевдонимы.
У псевдонимов нет дочерних элементов.

Поставщик **псевдонимов** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

В PowerShell имеется набор командлетов, предназначенных для просмотра и изменения псевдонимов. При использовании командлетов **псевдонимов** не нужно указывать `Alias:` диск в имени. В этой статье не рассматривается работа с командлетами **псевдонимов** .

- [Export-Alias](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [Import-Alias](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias)
- [Set-Alias](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Каждый псевдоним является экземпляром класса [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) .

## <a name="navigating-the-alias-drive"></a>Навигация по псевдониму диска

Поставщик **псевдонимов** предоставляет хранилище данных на `Alias:` диске. Для работы с псевдонимами можно изменить расположение на `Alias:` диск с помощью следующей команды:

```powershell
Set-Location Alias:
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите:

```powershell
Set-Location C:
```

Вы также можете работать с поставщиком псевдонимов с любого другого диска PowerShell. Чтобы сослаться на псевдоним из другого расположения, используйте `Alias:` имя диска в пути.

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

### <a name="displaying-the-contents-of-the-alias-drive"></a>Отображение содержимого диска Alias:

Эта команда возвращает список всех псевдонимов, если текущим расположением является `Alias:` диск. Он использует подстановочный знак `*` для указания всего содержимого текущего расположения.

```powershell
PS Alias:\> Get-Item -Path *
```

На `Alias:` диске точка `.` , которая представляет текущее расположение, и символ-шаблон `*` , который представляет все элементы в текущем расположении, имеют одинаковый результат. Например, `Get-Item -Path .` или `Get-Item \*` получить тот же результат.

Поставщик псевдонимов не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a>Получить выбранный псевдоним

Эта команда возвращает `ls` псевдоним.
Так как он содержит путь, его можно использовать на любом диске PowerShell.

```powershell
Get-Item -Path Alias:ls
```

Если вы используете `Alias:` диск, можно опустить имя диска из пути.

Можно также получить определение псевдонима путем добавления префикса к поставщику в виде символа доллара ( `$` ).

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a>Получение всех псевдонимов для конкретного командлета

Эта команда возвращает список псевдонимов, связанных с `Get-ChildItem` командлетом. В нем используется свойство **definition** , в котором хранится имя командлета.

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a>Создание псевдонимов

### <a name="create-an-alias-from-the-alias-drive"></a>Создание псевдонима из диска Alias:

Эта команда создает `serv` псевдоним для `Get-Service` командлета. Поскольку текущее расположение находится на `Alias:` диске, `-Path` параметр не требуется.

Эта команда также использует `-Options` динамический параметр для задания параметра **AllScope** в псевдониме. `-Options`Параметр доступен в `New-Item` командлете, только если находится на `Alias:` диске. Точка ( `.` ) указывает текущий каталог, который является диском псевдонимов.

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a>Создание псевдонима с абсолютным путем

Псевдоним может быть создан для любого элемента, который вызывает команду.
Эта команда создает `np` псевдоним для `Notepad.exe` .

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a>Создание псевдонима для новой функции

Псевдоним может быть создан для любой функции. Эта возможность позволяет создать псевдоним, включающий как командлет, так и его параметры.

Первая команда создает `CD32` функцию, которая изменяет текущий каталог на `System32` каталог. Вторая команда создает `go` псевдоним для `CD32` функции.

После завершения команды можно использовать `CD32` или `go` для вызова функции.

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a>Изменение псевдонимов

### <a name="change-the-options-of-an-alias"></a>Изменение параметров псевдонима

`Set-Item` `-Options` Для изменения значения свойства псевдонима можно использовать командлет с динамическим параметром `-Options` .

Эта команда задает параметры **AllScope** и **ReadOnly** для `dir` псевдонима. Команда использует `-Options` динамический параметр `Set-Item` командлета. `-Options`Параметр доступен в, `Set-Item` если он используется с **псевдонимом** или поставщиком **функций** .

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a>Изменение команды, на которую ссылается псевдоним

Эта команда использует `Set-Item` командлет для изменения `gp` псевдонима, чтобы он предменял `Get-Process` командлет, а не `Get-ItemProperty` командлет.
`-Force`Параметр является обязательным, так как для свойства **Options** `gp` псевдонима задано значение `ReadOnly` . Поскольку команда отправляется с `Alias:` диска, диск не указывается в пути.

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

Это изменение затрагивает четыре свойства, которые определяют связь между псевдонимом и командой. Чтобы просмотреть результат изменения, введите следующую команду:

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a>Переименование псевдонима

Эта команда использует `Rename-Item` командлет, чтобы изменить `popd` псевдоним на `pop` .

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a>Копирование псевдонима

Эта команда копирует `pushd` псевдоним, чтобы `push` для командлета был создан новый псевдоним `Push-Location` .

При создании нового псевдонима его свойство **Description** имеет значение null.
И свойство **параметра** имеет значение `None` . Если команда выполняется из `Alias:` диска, имя диска можно опустить в значении `-Path` параметра.

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a>Удаление псевдонима

Эта команда удаляет `serv` псевдоним из текущего сеанса.
Эту команду можно использовать на любом диске PowerShell.

```powershell
Remove-Item -Path Alias:serv
```

Эта команда удаляет псевдонимы, начинающиеся со знака "s".
Она не удаляет псевдонимы, доступные только для чтения.

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a>Удалить псевдонимы только для чтения

Эта команда удаляет все псевдонимы из текущего сеанса, за исключением тех, `Constant` для которых задано значение свойства **Options** . `-Force`Параметр позволяет команде удалять псевдонимы, свойство **Options** которых имеет значение `ReadOnly` .

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.

### <a name="options-systemmanagementautomationscopeditemoptions"></a>Параметры [System. Management. Automation. Скопедитемоптионс]

Определяет значение свойства **Options** псевдонима.

- **Нет** : нет параметров. Это значение по умолчанию.
- **Константа** : псевдоним не может быть удален, и его свойства нельзя изменить.
  **Константа** доступна только при создании псевдонима. Нельзя изменить параметр существующего псевдонима на **Постоянный**.
- **Частный** : псевдоним является видимым только в текущей области, а не в дочерних областях.
- **ReadOnly** : свойства псевдонима не могут быть изменены, за исключением использования `-Force` параметра. `Remove-Item`Для удаления псевдонима можно использовать.
- **AllScope** : Псевдоним копируется во все новые создаваемые области.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)

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
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a>См. также статью

[about_Aliases](../About/about_Aliases.md)

[about_Providers](../About/about_Providers.md)
