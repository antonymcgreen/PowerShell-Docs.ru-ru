---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC ProcessSet
ms.openlocfilehash: d18d2c96239abd83cea735e0fbce198d0456cea6
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093996"
---
# <a name="dsc-windowsprocess-resource"></a>Ресурс WindowsProcess в DSC

> Область применения: Windows PowerShell 5.0

Ресурс **ProcessSet** в DSC Windows PowerShell предоставляет механизм настройки процессов на целевом узле. Он является [составным ресурсом](authoringResourceComposite.md), который вызывает [ресурс WindowsProcess](windowsProcessResource.md) для каждой группы, указанной в параметре `GroupName`.

## <a name="syntax"></a>Синтаксис

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Аргументы| Строка, содержащая аргументы, которые будут переданы процессу "как есть". Если необходимо передать несколько аргументов, поместите их все в эту строку.|
| путь| Пути к исполняемым файлам процессов. Если это имена исполняемых файлов (а не полные пути к ним), ресурс DSC будет искать переменную среды **Path** (`$env:Path`), чтобы найти файлы. Если значения этого свойства — полные пути, ресурс DSC не будет использовать переменную среды **Path** для поиска файлов и вызовет ошибку в случае отсутствия путей. Относительные пути не допускаются.|
| Учетные данные| Указывает учетные данные для запуска процесса.|
| Ensure| Указывает, существуют ли процессы. Если процесс существует, укажите для этого свойства значение Present. В противном случае укажите значение Absent. Значение по умолчанию — Present.|
| StandardErrorPath| Путь, по которому процессы записывают стандартную ошибку. Все существующие файлы в этом каталоге будут перезаписаны.|
| StandardInputPath| Поток, из которого процесс получает стандартные входные данные.|
| StandardOutputPath| Путь, по которому процессы записывают стандартные выходные данные. Все существующие файлы в этом каталоге будут перезаписаны.|
| WorkingDirectory| Расположение, которое используется в качестве текущего рабочего каталога для процессов.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока скрипта для конфигурации ресурса — **ResourceName**, а его тип — **_ResourceType**, то синтаксис использования этого свойства таков: "DependsOn = "[ResourceType]ResourceName"".|