---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс File в DSC
ms.openlocfilehash: 4c6945d4cdcbc64ac6d52db563823efe8fd0247e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954681"
---
# <a name="dsc-file-resource"></a>Ресурс File в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **File** в DSC Windows PowerShell предоставляет механизм управления файлами и папками на целевом узле. Свойства **DestinationPath** и **SourcePath** должны быть доступны для целевого узла.

## <a name="syntax"></a>Синтаксис

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|DestinationPath |Расположение на целевом узле, которое нужно проверить (**Ensure**) на наличие (**Present**) или отсутствие (**Absent**). |
|Атрибуты |Требуемое состояние атрибутов для целевого файла или каталога. Допустимые значения: _Archive_, _Hidden_, _ReadOnly_ и _System_. |
|Контрольная сумма |Тип контрольной суммы для использования при проверке двух файлов на идентичность. Допустимые значения: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**. |
|Содержимое |Допустимо только при использовании с типом **Type** **File**. Указывает содержимое из целевого файла, которое нужно проверить (**Ensure**) на наличие (**Present**) или отсутствие (**Absent**). |
|Учетные данные |Учетные данные, необходимые для доступа к ресурсам, например, к исходным файлам. |
|Force |Переопределяет операции доступа, которые вызывают ошибку (например, перезапись файла или удаление непустого каталога). Значение по умолчанию: `$false`. |
|Recurse |Допустимо только при использовании с типом **Type** **Directory**. Рекурсивно выполняет операции с состоянием во всех подкаталогах. Значение по умолчанию: `$false`. |
|SourcePath |Путь, откуда нужно скопировать ресурс файла или папки. |
|Type |Тип настраиваемого ресурса. Допустимые значения: **Directory** и **File**. Значение по умолчанию — **File**. |
|MatchSource |Определяет, должен ли ресурс отслеживать новые файлы, добавленные в исходный каталог после исходной копии. Значение `$true` указывает, что после исходной копии все новые исходные файлы должны быть скопированы в место назначения. Если задано значение `$false`, ресурс кэширует содержимое исходного каталога и игнорирует любые файлы, добавленные после исходной копии. Значение по умолчанию: `$false`. |

> [!WARNING]
> Если не указать значение для свойства **Credential** или **PSRunAsCredential**, ресурс будет использовать учетную запись компьютера целевого узла для доступа к свойству **SourcePath**. Если **SourcePath** представляет собой общий ресурс UNC, это может привести к ошибке отказа в доступе. Убедитесь, что разрешения установлены соответственно, или используйте свойства **Credential** или **PSRunAsCredential**, чтобы указать учетную запись, которая должна использоваться.

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Определяет, должны ли существовать файл и **Contents** в **Destination**. Чтобы гарантировать, что файл существует, укажите для этого свойства значение **Present**. Чтобы убедиться, что содержимого не существует, укажите для этого свойства значение **Absent**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

### <a name="additional-information"></a>Дополнительные сведения

- При указании только свойства **DestinationPath** ресурс проверяет, что путь существует (**Present**) или не существует (**Absent**).
- При указании свойств **SourcePath** и **DestinationPath**, для которых свойство **Type** имеет значение **Directory**, ресурс копирует исходный каталог в путь назначения. Свойства **Recurse**, **Force** и **MatchSource** изменяют тип выполняемой операции копирования, а свойство **Credential** определяет, какую учетную запись следует использовать для доступа к исходному каталогу.
- Если вы указали значение **ReadOnly** для свойства **Attributes** вместе с **DestinationPath**, **Ensure** и **Present** будут создавать указанный путь, а **Contents** задает содержимое файла. Задание **Ensure** **Absent** приведет к пропуску свойства **Attributes** полностью и удалит любой файл по указанному пути.

## <a name="example"></a>Пример

В следующем примере копируется каталог и его подкаталоги с опрашиваемого сервера на целевой узел, использующий ресурс File. Если операция прошла успешно, ресурс Log записывает в журнал событий сообщение с подтверждением.

Исходный каталог — это UNC-путь (`\\PullServer\DemoSource`), к которому предоставлен общий доступ с опрашиваемого сервера. Свойство **Recurse** гарантирует, что также копируются все подкаталоги.

> [!IMPORTANT]
> LCM на целевом узле выполняется в контексте локальной системной учетной записи по умолчанию. Чтобы предоставить доступ к свойству **SourcePath**, задайте соответствующие разрешения для учетной записи компьютера целевого узла. Свойства **Credential** и **PSDSCRunAsCredential** изменяют контекст, который LCM использует для доступа к свойству **SourcePath**. Вам по-прежнему необходимо предоставить доступ к учетной записи, которая будет использоваться для доступа к свойству **SourcePath**.

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