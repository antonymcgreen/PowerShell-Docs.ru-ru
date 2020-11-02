---
ms.date: 07/16/2020
ms.topic: reference
title: Ресурс DSC ProcessSet
description: Ресурс DSC ProcessSet
ms.openlocfilehash: 3e09c8c7b4ca7d8e95b36f9d4c20c2a85abad9dd
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142571"
---
# <a name="dsc-processset-resource"></a>Ресурс DSC ProcessSet

> Область применения: Windows PowerShell 5.x

Ресурс **ProcessSet** в DSC Windows PowerShell предоставляет механизм настройки процессов на целевом узле.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Синтаксис

```Syntax
ProcessSet [string] #ResourceName
{
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|путь |Путь к исполняемому файлу процесса. Если это имена исполняемых файлов (а не полные пути к ним), ресурс DSC будет искать переменную среды `$env:Path`, чтобы найти файлы. Если значения этого свойства — полные пути, ресурс DSC не будет использовать переменную среды `$env:Path` для поиска файлов и вызовет ошибку в случае отсутствия путей. Относительные пути не допускаются. |
|Учетные данные |Указывает учетные данные для запуска процесса. |
|StandardErrorPath |Путь, по которому процессы записывают стандартную ошибку. Все существующие файлы в этом каталоге будут перезаписаны. |
|StandardInputPath |Поток, из которого процесс получает стандартные входные данные. |
|StandardOutputPath |Путь, по которому процессы записывают стандартные выходные данные. Все существующие файлы в этом каталоге будут перезаписаны. |
|WorkingDirectory |Расположение, которое используется в качестве текущего рабочего каталога для процессов. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существуют ли процессы. Чтобы гарантировать, что процесс существует, укажите для этого свойства значение **Present** . В противном случае укажите значение **Absent** . Значение по умолчанию — **Present** . |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).
