---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Работа с разделами реестра
ms.openlocfilehash: 3feaf6d26db51a507434a6cec1f1095c9013efc8
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736851"
---
# <a name="working-with-registry-keys"></a>Работа с разделами реестра

Так как разделы реестра представляют собой элементы на дисках PowerShell, работа с ними очень похожа на работу с файлами и папками. Одно важное различие заключается в том, что каждый элемент реестрового диска PowerShell представляет собой контейнер, как и папка на диске файловой системы. Однако записи реестра и связанные с ними значения являются свойствами элементов, а не отдельными элементами.

## <a name="listing-all-subkeys-of-a-registry-key"></a>Получение всех подразделов раздела реестра

Показать все элементы, непосредственно содержащиеся в разделе реестра, можно с помощью командлета `Get-ChildItem`. Для отображения скрытых и системных элементов добавьте необязательный параметр **Force**. Например, эта команда отображает элементы, непосредственно расположенные на диске `HKCU:` PowerShell, который соответствует кусту реестра `HKEY_CURRENT_USER`:

```powershell
Get-ChildItem -Path HKCU:\ | Select-Object Name
```

```Output
   Hive: Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER

Name
----
HKEY_CURRENT_USER\AppEvents
HKEY_CURRENT_USER\Console
HKEY_CURRENT_USER\Control Panel
HKEY_CURRENT_USER\DirectShow
HKEY_CURRENT_USER\dummy
HKEY_CURRENT_USER\Environment
HKEY_CURRENT_USER\EUDC
HKEY_CURRENT_USER\Keyboard Layout
HKEY_CURRENT_USER\MediaFoundation
HKEY_CURRENT_USER\Microsoft
HKEY_CURRENT_USER\Network
HKEY_CURRENT_USER\Printers
HKEY_CURRENT_USER\Software
HKEY_CURRENT_USER\System
HKEY_CURRENT_USER\Uninstall
HKEY_CURRENT_USER\WXP
HKEY_CURRENT_USER\Volatile Environment
```

Это разделы верхнего уровня, отображаемые внутри `HKEY_CURRENT_USER` в редакторе реестра (Regedit.exe).

Указать этот путь в реестре можно также, задав имя поставщика реестра с последующей строкой `::`. Полное имя поставщика реестра имеет вид `Microsoft.PowerShell.Core\Registry`, но может быть сокращено до `Registry`. Любая из следующих команд выводит содержимое элементов, непосредственно расположенных внутри `HKCU:`.

```powershell
Get-ChildItem -Path Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Registry::HKCU
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKCU
Get-ChildItem HKCU:
```

Эти команды выводят только элементы, содержащиеся на диске непосредственно, так же как и команда `DIR` оболочки **Cmd.exe** или команда `ls` оболочки UNIX. Для показа вложенных элементов необходимо указать параметр **Recurse**. Для вывода всех разделов реестра в `HKCU:` используется приведенная ниже команда.

```powershell
Get-ChildItem -Path HKCU:\ -Recurse
```

Командлет `Get-ChildItem` позволяет выполнять сложные операции фильтрации с помощью параметров **Path**, **Filter**, **Include** и **Exclude**, но обычно осуществляется лишь фильтрация по имени. Сложную фильтрацию на основе других свойств элементов можно выполнить с помощью командлета `Where-Object`. Следующая команда находит все разделы в `HKCU:\Software`, у которых не более одного подраздела и ровно четыре значения:

```powershell
Get-ChildItem -Path HKCU:\Software -Recurse |
  Where-Object {($_.SubKeyCount -le 1) -and ($_.ValueCount -eq 4) }
```

## <a name="copying-keys"></a>Копирование разделов

Копирование выполняется с помощью командлета `Copy-Item`. Следующая команда копирует подраздел `CurrentVersion` из `HKLM:\SOFTWARE\Microsoft\Windows\` и все его свойства в `HKCU:\`.

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU:
```

Если изучить этот новый раздел в редакторе реестра или с помощью командлета `Get-ChildItem`, вы увидите, что в новом расположении отсутствуют копии подразделов, содержавшихся в исходном разделе. Чтобы скопировать все содержимое контейнера, необходимо указать параметр **Recurse**. Копирование в предыдущем примере можно сделать рекурсивным, если использовать следующую команду:

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU: -Recurse
```

Для копирования файловой системы можно использовать и другие доступные средства. В оболочке Windows PowerShell можно использовать любые средства для редактирования реестра (в том числе **reg.exe**, **regini.exe** и **regedit.exe**), а также COM-объекты, поддерживающие редактирование реестра (такие как **WScript.Shell** и WMI-класс **StdRegProv**).

## <a name="creating-keys"></a>Создание разделов

Создание новых разделов в реестре проще, чем создание нового элемента в файловой системе. Поскольку все разделы реестра являются контейнерами, нет необходимости указывать тип элемента. Достаточно указать явный путь, например:

```powershell
New-Item -Path HKCU:\Software_DeleteMe
```

Для указания раздела можно также использовать путь на основе имени поставщика:

```powershell
New-Item -Path Registry::HKCU\Software_DeleteMe
```

## <a name="deleting-keys"></a>Удаление разделов

Удаление элементов в принципе осуществляется одинаково для всех поставщиков. Следующие команды удаляют элементы, не выводя никаких сообщений:

```powershell
Remove-Item -Path HKCU:\Software_DeleteMe
Remove-Item -Path 'HKCU:\key with spaces in the name'
```

## <a name="removing-all-keys-under-a-specific-key"></a>Удаление всех разделов внутри определенного раздела

Удалить вложенные элементы можно с помощью командлета `Remove-Item`, однако он потребует подтверждения удаления, если элемент сам что-нибудь содержит. Например, при попытке удаления созданного нами подраздела `HKCU:\CurrentVersion` будет отображено следующее:

```powershell
Remove-Item -Path HKCU:\CurrentVersion
```

```Output
Confirm
The item at HKCU:\CurrentVersion\AdminDebug has children and the -recurse
parameter was not specified. If you continue, all children will be removed with
the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Для удаления вложенных элементов без подтверждения следует указать параметр **Recurse**:

```powershell
Remove-Item -Path HKCU:\CurrentVersion -Recurse
```

Если нужно удалить все элементы в `HKCU:\CurrentVersion`, но не сам раздел `HKCU:\CurrentVersion`, вместо этого введите следующее:

```powershell
Remove-Item -Path HKCU:\CurrentVersion\* -Recurse
```
