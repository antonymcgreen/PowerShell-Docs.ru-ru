---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxArchive в DSC для Linux
ms.openlocfilehash: 77b52ad68344ba791501baeb585a5001cc97a126
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953331"
---
# <a name="dsc-for-linux-nxarchive-resource"></a>Ресурс nxArchive в DSC для Linux

Ресурс **nxArchive** в DSC PowerShell предоставляет механизм распаковки файлов архивов (TAR, ZIP) в указанную папку на узле с Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
nxArchive <string> #ResourceName
{
    SourcePath = <string>
    DestinationPath = <string>
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Force = <bool> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|SourcePath |Указывает исходный путь для файла архива. Это должен быть файл в формате TAR, ZIP или TAR.GZ. |
|DestinationPath |Указывает, куда будет извлечено содержимое архива. |
|Контрольная сумма |Указывает тип для использования при определении факта обновления исходного архива. Значения: **ctime**, **mtime** или **md5**. Значение по умолчанию — **md5**. |
|Force |Определенные операции с файлами (например, перезапись файла или удаление непустого каталога) вызывают ошибку. Свойство **Force** позволяет переопределять такие ошибки. Значение по умолчанию: `$false`. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает необходимость проверки того, существует ли содержимое архива в **папке назначения**. Чтобы убедиться, что содержимое существует, укажите для этого свойства значение **Present**. Чтобы убедиться, что содержимого не существует, укажите для этого свойства значение **Absent**. Значение по умолчанию — **Present**. |

## <a name="example"></a>Пример

В следующем примере показано, как использовать ресурс **nxArchive**, чтобы убедиться, что содержимое архивного файла с именем `website.tar` существует и извлекается в указанную папку.

```powershell
Import-DSCResource -Module nx

nxFile SyncArchiveFromWeb
{
   Ensure = "Present"
   SourcePath = "http://release.contoso.com/releases/website.tar"
   DestinationPath = "/usr/release/staging/website.tar"
   Type = "File"
   Checksum = "mtime"
}

nxArchive SyncWebDir
{
   SourcePath = "/usr/release/staging/website.tar"
   DestinationPath = "/usr/local/apache2/htdocs/"
   Force = $false
   DependsOn = "[nxFile]SyncArchiveFromWeb"
}
```