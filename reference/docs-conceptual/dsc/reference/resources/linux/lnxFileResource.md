---
ms.date: 07/17/2020
ms.topic: reference
title: Ресурс nxFile в DSC для Linux
description: Ресурс nxFile в DSC для Linux
ms.openlocfilehash: 14a8174a92f1bbde9b1f16cf814ef7c83309c737
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389034"
---
# <a name="dsc-for-linux-nxfile-resource"></a>Ресурс nxFile в DSC для Linux

Ресурс **nxFile** в настройке требуемого состояния PowerShell предоставляет механизм управления файлами и каталогами на узле Linux.

## <a name="syntax"></a>Синтаксис

```Syntax
nxFile <string> #ResourceName
{
    DestinationPath = <string>
    [ SourcePath = <string> ]
    [ Type = <string> { directory | file | link } ]
    [ Contents = <string> ]
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Recurse = <bool> ]
    [ Force = <bool> ]
    [ Links = <string> { follow | manage | ignore } ]
    [ Group = <string> ]
    [ Mode = <string> ]
    [ Owner = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|DestinationPath |Указывает, в каком расположении нужно проверить состояние файла или каталога. |
|SourcePath |Указывает, откуда нужно скопировать файл или папку. Этот может быть локальный путь или URL-адрес `http/https/ftp`. Удаленные URL-адреса `http/https/ftp` поддерживаются, только если для свойства **Type** выбрано значение **file**. |
|Тип |Указывает, является ли настраиваемый ресурс каталогом или файлом. Если выбрано значение **directory**, то ресурс является каталогом, а если значение **file** — файлом. Значение по умолчанию — **file**. |
|Содержимое |Указывает содержимое файла, например определенную строку. |
|Контрольная сумма |Определяет тип проверки пары файлов на идентичность. Если свойство **Checksum** не задано, для сравнения используется только имя файла или каталога. Значения: **ctime**, **mtime** или **md5**. |
|Recurse |Указывает, используются ли вложенные папки. Если свойство имеет значение `$true`, вложенные папки включаются. Значение по умолчанию — `$false`. Это свойство можно использовать только в том случае, если свойство **Type** имеет значение **directory**. |
|Force |Определенные операции с файлами (например, перезапись файла или удаление непустого каталога) вызывают ошибку. Свойство **Force** позволяет переопределять такие ошибки. Значение по умолчанию — `$false`. |
|Ссылки |Определяет желаемое поведение символических ссылок. Если для свойства установлено значение **follow**, символические ссылки отслеживаются, а к целевым объектам применяются действия (например, копирование файла вместо ссылки). Если установлено значение **manage**, действие применяется к ссылке (например, копирование самой ссылки). Если установлено значение **ignore**, символические ссылки игнорируются. |
|Группа |Имя ресурса **Group** — обладателя разрешений для файла или каталога. |
|Режим |Указывает нужные разрешения для ресурса в восьмеричной или символьной нотации (например, **777** или **rwxrwxrwx**). Если используется символьная нотация, не указывайте первый символ, обозначающий каталог или файл. |
|Владелец |Имя группы — владельца файла или каталога. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Определяет, нужно ли проверять существование файла. Чтобы гарантировать, что файл существует, укажите для этого свойства значение **Present**. Чтобы гарантировать, что файл не существует, укажите для этого свойства значение **Absent**. Значение по умолчанию — **Present**. |

## <a name="additional-information"></a>Дополнительные сведения

Linux и Windows используют разные символы разрыва строки в текстовых файлах по умолчанию, что может привести к непредвиденным результатам при настройке некоторых файлов на компьютере Linux с помощью **nxFile**. Избежать проблем из-за непредвиденных символов разрыва строки при работе с содержанием файла Linux можно разными способами:

1. Копирование файла из удаленного источника (HTTP, HTTPS или FTP)

   Создайте файл с нужным содержанием на компьютере с Linux и поместите его на веб- или FTP-сервер, доступный для настраиваемого узла. Определите свойство **SourcePath** в ресурсе **nxFile**, указав URL-адрес файла на веб- или FTP-сервере.

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      nxFile resolvConf
      {
         SourcePath = "http://10.185.85.11/conf/resolv.conf"
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
      }
   }
   ```

1. Прочтите содержимое файла в сценарии PowerShell с помощью командлета [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content), настроив символ переноса строки Linux с помощью свойства **$OFS**.

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      $OFS = "`n"
      $Contents = Get-Content C:\temp\resolv.conf

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = "$Contents"
      }
   }
   ```

1. Воспользуйтесь функцией PowerShell для замены символов разрыва строки в Windows на символы разрыва строки в Linux.

   ```powershell
   Function LinuxString($inputStr){
      $outputStr = $inputStr.Replace("`r`n","`n")
      $outputStr += "`n"
      Return $outputStr
   }

   Import-DSCResource -Module nx

   Node $Node
   {
      $Contents = @'
   search contoso.com
   domain contoso.com
   nameserver 10.185.85.11
   '@
       $Contents = LinuxString $Contents

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = $Contents
      }
   }
   ```

## <a name="example"></a>Пример

В следующем примере проверяется существование каталога `/opt/mydir` и файла с указанным содержимым в этом каталоге.

```powershell
Import-DSCResource -Module nx

Node $node {
    nxFile DirectoryExample
    {
        Ensure = "Present"
        DestinationPath = "/opt/mydir"
        Type = "Directory"
    }

    nxFile FileExample
    {
        Ensure = "Present"
        Destinationpath = "/opt/mydir/myfile"
        Contents=@"
#!/bin/bash`necho "hello world"`n
"@
        Mode = "755"
        DependsOn = "[nxFile]DirectoryExample"
    }
}
```
