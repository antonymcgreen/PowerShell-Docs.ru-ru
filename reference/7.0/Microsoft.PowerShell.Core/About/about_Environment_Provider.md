---
description: Среда
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Environment Provider
ms.openlocfilehash: ae98e0e8c7d1c4a7e6e975b34e4c6e18b104c01b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232605"
---
# <a name="environment-provider"></a>Поставщик среды

## <a name="provider-name"></a>Имя поставщика
Среда

## <a name="drives"></a>Диски

`Env:`

## <a name="capabilities"></a>Характеристики

**ShouldProcess**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к переменным среды Windows.

## <a name="detailed-description"></a>Подробное описание

Поставщик **среды** PowerShell позволяет получать, добавлять, изменять, очищать и удалять переменные среды и значения в PowerShell.

Переменные **среды** — это переменные с динамическим именованием, описывающие среду, в которой выполняются программы. Windows и PowerShell используют переменные среды для хранения постоянных данных, влияющих на выполнение системы и процесса. В отличие от переменных PowerShell, переменные среды не подчиняются ограничениям области.

Диск **среды** — это плоское пространство имен, содержащее переменные среды, относящиеся к сеансу текущего пользователя. Переменные среды не имеют дочерних элементов.

Поставщик **среды** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Каждая переменная среды является экземпляром класса [System. Collections. DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) . Имя переменной является ключом словаря. Значение переменной среды является значением словаря.

## <a name="navigating-the-environment-drive"></a>Навигация по диску среды

Поставщик **среды** предоставляет хранилище данных на `Env:` диске. Чтобы работать с переменными среды, измените расположение на `Env:` диск ( `Set-Location Env:` ) или с другого диска PowerShell. Чтобы сослаться на переменную среды из другого расположения, используйте `Env:` имя диска в пути.

```powershell
Set-Location Env:
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите:

```powershell
Set-Location C:
```

Вы также можете работать с поставщиком **среды** с любого другого диска PowerShell. Чтобы сослаться на переменную среды из другого расположения, используйте имя диска `Env:` в пути.

Поставщик **среды** также предоставляет переменные среды с помощью префикса переменной `$env:` .  Следующая команда просматривает содержимое переменной среды **ProgramFiles** . `$env:`Префикс переменной можно использовать с любого диска PowerShell.

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

Значение переменной среды также можно изменить с помощью `$env:` префикса переменной.  Все внесенные изменения относятся только к текущему сеансу PowerShell до тех пор, пока он активен.

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-environment-variables"></a>Получение переменных среды

Эта команда выводит список всех переменных среды в текущем сеансе.

```powershell
Get-Item -Path Env:
```

Эту команду можно использовать на любом диске PowerShell.

Поставщик среды не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a>Получить выбранную переменную среды

Эта команда возвращает `WINDIR` переменную среды.

```powershell
Get-ChildItem -Path Env:windir
```

Можно также использовать формат префикса переменной.

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a>Создание переменной среды

Эта команда создает `USERMODE` переменную среды со значением "без прав администратора". `-Path`Значение параметра создает новый элемент на `Env:` диске. Новую переменную среды можно использовать только в текущем сеансе PowerShell до тех пор, пока он активен.

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a>Изменение переменной среды

### <a name="rename-an-environment-variable"></a>Переименование переменной среды

Эта команда использует `Rename-Item` командлет для изменения имени `USERMODE` переменной среды, созданной в `USERROLE` . Не изменяйте имена переменных среды, используемых системой. Хотя эти изменения затрагивают только текущий сеанс, они могут привести к некорректному поведению системы или программы.

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a>Изменение переменной среды

Эта команда использует `Set-Item` командлет, чтобы изменить значение `USERROLE` переменной среды на "Administrator".

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a>Копирование переменной среды

Эта команда копирует значение `USERROLE` переменной среды в `USERROLE2` переменную среды.

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a>Удаление переменной среды

Эта команда удаляет `USERROLE2` переменную среды из текущего сеанса.

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a>Удаление переменной среды с Clear-Item

Эта команда удаляет `USERROLE` переменную среды путем очистки ее значения.

```powershell
Clear-Item -Path Env:USERROLE
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
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a>См. также статью

[about_Providers](../About/about_Providers.md)
