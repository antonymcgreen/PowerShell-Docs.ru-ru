---
description: Описывает, как поставщики PowerShell предоставляют доступ к данным и компонентам, которые не были бы легко доступны в командной строке. Данные представлены в единообразном формате, который напоминает диск файловой системы.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 08ea1679516b58e326eeb3d90fc1aaef4e983a34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232681"
---
# <a name="about-providers"></a>О поставщиках

## <a name="short-description"></a>Краткое описание
Описывает, как поставщики PowerShell предоставляют доступ к данным и компонентам, которые не были бы легко доступны в командной строке.
Данные представлены в единообразном формате, который напоминает диск файловой системы.

## <a name="long-description"></a>Подробное описание

Поставщики PowerShell — это программы .NET, обеспечивающие доступ к специализированным хранилищам данных для упрощения просмотра и управления. Данные отображаются на диске, а доступ к данным осуществляется по пути, как и на жестком диске. Для управления данными на диске поставщика можно использовать любой из встроенных командлетов, поддерживаемых поставщиком. И можно использовать пользовательские командлеты, разработанные специально для данных.

Поставщики также могут добавлять динамические параметры во встроенные командлеты. Эти параметры доступны только при использовании командлета с данными поставщика.

## <a name="built-in-providers"></a>Встроенные поставщики

В PowerShell имеется набор встроенных поставщиков, которые можно использовать для доступа к различным типам хранилищ данных.

| Поставщик   |   Диск (ы)  |OutputType                                                    |
|----------- |------------ |--------------------------------------------------------------|
|Псевдоним       |Alias:       |System.Management.Automation.AliasInfo                        |
|Сертификат |Cert:        |Microsoft. PowerShell. Commands. X509StoreLocation               |
|            |             |System.Security.Cryptography.X509Certificates.X509Certificate2|
|Среда |Env:         |System. Collections. DictionaryEntry                            |
|FileSystem  |C: (*)       |System. IO. FileInfo                                            |
|            |             |System.IO.DirectoryInfo                                       |
|Компонент    |Функция:    |System.Management.Automation.FunctionInfo                     |
|Реестр    |HKLM: HKCU:  |Microsoft. Win32. RegistryKey                                   |
|Переменная    |Variable:    |System. Management. Automation. PSVariable                       |
|WSMan       |WSMan:       |Microsoft.WSMan.Management.WSManConfigContainerElement        |

(*) Диски файловой системы различаются в каждой системе.

Вы также можете создавать собственные поставщики PowerShell, а также устанавливать поставщиков, разрабатываемых другими разработчиками. Чтобы получить список поставщиков, доступных в вашем сеансе, введите:

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a>Установка и удаление поставщиков

Поставщики обычно устанавливаются с помощью модулей PowerShell. При импорте модуля в сеанс загружается поставщик. Невозможно удалить встроенные поставщики. Можно удалить поставщиков, загруженных другими модулями.

Вы можете выгрузить поставщик из текущего сеанса с помощью `Remove-Module` командлета. Этот командлет не удаляет поставщик, но делает его недоступным в сеансе.

Кроме того, с помощью `Remove-PSDrive` командлета можно удалить все диски из текущего сеанса. Эти данные на диске не затрагиваются, но диск больше не доступен в этом сеансе.

## <a name="viewing-providers"></a>Просмотр поставщиков

Чтобы просмотреть поставщиков PowerShell на компьютере, введите:

```powershell
Get-PSProvider
```

В выходных данных перечислены встроенные поставщики и поставщики, добавленные в сеанс.

## <a name="the-provider-cmdlets"></a>Командлеты поставщика

Следующие командлеты предназначены для работы с данными, предоставляемыми любым поставщиком. Те же командлеты можно использовать так же, как и для управления различными типами данных, предоставляемыми поставщиками. После того как вы научитесь управлять данными одного поставщика, вы можете использовать те же процедуры с данными от любого поставщика.

Например, `New-Item` командлет создает новый элемент. На `C:` диске, поддерживаемом поставщиком **FileSystem** , можно использовать `New-Item` для создания нового файла или папки. На дисках, которые поддерживаются поставщиком **реестра** , можно использовать `New-Item` для создания нового раздела реестра. На `Alias:` диске можно использовать `New-Item` для создания нового псевдонима.

Для получения подробных сведений о любом из следующих командлетов введите:

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a>Командлеты ChildItem

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a>Командлеты содержимого

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Clear-Content](xref:Microsoft.PowerShell.Management.Clear-Content)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a>Командлеты элементов

- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Rename-Item](xref:Microsoft.PowerShell.Management.Rename-Item)
- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a>Командлеты ItemProperty

- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Move-ItemProperty](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Rename-ItemProperty](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a>Командлеты Location

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Pop-Location](xref:Microsoft.PowerShell.Management.Pop-Location)
- [Push-Location](xref:Microsoft.PowerShell.Management.Push-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a>Командлеты пути

- [Join-Path](xref:Microsoft.PowerShell.Management.Join-Path)
- [Convert-Path](xref:Microsoft.PowerShell.Management.Convert-Path)
- [Split-Path](xref:Microsoft.PowerShell.Management.Split-Path)
- [Resolve-Path](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a>Командлеты PSDrive

- [Get-PSDrive](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [New-PSDrive](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [Remove-PSDrive](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a>Командлеты PSProvider

- [Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a>Просмотр данных поставщика

Основное преимущество поставщика заключается в том, что он предоставляет свои данные привычным и согласованным способом. Модель представления данных — это диск файловой системы.

Поставщик позволяет просматривать, перемещать и изменять элементы в хранилище данных, как будто они являются данными в файловой системе. Доступ к хранилищу данных осуществляется по имени диска, который он поддерживает.

Диск отображается в списке по умолчанию для `Get-PSProvider` командлета, но сведения о диске поставщика можно получить с помощью `Get-PSDrive` командлета. Например, чтобы получить все свойства диска Function:, введите:

```powershell
Get-PSDrive Function | Format-List *
```

Данные можно просматривать и перемещать по данным на диске поставщика точно так же, как и на диске файловой системы.

Чтобы просмотреть содержимое диска поставщика, используйте командлеты Get-Item или Get-ChildItem. Введите имя диска, за которым следует двоеточие (:). Например, чтобы просмотреть содержимое диска Alias:, введите:

```powershell
Get-Item alias:
```

Вы можете просматривать данные и управлять ими на любом диске с другого диска, включив имя диска в путь. Например, чтобы просмотреть раздел реестра HKLM\Software на диске HKLM: с другого диска, введите:

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

Чтобы открыть диск, используйте командлет Set-Location. Запомните двоеточие при указании пути к диску. Например, чтобы изменить расположение на корневой каталог диска Cert:, введите:

```powershell
Set-Location cert:
```

Затем, чтобы просмотреть содержимое диска Cert:, введите:

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a>Перемещение по иерархическим данным

Вы можете перемещаться по диску поставщика так же, как и к жесткому диску.
Если данные упорядочены в иерархии элементов внутри элементов, используйте обратную косую черту ( `\` ), чтобы указать дочерний элемент. Используйте следующий формат:

```
drive:\location\child-location\...
```

Например, чтобы изменить расположение на раздел реестра HKLM\Software, введите команду Set-Location, например:

```powershell
Set-Location HKLM:\SOFTWARE\
```

Если любой элемент в полном имени содержит пробелы, имя необходимо заключить в двойные кавычки ( `"` ). В следующем примере показан полный путь, содержащий пробелы.

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

Можно также использовать относительные ссылки на расположения. Точка ( `.` ) представляет текущее расположение. Например, если вы используете раздел `HKLM:\Software\Microsoft` реестра и хотите перечислить подразделы реестра в `HKLM:\Software\Microsoft\PowerShell` разделе, введите следующую команду:

```powershell
Get-ChildItem .\PowerShell
```

Кроме того, двойные точки ( `..` ) ссылаются на каталог или контейнер непосредственно над текущим расположением. Для навигации по иерархии поставщика можно использовать двойные точки ( `..` ).

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a>Домашняя страница поставщика

Поставщики также имеют **домашнюю** папку.  Это расположение является общим для всех, `PSDrives` которое поддерживается поставщиком. Его можно получить, просмотрев свойство **Home** поставщика.

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

Поставщик **FileSystem** является единственным поставщиком, имеющим значение по умолчанию для **Home**. Это то же значение, что и `$Home` . Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).

Можно задать **домашний** каталог для поставщика в текущем сеансе, используя его свойство.

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

`~`Символ может использоваться для представления домашнего каталога поставщика.
Если у поставщика нет установленного **домашней** папки, появится сообщение об ошибке.

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a>Поиск динамических параметров

Динамические параметры — это параметры командлета, которые добавляются в командлет поставщиком. Эти параметры доступны только в том случае, если командлет используется с поставщиком, который их добавил.

Например, `Cert:` диск добавляет параметр **CodeSigningCert** в `Get-Item` `Get-ChildItem` командлеты и. Этот параметр можно использовать только при использовании `Get-Item` или `Get-ChildItem` на `Cert:` диске.

Список динамических параметров, поддерживаемых поставщиком, см. в файле справки для поставщика. Тип:

```
Get-Help <provider-name>
```

Пример:

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a>Изучение поставщиков

Несмотря на то что все данные поставщика отображаются в дисках и для их перемещения используются те же методы, подобный процесс останавливается. Хранилище данных, предоставляемое поставщиком, может быть так же разнообразным, как Active Directory расположений и почтовых ящиков Microsoft Exchange Server.

Для получения сведений об отдельных поставщиках PowerShell введите:

```
Get-Help <ProviderName>
```

Пример:

```powershell
Get-Help registry
```

Чтобы получить список разделов справки о поставщиках, введите:

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a>См. также статью

[about_Locations](about_Locations.md)

[about_Path_Syntax](about_Path_Syntax.md)

