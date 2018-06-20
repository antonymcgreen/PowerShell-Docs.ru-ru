---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс WindowsFeature в DSC
ms.openlocfilehash: ece77043d3a4131150b934a19ee8b92dd75c48f0
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34188315"
---
# <a name="dsc-windowsfeature-resource"></a>Ресурс WindowsFeature в DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурс **WindowsFeature** в DSC Windows PowerShell предоставляет механизм добавления и удаления ролей и компонентов на целевом узле.

## <a name="syntax"></a>Синтаксис

```
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Source = [string] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Name| Указывает имя роли или компонента, которые необходимо добавить или удалить. Это свойство аналогично свойству __Name__ командлета [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) и не является отображаемым именем роли или компонента.|
| Учетные данные| Указывает учетные данные для добавления или удаления роли или компонента.|
| Ensure| Указывает, добавляется или удаляется роль или компонент. Чтобы добавить роль или компонент, установите это свойство равным Present, чтобы удалить — равным Absent.|
| IncludeAllSubFeature| Присвойте этому свойству значение __$true__ для синхронизации состояния всех необходимых дополнительных компонентов с состоянием компонента, указанного в свойстве __Name__.|
| LogPath| Указывает путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы.|
| DependsOn| Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.|
| Источник| Указывает расположение исходного файла для установки, если он необходим.|

## <a name="example"></a>Пример
```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```