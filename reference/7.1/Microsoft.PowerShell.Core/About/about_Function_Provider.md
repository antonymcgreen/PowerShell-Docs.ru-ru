---
description: Компонент
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Function Provider
ms.openlocfilehash: 8789ceadbefed2dca47c10c26204f3e9ae82d36e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231117"
---
# <a name="function-provider"></a>Поставщик функций

## <a name="provider-name"></a>Имя поставщика
Компонент

## <a name="drives"></a>Диски

`Function:`

## <a name="capabilities"></a>Характеристики

**ShouldProcess**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к функциям, определенным в PowerShell.

## <a name="detailed-description"></a>Подробное описание

Поставщик **функций** PowerShell позволяет получать, добавлять, изменять, очищать и удалять функции и фильтры в PowerShell.

Функция представляет собой именованный блок кода, выполняющий некоторое действие. Если ввести имя функции, выполняется код этой функции. Фильтр представляет собой именованный блок кода, устанавливающий условия выполнения некоторого действия. Можно ввести имя фильтра вместо условия, например в `Where-Object` команде.

Диск **функции** является плоским пространством имен, которое содержит только объекты Function и Filter. Ни функции, ни фильтры не имеют дочерних элементов.

Поставщик **функций** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Каждая функция является экземпляром класса [System. Management. Automation. FunctionInfo](/dotnet/api/system.management.automation.functioninfo) . Каждый фильтр является экземпляром класса [System. Management. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) .

## <a name="navigating-the-function-drive"></a>Навигация по диску функции

Поставщик **функций** предоставляет хранилище данных на `Function:` диске. Для работы с функциями можно изменить расположение на `Function:` диск ( `Set-Location Function:` ). Кроме того, можно работать с другого диска PowerShell. Чтобы сослаться на функцию из другого расположения, используйте имя диска ( `Function:` ) в пути.

```powershell
Set-Location Function:
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите:

```powershell
Set-Location C:
```

Вы также можете работать с поставщиком **функций** из любого другого диска PowerShell. Чтобы сослаться на функцию из другого расположения, используйте имя диска `Function:` в пути.

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-functions"></a>Получение функций

Эта команда возвращает список всех функций в текущем сеансе. Эту команду можно использовать на любом диске PowerShell.

```powershell
Get-ChildItem -Path Function:
```

Поставщик функций не имеет контейнеров, поэтому приведенная выше команда оказывает тот же результат при использовании с `Get-ChildItem` .

```powershell
Get-ChildItem -Path Function:
```

Определение функции можно получить, обратившись к свойству **определения** , как показано ниже.

```powershell
(Get-Item -Path function:more).Definition
```

Кроме того, можно получить определение функции, используя путь к поставщику с префиксом доллара ( `$` ).

```powershell
$function:more
```

### <a name="getting-selected-functions"></a>Получение выбранных функций

Эта команда возвращает `man` функцию с `Function:` диска. `Get-Item`Для получения функции используется командлет. Оператор конвейера ( `|` ) отправляет результат в `Format-Table` . `-Wrap`Параметр направляет текст, который не умещается на строке, на следующую строку. `-Autosize`Параметр изменяет размер столбцов таблицы в соответствии с текстом.

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a>Работа с путями поставщика функций

Эти команды получают функцию с именем `c:` . Первую команду можно использовать на любом диске. Вторая команда используется на `Function:` диске. Поскольку имя функции оканчивается двоеточием, то есть имеет синтаксис имени диска, необходимо указать в пути имя диска. На `Function:` диске можно использовать любой из этих форматов. Во второй команде точка ( `.` ) представляет текущее расположение.

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a>Создание функции

Эта команда использует `New-Item` командлет для создания функции с именем `Win32:` .
Выражение в фигурных скобках является блоком скрипта, который представлен именем функции.

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

Вы также можете создать функцию, введя ее в командной строке PowerShell. Например, типов `Function:Win32: {Set-Location C:\Windows\System32}` . Если вы используете `Function:` диск, можно опустить имя диска.

## <a name="deleting-a-function"></a>Удаление функции

Эта команда удаляет `more:` функцию из текущего сеанса.

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a>Изменение функции

Эта команда использует `Set-Item` командлет для изменения `prompt` функции таким образом, чтобы она отображала время перед путем.

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a>Переименование функции

Эта команда использует `Rename-Item` командлет, чтобы изменить имя `help` функции на `gh` .

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a>Копирование функции

Эта команда копирует `prompt` функцию в `oldPrompt` , эффективно создавая новое имя для блока сценария, связанного с функцией prompt.
Таким образом можно сохранить исходную функцию prompt, если планируется изменить ее.
Свойство **Options** новой функции имеет значение `None` . Чтобы изменить значение свойства **Options** , используйте `Set-Item` .

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.

### <a name="options-systemmanagementautomationscopeditemoptions"></a>Параметры < [System. Management. Automation. Скопедитемоптионс] >

Определяет значение свойства **Options** функции.

- `None`: Нет параметров. Значение по умолчанию — `None`.
- `Constant`: Функция не может быть удалена, и ее свойства нельзя изменить. `Constant` доступен только при создании функции.
  Нельзя изменить параметр существующей функции на `Constant` .
- `Private`: Функция видима только в текущей области видимости
- (не в дочерних областях).
- `ReadOnly`: Свойства функции не могут быть изменены, за исключением использования `-Force` параметра. `Remove-Item`Для удаления функции можно использовать.
- `AllScope`: Функция копируется во все новые создаваемые области.

### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

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
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a>См. также статью

[about_Functions](../About/about_Functions.md)

[about_Providers](../About/about_Providers.md)

