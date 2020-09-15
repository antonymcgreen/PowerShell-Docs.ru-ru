---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс WindowsProcess в DSC
ms.openlocfilehash: a1f8840a5894049efd27c5d213a66363cd8dbebc
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464134"
---
# <a name="dsc-windowsprocess-resource"></a>Ресурс WindowsProcess в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **WindowsProcess** в DSC Windows PowerShell предоставляет механизм настройки процессов на целевом узле.

## <a name="syntax"></a>Синтаксис

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Description |
|---|---|
|Аргументы |Указывает строку аргументов, которая будет передана процессу "как есть". Если необходимо передать несколько аргументов, поместите их все в эту строку. |
|путь |Путь к исполняемому файлу процесса. Если это имя исполняемого файла (а не полный путь к нему), ресурс DSC будет искать переменную среды `$env:Path`, чтобы найти исполняемый файл. Если значение этого свойства — полный путь, ресурс DSC не будет использовать переменную среды `$env:Path` для поиска файла и вызовет ошибку в случае отсутствия пути. Относительные пути не допускаются. |
|Учетные данные |Указывает учетные данные для запуска процесса. |
|StandardErrorPath |Указывает путь к каталогу для записи стандартных ошибок. Все существующие файлы в этом каталоге будут перезаписаны. |
|StandardInputPath |Указывает расположение стандартного ввода. |
|StandardOutputPath |Указывает расположение стандартного вывода. Все существующие файлы в этом каталоге будут перезаписаны. |
|WorkingDirectory |Указывает расположение, которое будет использоваться в качестве текущего рабочего каталога для процесса. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Description |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, существует ли процесс. Чтобы гарантировать, что процесс существует, укажите для этого свойства значение **Present**. В противном случае укажите значение **Absent**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |
