---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: 04346a3bd324b2d7033405546f131d2d56c5a2bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227241"
---
# New-PSDrive

## Краткий обзор
Создает временные и постоянные сопоставленные сетевые диски.

## SYNTAX

### Все

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`New-PSDrive`Командлет создает временные и постоянные диски, сопоставленные с расположением в хранилище данных или связанные с ним, например сетевой диск, каталог на локальном компьютере или раздел реестра, а также постоянные сопоставленные сетевые диски Windows, связанные с расположением файловой системы на удаленном компьютере.

Временные диски существуют только в текущем сеансе PowerShell и в сеансах, создаваемых в текущем сеансе. Они могут иметь любое имя, допустимое в PowerShell, и могут быть сопоставлены с любым локальным или удаленным ресурсом. Вы можете использовать временные диски PowerShell для доступа к данным в связанном хранилище данных так же, как и с любым подключенным сетевым диском. Можно изменить расположение на диске, используя и `Set-Location` получить доступ к содержимому диска с помощью `Get-Item` или `Get-ChildItem` .

Поскольку временные диски известны только для PowerShell, к ним нельзя получить доступ с помощью проводника, инструментарий управления Windows (WMI) (WMI), модели COM, Microsoft .NET Framework или с помощью таких средств, как **net use**.

В PowerShell 3,0 добавлены следующие функции `New-PSDrive` :

- Подключенные сетевые диски. Параметр **Persist** параметра можно использовать `New-PSDrive` для создания сопоставленных сетевых дисков Windows. В отличие от временных дисков PowerShell, сопоставленные сетевые диски Windows не зависят от сеанса. Они сохраняются в Windows и могут управляться с помощью стандартных средств Windows, таких как проводник и **net use**. Сопоставленным сетевым дискам должно быть присвоено имя буквы диска, и они должны подключаться к расположению удаленной файловой системы. Если команда находится локально, без точки-источника, параметр **Persist** не сохраняет создание **PSDrive** за пределами области, в которой выполняется команда. Если вы используете `New-PSDrive` внутри сценария и хотите, чтобы диск сохранялся бессрочно, необходимо создать точку сценария с точкой. Для достижения лучших результатов, чтобы принудительно сохранить новый диск в течение неограниченного времени, добавьте в команду параметр **Scope** и присвойте ему значение **Global**. Дополнительные сведения об использовании источников см. в разделе [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).
- Внешние диски. При подключении к компьютеру внешнего диска PowerShell автоматически добавляет **PSDrive** в файловую систему, представляющую новый диск. Не нужно перезапускать PowerShell. Аналогично, когда внешний диск отключается от компьютера, PowerShell автоматически удаляет **PSDrive** , представляющий удаленный диск.
- Учетные данные для UNC-путей.

Если параметр **root** имеет путь UNC, например `\\Server\Share` , для создания **PSDrive** используется учетные данные, указанные в значении параметра **Credential** . В противном случае **учетные данные** не вступают в силу при создании новых дисков файловой системы.

В некоторых примерах кода используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости. Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## Примеры

### Пример 1. Создание временного диска, сопоставленного с общей сетевой папкой

В этом примере создается временный диск PowerShell, сопоставленный с общей сетевой папкой.

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

`New-PSDrive` использует параметр **Name** для указания диска PowerShell с именем `Public` и параметр **psprovider** для указания `FileSystem` поставщика PowerShell. Параметр **root** указывает UNC-путь к сетевой папке.

Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path Public:`

### Пример 2. Создание временного диска, сопоставленного с локальным каталогом

В этом примере создается временный диск PowerShell, который предоставляет доступ к каталогу на локальном компьютере.

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

Сплаттинг создает ключи и значения параметров. Параметр **Name** указывает имя диска **MyDocs**. Параметр **psprovider** указывает `FileSystem` поставщика PowerShell. **Root** указывает каталог локального компьютера. Параметр **Description** описывает назначение диска. `New-PSDrive` использует параметры сплаттед для создания `MyDocs` диска.

Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path MyDocs:`

### Пример 3. Создание временного диска для раздела реестра

В этом примере создается временный диск PowerShell, который предоставляет доступ к разделу реестра. Он создает диск с именем MyCompany, сопоставленный с `HKLM:\Software\MyCompany` разделом реестра.

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

`New-PSDrive` использует параметр **Name** для указания диска PowerShell с именем `MyCompany` и параметр **psprovider** для указания `Registry` поставщика PowerShell. Параметр **root** указывает расположение реестра.

Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path MyCompany:`

### Пример 4. Создание постоянного сопоставленного сетевого диска с использованием учетных данных

Этот пример сопоставляет сетевой диск, который прошел проверку подлинности, с учетными данными учетной записи службы домена.
Дополнительные сведения об объекте **PSCredential** , в котором хранятся учетные данные и о том, как хранятся пароли в качестве **SecureString** , см. в описании параметра **Credential** .

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> Помните, что при использовании приведенного выше фрагмента в скрипте задайте для параметра **области** значение "Global", чтобы диск сохранялся вне текущей области.

`$cred`Переменная сохраняет объект **PSCredential** , содержащий учетные данные учетной записи службы. `Get-Credential` предлагает ввести пароль, хранящийся в **SecureString**.

`New-PSDrive` создает сопоставленный сетевой диск с помощью нескольких параметров. **Имя** указывает `S` букву диска, которую Windows принимает. и **root** определяют `\\Server01\Scripts` расположение на удаленном компьютере. **Сохранить** создает сопоставленный сетевой диск Windows, сохраненный на локальном компьютере. **Psprovider** указывает `FileSystem` поставщика. **Учетные** данные используют `$cred` переменную для получения учетных данных учетной записи службы для проверки подлинности.

Подключенный диск можно просмотреть на локальном компьютере в сеансах PowerShell, проводнике и с помощью таких средств, как **net use**. Чтобы просмотреть содержимое сеанса PowerShell, выполните следующие действия. `Get-ChildItem -Path S:`

### Пример 5. Создание постоянных и временных дисков

В этом примере показано различие между постоянным подключенным сетевым диском и временным диском PowerShell, сопоставленным с одной и той же сетевой папкой.

Если закрыть сеанс PowerShell, а затем открыть новый сеанс, временная память `PSDrive:` недоступна, а постоянный `X:` диск будет доступен. При принятии решения о том, какой метод следует использовать для подключения сетевых дисков, рассмотрите способ использования диска. Например, должен ли он быть постоянным и должен ли диск отображаться для других компонентов Windows.

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## PARAMETERS

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на это действие. По умолчанию используется текущий пользователь.

Начиная с PowerShell 3,0, если параметр **root** является путем в формате UNC, для создания дисков файловой системы можно использовать учетные данные.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description

Указывает краткое описание диска. Введите любую строку.

Чтобы просмотреть описания всех дисков сеанса, `Get-PSDrive | Format-Table Name, Description` .

Чтобы просмотреть описание конкретного диска, введите `(Get-PSDrive <DriveName>).Description` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имя нового диска. Для постоянных сопоставленных сетевых дисков используйте букву диска. Для временных дисков PowerShell вы не ограничены буквами дисков, используйте любую допустимую строку.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Сохранить

Указывает, что этот командлет создает сопоставленный сетевой диск Windows. Параметр **Persist** доступен только в Windows.

Сопоставленные сетевые диски сохраняются в Windows на локальном компьютере. Они являются постоянными, а не специфичными для сеанса, и их можно просматривать и контролировать в проводнике и других средствах.

Если команда выполняется локально, без точки с точками, параметр **Persist** не сохраняет создание **PSDrive** за пределами области, в которой выполнялась команда. Если вы запустили `New-PSDrive` внутри скрипта и хотите, чтобы новый диск сохранялся бессрочно, необходимо создать точку сценария с точкой. Для получения наилучших результатов, чтобы принудительно сохранить новый диск, укажите **Global** в качестве значения параметра **Scope** и включите **хранимые** команды.

Имя диска должно быть буквой, например `D` или `E` . Значение параметра **root** должно быть UNC-путем к другому компьютеру. Значение параметра **psprovider** должно быть `FileSystem` .

Чтобы отключить сопоставленный сетевой диск Windows, используйте `Remove-PSDrive` командлет. При отключении сопоставленного сетевого диска Windows сопоставление удаляется без возможности восстановления с компьютера, а не только из текущего сеанса.

Сопоставленные сетевые диски относятся только к учетной записи пользователя. Подключенные диски, созданные в сеансах с повышенными привилегиями или сеансах с использованием учетных данных другого пользователя, не видны в сеансах, запущенных с использованием других

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSProvider

Указывает поставщика PowerShell, который поддерживает диски такого типа.

Например, если диск связан с сетевой папкой или каталогом файловой системы, то поставщиком PowerShell является `FileSystem` . Если диск связан с разделом реестра, поставщик имеет значение `Registry` .

Временные диски PowerShell могут быть связаны с любым поставщиком PowerShell. Сопоставленные сетевые диски могут быть связаны только с `FileSystem` поставщиком.

Чтобы просмотреть список поставщиков в сеансе PowerShell, используйте `Get-PSProvider` командлет.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Root

Указывает расположение хранилища данных, с которым сопоставлен диск PowerShell.

Например, укажите сетевую папку, например, `\\Server01\Public` локальный каталог, например `C:\Program Files` , или раздел реестра, например `HKLM:\Software\Microsoft` .

Временные диски PowerShell могут быть связаны с локальным или удаленным расположением на любом поддерживаемом диске поставщика. Сопоставленные сетевые диски можно связать только с расположением файловой системы на удаленном компьютере.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope

Указывает область для диска. Допустимые значения для этого параметра: **Global** , **Local** и **script** или Number, относящихся к текущей области. Области с номером 0 по числу областей. Текущий номер области равен 0, а его родительский элемент — 1. Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете конвейерировать входные данные для этого командлета.

## Выходные данные

### System.Management.Automation.PSDРивеинфо

## ПРИМЕЧАНИЯ

`New-PSDrive` предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы получить список поставщиков, доступных в вашем сеансе, используйте `Get-PSProvider` . Дополнительные сведения о поставщиках см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Сопоставленные сетевые диски относятся только к учетной записи пользователя. Подключенные диски, созданные в сеансах с повышенными привилегиями или сеансах с использованием учетных данных другого пользователя, не видны в сеансах, запущенных с использованием других

## Связанные ссылки

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-PSDrive](Get-PSDrive.md)

[Remove-PSDrive](Remove-PSDrive.md)
