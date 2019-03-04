---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsOptionalFeature
ms.openlocfilehash: 390caefd2ad190afc651b22ed1beb5cf1d604527
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047668"
---
# <a name="dsc-windowsoptionalfeature-resource"></a>Ресурс DSC WindowsOptionalFeature

> Область применения. Windows PowerShell 5.0

Ресурс **WindowsOptionalFeature** в DSC Windows PowerShell предоставляет механизм включения дополнительных компонентов на целевом узле.

## <a name="syntax"></a>Синтаксис

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Enable | Disable }  ]
    [ Source = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Name| Указывает имя компонента, который необходимо включить или отключить.|
| Ensure| Указывает, включен ли компонент. Чтобы включить компонент, установите для этого свойства значение "Включить", чтобы отключить — значение "Отключить".|
| Источник| Не реализовано.|
| NoWindowsUpdateCheck| Указывает, обращается ли система DISM к Центру обновления Windows при поиске исходных файлов для включения компонента. Если задано значение $true, система DISM не обращается к Центру обновления Windows.|
| RemoveFilesOnDisable| Задайте значение **$true**, чтобы удалить все файлы, связанные с компонентом, при его отключении (то есть когда свойству **Ensure** присваивается значение Absent).|
| Уровень журнала| Максимальный уровень результатов, показываемый в журналах. Допустимыми являются значения: «ErrorsOnly» (записываются только ошибки), «ErrorsAndWarning» (ошибки и предупреждения записываются) и «ErrorsAndWarningAndInformation» (регистрируются ошибки, предупреждения и отладочной информации).|
| LogPath| Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.|
| DependsOn| Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|