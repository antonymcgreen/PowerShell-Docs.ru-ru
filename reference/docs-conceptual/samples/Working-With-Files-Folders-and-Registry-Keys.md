---
ms.date: 07/28/2020
keywords: powershell,командлет
title: Работа с файлами, папками и разделами реестра
description: В этой статье описывается, как работать с разделами реестра с помощью PowerShell.
ms.openlocfilehash: 6f653c1fb409a238aa05658e89261a12e96f6fe1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499983"
---
# <a name="working-with-files-folders-and-registry-keys"></a>Работа с файлами, папками и разделами реестра

Windows PowerShell использует существительное **Item** , чтобы ссылаться на элементы, найденные на диске Windows PowerShell.
При работе с поставщиком FileSystem Windows PowerShell **Item** может быть файлом, папкой или диском Windows PowerShell. Создание списков элементов и работа с ними является критически важной задачей в большинстве административных учреждений, поэтому необходимо подробно обсудить ее.

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a>Перечисление файлов, папок и разделов реестра (Get-ChildItem)

Так как получение коллекции элементов из определенного расположения является обычной задачей, командлет `Get-ChildItem` предназначен специально для возврата всех элементов, найденных в контейнере, например в папке.

Если необходимо вернуть все файлы и папки, которые находятся непосредственно в папке C:\\Windows, введите:

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

Списки выглядят аналогично тем спискам, которые появляются при вводе команды `dir` в **Cmd.exe** или команды `ls` в командной оболочке UNIX.

С помощью параметров командлета `Get-ChildItem` можно создавать очень сложные списки. Далее рассмотрим несколько сценариев. Синтаксис командлета `Get-ChildItem` можно увидеть, введя следующее.

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

Эти параметры можно скомбинировать и сопоставить для получения настраиваемых выходных данных.

### <a name="listing-all-contained-items--recurse"></a>Перечисление всех элементов в контейнере (-Recurse)

Чтобы увидеть оба элемента в папке Windows и все элементы во вложенных папках, используйте параметр **Recurse** для `Get-ChildItem`. В списке отображается все, что находится в папке Windows, а также элементы в ее вложенных папках. Пример:

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a>Фильтрация элементов по имени (-Name)

Чтобы отобразить только имена элементов, используйте параметр **Name** для `Get-Childitem`.

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a>Принудительное перечисление скрытых элементов (-Force)

В выходных данных команды `Get-ChildItem` не отображаются элементы, которые обычно невидимы в проводнике или Cmd.exe. Чтобы показать скрытые элементы, используйте параметр **Force** для `Get-ChildItem`.
Пример:

```powershell
Get-ChildItem -Path C:\Windows -Force
```

Этот параметр называется Force, так как позволяет принудительно переопределить обычное поведение команды `Get-ChildItem`. Параметр Force широко используется для принудительного выполнения действия командлетом. Тем не менее, он не будет выполнять действия, компрометирующие систему безопасности.

### <a name="matching-item-names-with-wildcards"></a>Сопоставление имен элементов с подстановочными знаками

Команда `Get-ChildItem` принимает подстановочные знаки в пути к элементам списка.

Так как сопоставление с подстановочными знаками обрабатывается подсистемой Windows PowerShell, все командлеты, которые принимают подстановочные знаки, используют одну нотацию и имеют одно поведение сопоставления. В нотацию подстановочных знаков Windows PowerShell входит:

- Звездочка (`*`) соответствует нулю или большему количеству вхождений любого символа.

- Знак вопроса (`?`) соответствует ровно одному символу.

- Открывающая квадратная скобка (`[`) и закрывающая квадратная скобка (`]`) заключают в себя набор символов для сопоставления.

Далее приводится несколько примеров работы спецификации из подстановочных знаков.

Чтобы найти в каталоге Windows все файлы, имеющие суффикс `.log` и ровно пять символов в основном имени, введите следующую команду.

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

Чтобы найти в каталоге Windows все файлы с именами, начинающимися на букву `x`, введите следующее.

```powershell
Get-ChildItem -Path C:\Windows\x*
```

Чтобы найти все файлы с именами, начинающимися на x или z, введите следующее.

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

Дополнительные сведения о подстановочных знаках см. в разделе [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).

### <a name="excluding-items--exclude"></a>Исключение элементов (-Exclude)

Вы можете исключить определенные элементы с помощью параметра **Exclude** для `Get-ChildItem`. Это позволит вам выполнить сложную фильтрацию в одном операторе.

Например, вы пытаетесь найти библиотеку службы времени Windows в папке **System32** и все, что вам известно об имени библиотеки, — то, что оно начинается с W и содержит 32.

Такое выражение, как `w*32*.dll`, найдет все библиотеки DLL, которые отвечают этим условиям, но вам может потребоваться дополнительно отфильтровать файлы и пропустить все файлы win32. Эти файлы можно пропустить с помощью параметра **Exclude** с шаблоном `win*`.

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a>Смешение параметров Get-ChildItem

В одной команде можно использовать несколько параметров командлета `Get-ChildItem`. Перед тем как комбинировать параметры, убедитесь, что понимаете принципы сопоставления подстановочных знаков. Например, следующая команда не возвращает результатов:

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

Результаты отсутствуют, даже если существуют две библиотеки, которые начинаются на букву z в папке Windows.

Результаты не возвращены, так как подстановочный знак указан как часть пути. Хотя команда и была рекурсивной, командлет `Get-ChildItem` ограничил элементы до тех, которые находятся в папке Windows с именами, заканчивающимися на `.dll`.

Чтобы указать рекурсивный поиск для файлов, имена которых соответствуют специальному шаблону, используйте параметр **Include** .

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
