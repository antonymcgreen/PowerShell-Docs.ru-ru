---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс File в DSC
ms.openlocfilehash: b5bc2c305b8cfccbd044274811df631264a24279
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077336"
---
# <a name="dsc-file-resource"></a>Ресурс File в DSC

> Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс File в DSC Windows PowerShell предоставляет механизм управления файлами и папками на целевом узле. Свойства **DestinationPath** и **SourcePath** должны быть доступны для целевого узла.

## <a name="syntax"></a>Синтаксис

```
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ DependsOn = [string[]] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
}
```

## <a name="properties"></a>Свойства

|Свойство       |Описание                                                                   |Обязательный|Значение по умолчанию|
|---------------|------------------------------------------------------------------------------|--------|-------|
|DestinationPath|Расположение на целевом узле, которое нужно проверить на наличие (`Present`) или отсутствие (`Absent`).|Да|Нет|
|Атрибуты     |Требуемое состояние атрибутов для целевого файла или каталога. Допустимые значения: **Archive**, **Hidden**, **ReadOnly** и **System**.|Нет|Нет|
|Контрольная сумма      |Тип контрольной суммы для использования при проверке двух файлов на идентичность. Допустимые значения: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.|Нет|Сравнивается только имя файла или каталога.|
|Содержимое       |Допустимо только при использовании с типом `File`. Указывает содержимое из целевого файла, которое нужно проверить на наличие (`Present`) или отсутствие (`Absent`). |Нет|Нет|
|Учетные данные     |Учетные данные, необходимые для доступа к ресурсам, например, к исходным файлам.|Нет|Учетная запись компьютера целевого узла. (*см. Примечание*)|
|Ensure         |Требуемое состояние целевого файла или каталога. |Нет|**Присутствует**|
|Force          |Переопределяет операции доступа, которые вызывают ошибку (например, перезапись файла или удаление непустого каталога).|Нет|`$false`|
|Recurse        |Допустимо только при использовании с типом `Directory`. Рекурсивно выполняет операции с состоянием во всех подкаталогах.|Нет|`$false`|
|DependsOn      |Задает зависимость для указанных ресурсов. Этот ресурс будет выполняться только после успешного выполнения всех зависимых ресурсов. Вы можете указать зависимые ресурсы, используя синтаксис `"[ResourceType]ResourceName"`. Сведения см. в разделе [Использование зависимостей ресурсов с DependsOn](../../../configurations/resource-depends-on.md).|Нет|Нет|
|SourcePath     |Путь, откуда нужно скопировать ресурс файла или папки.|Нет|Нет|
|Type           |Тип настраиваемого ресурса. Допустимые значения: `Directory` и `File`.|Нет|`File`|
|MatchSource    |Определяет, должен ли ресурс отслеживать новые файлы, добавленные в исходный каталог после исходной копии. Значение `$true` указывает, что после исходной копии все новые исходные файлы должны быть скопированы в место назначения. Если задано значение `$False`, ресурс кэширует содержимое исходного каталога и игнорирует любые файлы, добавленные после исходной копии.|Нет|`$false`|

> [!WARNING]
> Если не указать значение для свойства `Credential` или `PSRunAsCredential` (PS версии 5), ресурс будет использовать учетную запись компьютера целевого узла для доступа к свойству `SourcePath`.  Если `SourcePath` представляет собой общий ресурс UNC, это может привести к ошибке отказа в доступе. Убедитесь, что разрешения установлены соответственно, или используйте свойства `Credential` или `PSRunAsCredential`, чтобы указать учетную запись, которая должна использоваться.

## <a name="present-vs-absent"></a>Сравнение значений Present и Absent

Каждый ресурс DSC выполняет различные операции на основе значения, указываемого для свойства `Ensure`. Значения, указываемые для приведенных выше свойств, определяют выполняемую операцию с состоянием.

### <a name="existence"></a>Существование

При указании только свойства `DestinationPath` ресурс проверяет, что путь существует (`Present`) или не существует (`Absent`).

### <a name="copy-operations"></a>Операции копирования

При указании свойств `SourcePath` и `DestinationPath`, для которых свойство `Type` имеет значение **Directory**, ресурс копирует исходный каталог в путь назначения. Свойства `Recurse`, `Force` и `MatchSource` изменяют тип выполняемой операции копирования, а свойство `Credential` определяет, какую учетную запись следует использовать для доступа к исходному каталогу.

### <a name="limitations"></a>Ограничения

Если указано значение `ReadOnly` для свойства `Attributes` вместе со свойством `DestinationPath`, `Ensure = "Present"` создаст указанный путь, а свойство `Contents` задаст содержимое файла.  Операция с состоянием `Absent` приведет к пропуску свойства `Attributes` полностью и удалит любой файл по указанному пути.

## <a name="example"></a>Пример

В следующем примере копируется каталог и его подкаталоги с опрашиваемого сервера на целевой узел, использующий ресурс File. Если операция прошла успешно, ресурс Log записывает в журнал событий сообщение с подтверждением.

Исходный каталог — это UNC-путь (`\\PullServer\DemoSource`), к которому предоставлен общий доступ с опрашиваемого сервера. Свойство `Recurse` гарантирует, что также копируются все подкаталоги.

> [!IMPORTANT]
> LCM на целевом узле выполняется в контексте локальной системной учетной записи по умолчанию. Чтобы предоставить доступ к свойству **SourcePath**, задайте соответствующие разрешения для учетной записи компьютера целевого узла. Свойства **Credential** и **PSDSCRunAsCredential** (версия 5) изменяют контекст, который LCM использует для доступа к свойству **SourcePath**. Вам по-прежнему необходимо предоставить доступ к учетной записи, которая будет использоваться для доступа к свойству **SourcePath**.

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

Дополнительные сведения об использовании свойства **Credentials** в DSC см. в разделе [Use Credentials with DSC Resources](../../../configurations/runAsUser.md) (Использование учетных данных с ресурсами DSC) или [Credentials Options in Configuration Data](../../../configurations/configDataCredentials.md) (Параметры учетных данных в данных конфигурации).
