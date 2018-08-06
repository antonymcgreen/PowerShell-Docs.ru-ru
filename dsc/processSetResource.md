---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC ProcessSet
ms.openlocfilehash: 33000786a9e17e11168b5e08c3bcfcacf3af2611
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268023"
---
# <a name="dsc-windowsprocess-resource"></a>Ресурс WindowsProcess в DSC

_Область применения: Windows PowerShell 5.0_

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

| Свойство | Описание |
| --- | --- |
| Аргументы| Строка, содержащая аргументы, которые будут переданы процессу "как есть". Если необходимо передать несколько аргументов, поместите их все в эту строку.|
| путь| Пути к исполняемым файлам процессов. Если это имена исполняемых файлов (а не полные пути к ним), ресурс DSC будет искать переменную среды **Path** (`$env:Path`), чтобы найти файлы. Если значения этого свойства — полные пути, ресурс DSC не будет использовать переменную среды **Path** для поиска файлов и вызовет ошибку в случае отсутствия путей. Относительные пути не допускаются.|
| Учетные данные| Указывает учетные данные для запуска процесса.|
| Ensure| Указывает, существуют ли процессы. Если процесс существует, укажите для этого свойства значение Present. В противном случае укажите значение Absent. Значение по умолчанию — Present.|
| StandardErrorPath| Путь, по которому процессы записывают стандартную ошибку. Все существующие файлы в этом каталоге будут перезаписаны.|
| StandardInputPath| Поток, из которого процесс получает стандартные входные данные.|
| StandardOutputPath| Путь, по которому процессы записывают стандартные выходные данные. Все существующие файлы в этом каталоге будут перезаписаны.|
| WorkingDirectory| Расположение, которое используется в качестве текущего рабочего каталога для процессов.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока скрипта для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, синтаксис использования этого свойства будет таким: `DependsOn = "[ResourceType]ResourceName"`.|