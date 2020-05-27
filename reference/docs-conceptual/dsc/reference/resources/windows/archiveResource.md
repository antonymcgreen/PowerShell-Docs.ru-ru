---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Archive в DSC
ms.openlocfilehash: 679de8b965304c149b10321e73e42b224f49ecc5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560378"
---
# <a name="dsc-archive-resource"></a>Ресурс Archive в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс Archive в DSC Windows PowerShell предоставляет механизм распаковки файлов архивов (ZIP) в указанную папку.

## <a name="syntax"></a>Синтаксис

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Назначение |Указывает, куда будет извлечено содержимое архива. |
|путь |Указывает исходный путь для файла архива. |
|Контрольная сумма |Определяет тип проверки пары файлов на идентичность. Если свойство **Checksum** не задано, для сравнения используется только имя файла или каталога. Допустимые значения: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**. Если свойство **Checksum** указано без свойства **Validate**, возникает ошибка конфигурации. |
|Force |Определенные операции с файлами (например, перезапись файла или удаление непустого каталога) вызывают ошибку. Свойство **Force** позволяет переопределять такие ошибки. Значение по умолчанию равно **False**. |
|Проверить| Проверяет соответствие архива и подписи, используя свойство **Checksum**. Если свойство **Checksum** указано без свойства **Validate**, возникает ошибка конфигурации. Если свойство **Validate** указано без свойства **Checksum**, по умолчанию для **Checksum** используется значение _SHA-256_. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает необходимость проверки того, существует ли содержимое архива в **папке назначения**. Чтобы убедиться, что содержимое существует, укажите для этого свойства значение **Present**. Чтобы убедиться, что содержимого не существует, укажите для этого свойства значение **Absent**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

В следующем примере показано, как использовать ресурс Archive, чтобы убедиться, что содержимое архивного файла с именем `Test.zip` существует и извлекается в указанную папку.

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```
