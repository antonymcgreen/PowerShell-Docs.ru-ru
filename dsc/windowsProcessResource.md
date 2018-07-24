---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс WindowsProcess в DSC
ms.openlocfilehash: 3c4e6d8377c3dcbf4f1db87a603d5483b8caafb8
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093741"
---
# <a name="dsc-windowsprocess-resource"></a>Ресурс WindowsProcess в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс **WindowsProcess** в DSC Windows PowerShell предоставляет механизм настройки процессов на целевом узле.

## <a name="syntax"></a>Синтаксис

```
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ DependsOn = [string[]] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Аргументы| Указывает строку аргументов, которая будет передана процессу "как есть". Если необходимо передать несколько аргументов, поместите их все в эту строку.|
| путь| Путь к исполняемому файлу процесса. Если это имя исполняемого файла (а не полный путь к нему), ресурс DSC будет искать переменную среды **Path** (`$env:Path`), чтобы найти исполняемый файл. Если значение этого свойства — полный путь, ресурс DSC не будет использовать переменную среды **Path** для поиска файла и вызовет ошибку в случае отсутствия пути. Относительные пути не допускаются.|
| Учетные данные| Указывает учетные данные для запуска процесса.|
| Ensure| Указывает, существует ли процесс. Если процесс существует, укажите для этого свойства значение Present. В противном случае укажите значение Absent. Значение по умолчанию — Present.|
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: 'DependsOn = "[ResourceType]ResourceName"''.|
| StandardErrorPath| Указывает путь к каталогу для записи стандартных ошибок. Все существующие файлы в этом каталоге будут перезаписаны.|
| StandardInputPath| Указывает расположение стандартного ввода.|
| StandardOutputPath| Указывает расположение стандартного вывода. Все существующие файлы в этом каталоге будут перезаписаны.|
| WorkingDirectory| Указывает расположение, которое будет использоваться в качестве текущего рабочего каталога для процесса.|