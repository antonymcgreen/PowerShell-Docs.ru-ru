---
description: Реестр
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Registry Provider
ms.openlocfilehash: a45513ca0ab4816793d52771ea1cfa56b239ecbf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232325"
---
# <a name="registry-provider"></a>Поставщик реестра

## <a name="provider-name"></a>Имя поставщика

Реестр

## <a name="drives"></a>Диски

`HKLM:`, `HKCU:`

## <a name="capabilities"></a>Характеристики

**ShouldProcess** , **усетрансактионс**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к разделам реестра, записям и значениям в PowerShell.

## <a name="detailed-description"></a>Подробное описание

Поставщик **реестра** PowerShell позволяет получать, добавлять, изменять, очищать и удалять разделы реестра, записи и значения в PowerShell.

Диски **реестра** — это иерархическое пространство имен, содержащее разделы реестра и подразделы на компьютере. Записи и значения реестра не являются компонентами этой иерархии. Но они являются свойствами каждого из разделов.

Поставщик **реестра** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Разделы реестра представлены как экземпляры класса [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) . Записи реестра представлены как экземпляры класса [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) .

## <a name="navigating-the-registry-drives"></a>Навигация по дискам реестра

Поставщик **реестра** предоставляет свое хранилище данных в виде двух дисков по умолчанию. Расположение реестра HKEY_LOCAL_MACHINE сопоставлено с `HKLM:` диском, и HKEY_CURRENT_USER сопоставлено с `HKCU:` диском. Для работы с реестром можно изменить расположение на `HKLM:` диск с помощью следующей команды.

```powershell
Set-Location HKLM:
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите:

```powershell
Set-Location C:
```

Вы также можете работать с поставщиком **реестра** с любого другого диска PowerShell. Чтобы сослаться на раздел реестра из другого расположения, используйте имя диска ( `HKLM:` , `HKCU:` ) в пути. Используйте обратную косую черту ( \\ ) или косую черту (/), чтобы указать уровень диска **реестра** .

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для командлета [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)и `pwd` являются псевдонимом для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

В последнем примере показан другой синтаксис пути, который можно использовать для навигации по поставщику **реестра** . В этом синтаксисе используется имя поставщика, за которым следуют два двоеточия `::` . Этот синтаксис позволяет использовать полное имя КУСТА вместо имени сопоставленного диска `HKLM` .

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a>Отображение содержимого разделов реестра

Реестр разделен на разделы, подразделы и записи. Дополнительные сведения о структуре реестра см. [в разделе Структура реестра](/windows/desktop/sysinfo/structure-of-the-registry).

В диске **реестра** каждый раздел является контейнером. Ключ может содержать любое количество ключей. Раздел реестра с родительским ключом называется подразделом. С помощью можно `Get-ChildItem` просматривать разделы реестра и `Set-Location` переходить по пути к ключу.

Значения реестра — это атрибуты раздела реестра. На диске **реестра** они называются **свойствами элементов**. Раздел реестра может иметь как дочерние ключи, так и свойства элементов.

В этом примере показана разница между `Get-Item` и `Get-ChildItem` . При использовании `Get-Item` в разделе реестра "Диспетчер очереди" можно просмотреть его свойства.

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

Каждый раздел реестра может также содержать подразделы. При использовании `Get-Item` в разделе реестра подразделы не отображаются. `Get-ChildItem`Командлет покажет вам дочерние элементы ключа "Диспетчер очереди сообщений", включая свойства каждого подраздела. Свойства родительского ключа не отображаются при использовании `Get-ChildItem` .

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

`Get-Item`Командлет также можно использовать в текущем расположении. В следующем примере выполняется переход к разделу реестра "spool" и получение свойств элемента.
Точка `.` используется для указания текущего положения.

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

Дополнительные сведения о командлетах, описываемых в этом разделе, см. в следующих статьях.

-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

## <a name="viewing-registry-key-values"></a>Просмотр значений разделов реестра

Значения разделов реестра хранятся в виде свойств каждого раздела реестра. `Get-ItemProperty`Командлет просматривает свойства раздела реестра, используя указанное имя. Результатом является **PSCustomObject** , содержащий заданное вами свойство.

В следующем примере командлет используется `Get-ItemProperty` для просмотра всех свойств. Сохранение результирующего объекта в переменной позволяет получить доступ к требуемому значению свойства.

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

Указание значения для `-Name` параметра позволяет выбрать указанные свойства и возвращает **PSCustomObject**.  В следующем примере показано различие в выходных данных при использовании `-Name` параметра.

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

Начиная с PowerShell 5,0 `Get-ItemPropertyValue` командлет возвращает только указанное значение свойства.

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.

- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Get-ItemPropertyValue](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a>Изменение значений разделов реестра

`Set-ItemProperty`Командлет установит атрибуты для разделов реестра. В следующем примере используется `Set-ItemProperty` для изменения типа запуска службы диспетчера очереди печати на ручной. В этом примере **старттипе** возвращается к *автоматическому* использованию `Set-Service` командлета.

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

Каждый раздел реестра имеет значение *по умолчанию* . Можно изменить значение *по умолчанию* для раздела реестра с помощью `Set-Item` или `Set-ItemProperty` .

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a>Создание разделов и значений реестра

`New-Item`Командлет создаст разделы реестра с предоставленным именем.
Можно также использовать `mkdir` функцию, которая вызывает `New-Item` командлет внутри.

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

`New-ItemProperty`С помощью командлета можно создавать значения в указанном разделе реестра. В следующем примере создается новое значение DWORD для раздела реестра Контосокомпани.

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> Другие допустимые значения типов см. в разделе динамические параметры этой статьи.

Подробные сведения об использовании командлетов см. в разделе [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).

## <a name="copying-registry-keys-and-values"></a>Копирование разделов и значений реестра

В поставщике **реестра** используйте командлет, чтобы `Copy-Item` скопировать разделы и значения реестра. Используйте `Copy-ItemProperty` командлет, чтобы скопировать только значения реестра.
Следующая команда копирует раздел реестра Contoso и его свойства в указанное расположение "HKLM: \ Софтваре\фабрикам".

`Copy-Item` создает ключ назначения, если он не существует. Если целевой ключ существует, `Copy-Item` создает дубликат исходного ключа в виде дочернего элемента (подраздела) целевого ключа.

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

Следующая команда использует командлет, `Copy-ItemProperty` чтобы скопировать значение "Server" из ключа Contoso в ключ "Fabrikam".

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.

- [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)
- [Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a>Перемещение разделов и значений реестра

`Move-Item` `Move-ItemProperty` Командлеты и ведут себя как аналоги копирования. Если место назначения существует, `Move-Item` перемещает исходный ключ под конечным ключом. Если целевой ключ не существует, исходный ключ перемещается в целевой путь.

Следующая команда перемещает ключ Contoso в путь "HKLM: \ Софтваре\фабрикам".

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

Эта команда перемещает все свойства из "HKLM: \ Софтваре\контосокомпани" в "HKLM: \ Софтваре\фабрикам".

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

Дополнительные сведения о командлетах, используемых в этом разделе, см. в следующих статьях.

- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [Move-ItemProperty](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a>Переименование разделов и значений реестра

Разделы и значения реестра можно переименовывать точно так же, как и файлы и папки.
`Rename-Item` Переименовывает разделы реестра, в то же время `Rename-ItemProperty` переименовывает значения реестра.

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a>Изменение дескрипторов безопасности

Доступ к разделам реестра можно ограничить с помощью `Get-Acl` `Set-Acl` командлетов и. В следующем примере добавляется новый пользователь с полным доступом к разделу реестра "HKLM: \ Софтваре\контосо".

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

Дополнительные примеры и сведения об использовании командлетов см. в следующих статьях.

- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a>Удаление и очистка разделов и значений реестра

Вы можете удалить содержащиеся элементы с помощью **Remove-Item** , но вам будет предложено подтвердить удаление, если элемент содержит что-нибудь еще. В следующем примере предпринимается попытка удалить раздел HKLM: \ Софтваре\контосо.

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

Чтобы удалить содержащиеся элементы без запроса, укажите `-Recurse` параметр.

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

Если требуется удалить все элементы в "HKLM: \ Софтваре\контосо", но не само "HKLM: \ Софтваре\контосо", используйте обратную косую черту, `\` за которой следует подстановочный знак.

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

Эта команда удаляет значение реестра "ContosoTest" из раздела реестра "HKLM: \ Софтваре\контосо".

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

`Clear-Item` Удаляет все значения реестра для ключа. В следующем примере удаляются все значения из раздела реестра "HKLM: \ Софтваре\контосо". Чтобы очистить только конкретное свойство, используйте `Clear-ItemProperty` .

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

Дополнительные примеры и сведения об использовании командлетов см. в следующих статьях.

- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.

### <a name="type-microsoftwin32registryvaluekind"></a>Введите <Microsoft. Win32. RegistryValueKind>

Задает или изменяет тип данных значения реестра. Значение по умолчанию — `String` (REG_SZ).

Этот параметр функционирует соответствующим образом для командлета [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty). Этот параметр также доступен для использования с командлетом [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) на дисках реестра, но он не оказывает никакого влияния.

|Значение | Описание |
| ---- | ----------- |
| `String` | Определяет строку, заканчивающуюся символом NULL. Эквивалентно типу REG_SZ. |
| `ExpandString` | Задает завершающуюся нулем строку, содержащую нераскрытные |
|                | ссылки на переменные среды, развернутые при |
|                | значение извлекается. Эквивалентно типу REG_EXPAND_SZ. |
| `Binary` | Определяет двоичные данные в любой форме. Эквивалентно типу REG_BINARY. |
| `DWord` | Определяет 32-разрядное двоичное число. Эквивалентно типу REG_DWORD. |
| `MultiString` | Указывает массив строк, заканчивающихся нулем, заканчивающийся на |
|               | два пустых символа. Эквивалентно типу REG_MULTI_SZ. |
| `QWord` | Задает 64-разрядное двоичное число. Эквивалентно типу REG_QWORD. |
| `Unknown` | Указывает на неподдерживаемый тип данных реестра, например |
|           | REG_RESOURCE_LIST. |

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a>Использование конвейера

Командлеты поставщика принимают входные данные конвейера. Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика. Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.

## <a name="getting-help"></a>Получение справки

Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.

Чтобы получить разделы справки, настроенные для диска файловой системы, выполните `Get-Help` команду на диске файловой системы или используйте параметр **path** , чтобы указать диск файловой системы.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a>См. также статью

 [about_Providers](../About/about_Providers.md)
