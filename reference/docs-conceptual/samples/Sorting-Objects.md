---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Сортировка объектов
ms.assetid: 8530caa8-3ed4-4c56-aed7-1295dd9ba199
ms.openlocfilehash: 06aa15d89888f1ecbe60b8e1dfb4efebb1d73673
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086057"
---
# <a name="sorting-objects"></a>Сортировка объектов

С помощью командлета `Sort-Object` можно упорядочить отображаемые данные для упрощения их проверки. `Sort-Object` принимает имя одного или нескольких свойств, по значениям которых выполняется сортировка, и возвращает данные, отсортированные по значениям этих свойств.

## <a name="basic-sorting"></a>Базовая сортировка

Рассмотрите проблему перечисления подкаталогов и файлов в текущем каталоге.
Если требуется отсортировать по **LastWriteTime** (времени последней записи), а затем по **Name** имени, это можно сделать, введя следующие команды.

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

Можно также отсортировать объекты в обратном порядке, указав параметр-переключатель **Descending** (по убыванию).

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

## <a name="using-hash-tables"></a>Использование хэш-таблиц

Используя хэш-таблицы в массиве, можно сортировать разные свойства в разном порядке.
Каждая хэш-таблица использует ключ **Expression** для указания имени свойства в виде строки и ключ **Ascending** (по возрастанию) или **Descending** (по убыванию) для указания порядка сортировки по `$true` или `$false`.
Ключ **Expression** является обязательным.
Ключи **Ascending** или **Descending** являются необязательными.

В следующем примере объекты сортируются в порядке убывания по  **LastWriteTime** и в порядке возрастания по **Name**.

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

Вы также можете установить блок скрипта для ключа **Expression**.
При выполнении командлета `Sort-Object` выполняется блок сценария, а его результат используется для сортировки.

В следующем примере объекты сортируются в порядке убывания в промежутке времени между **CreationTime** (временем создания файла) ​​и **LastWriteTime** (временем последней записи).

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

Вы можете опустить имя параметра **Свойство** следующим образом.

```powershell
Sort-Object LastWriteTime, Name
```

Кроме того, вы можете ссылаться на `Sort-Object` по его встроенному псевдониму `sort`.

```powershell
sort LastWriteTime, Name
```

Ключи в хэш-таблицах для сортировки можно сократить следующим образом.

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

В этом примере **e** расшифровывается **выражение**, **d** расшифровывается **по убыванию**и **a** обозначает **по возрастанию**.

Чтобы улучшить читабельность, хэш-таблицы можно поместить в отдельную переменную.

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```