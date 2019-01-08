---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Сортировка объектов
ms.assetid: 8530caa8-3ed4-4c56-aed7-1295dd9ba199
ms.openlocfilehash: 06aa15d89888f1ecbe60b8e1dfb4efebb1d73673
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402232"
---
# <a name="sorting-objects"></a>Сортировка объектов

Можно упорядочить отображаемые данные для упрощения проверки при помощи `Sort-Object` командлета. `Sort-Object` принимает имя одного или нескольких свойств для сортировки и возвращает данные, сортируются по значениям этих свойств.

## <a name="basic-sorting"></a>Основная сортировка

Рассмотрим проблему перечисления подкаталоги и файлы в текущем каталоге.
Если мы хотим выполнить сортировку по **LastWriteTime** и затем по **имя**, мы можно сделать, введя:

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

Можно также отсортировать объекты в обратном порядке, указав **по убыванию** параметр-переключатель.

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a>С помощью хэш-таблицы

Можно сортировать разным свойствам в разном порядке с помощью хэш-таблицы в массиве.
Использует каждую хэш-таблицу **выражение** ключей, чтобы задать имя свойства как строка и **по возрастанию** или **по убыванию** клавишу, чтобы указать порядок сортировки по `$true` или `$false`.
**Выражение** ключ является обязательным.
**По возрастанию** или **по убыванию** ключ не является обязательным.

Следующий пример сортирует объекты по убыванию **LastWriteTime** порядка и по возрастанию **имя** заказа.

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

Можно также задать блок сценария **выражение** ключ.
При выполнении `Sort-Object` командлета, выполняется блок сценария, и результат используется для сортировки.

Следующий пример сортирует объекты в убывающем порядке по период времени между **CreationTime** и **LastWriteTime**.

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a>Советы

Можно опустить **свойство** имя параметра, как показано ниже:

```powershell
Sort-Object LastWriteTime, Name
```

Кроме того, можно ссылаться на `Sort-Object` по его встроенному псевдониму `sort`:

```powershell
sort LastWriteTime, Name
```

Ключи в хэш-таблицы для сортировки можно сократить следующим образом:

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

В этом примере **e** расшифровывается **выражение**, **d** расшифровывается **по убыванию**и **a** обозначает **по возрастанию**.

Для повышения удобочитаемости можно поместить в отдельную переменную хэш-таблиц:

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```