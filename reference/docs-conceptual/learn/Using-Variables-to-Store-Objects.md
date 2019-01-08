---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Использование переменных для хранения объектов
ms.assetid: b1688d73-c173-491e-9ba6-6d0c1cc852de
ms.openlocfilehash: d166ec58dc658c1b134030c9a9592249ee40d4f5
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402475"
---
# <a name="using-variables-to-store-objects"></a>Использование переменных для хранения объектов

PowerShell работает с объектами. PowerShell позволяет создавать именованные объекты, которые называются переменными.
Имена переменных могут содержать, символ подчеркивания и любые буквы или цифры. В PowerShell перед именем переменной всегда используется символ \$.

## <a name="creating-a-variable"></a>Создание переменной

Чтобы создать переменную, можно ввести для нее допустимое имя:

```
PS> $loc
PS>
```

Этот пример не возвращает результаты, так как для переменной `$loc` не задано значение. Создать переменную и присвоить ей значение можно в одном шаге. PowerShell создает переменную, только если она не существует.
В противном случае используется существующая переменная, для которой задается нужное значение. В следующем примере в переменной `$loc` хранятся сведения о текущем расположении:

```powershell
$loc = Get-Location
```

В PowerShell не отображаются выходные данные при вводе этой команды. PowerShell отправляет выходные данные команды Get-Location в переменную `$loc`. В PowerShell данные, которые не были назначены или перенаправлены, выводятся на экран. Ввод переменной `$loc` показывает текущее расположение:

```
PS> $loc

Path
----
C:\temp
```

Команду `Get-Member` можно использовать для отображения сведений о содержимом переменных. Команда `Get-Member` показывает, что `$loc` — это объект **PathInfo**, так же как и выходные данные команды `Get-Location`:

```powershell
PS> $loc | Get-Member -MemberType Property

   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   System.String Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {...
ProviderPath Property   System.String ProviderPath {get;}
```

## <a name="manipulating-variables"></a>Работа с переменными

PowerShell предоставляет несколько команд для работы с переменными. Полный список в удобочитаемой форме можно получить, введя следующее:

```powershell
Get-Command -Noun Variable | Format-Table -Property Name,Definition -AutoSize -Wrap
```

PowerShell также создает несколько системных переменных. Можно использовать командлет `Remove-Variable`, чтобы удалить из текущего сеанса все переменные, которыми PowerShell не управляет. Введите следующую команду для очистки всех переменных:

```powershell
Remove-Variable -Name * -Force -ErrorAction SilentlyContinue
```

После выполнения предыдущей команды командлет `Get-Variable` отображает системные переменные PowerShell.

PowerShell также создает диск переменных. Чтобы отобразить все переменные PowerShell с помощью диска переменных, используйте следующий пример:

```powershell
Get-ChildItem variable:
```

## <a name="using-cmdexe-variables"></a>Использование переменных cmd.exe

PowerShell может использовать одни и те же переменные среды, доступные для любого процесса Windows, в том числе для **cmd.exe**. Эти переменные предоставляются с помощью диска с именем `env:`. Чтобы просмотреть эти переменные, введите следующую команду:

```powershell
Get-ChildItem env:
```

Стандартные командлеты `*-Variable` не предназначены для работы с переменными среды. Доступ к переменным среды осуществляется с помощью префикса диска `env:`. Например, переменная **%SystemRoot%** в командной строке **cmd.exe** содержит имя корневого каталога операционной системы. В PowerShell используйте `$env:SystemRoot` для доступа к этому же значению.

```
PS> $env:SystemRoot
C:\WINDOWS
```

В PowerShell также можно создавать и изменять переменные среды. Переменные среды в PowerShell соответствуют тем же правилам для переменных среды, которые используются в других частях операционной системы. В следующем примере создается переменная среды:

```powershell
$env:LIB_PATH='/usr/local/lib'
```

В именах переменных среды принято использовать прописные буквы, хоть это и не требуется.
