---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsFeatureSet
ms.openlocfilehash: 856c56e0b35a26add729ef77db9dca71fdc0a4d0
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463862"
---
# <a name="dsc-windowsfeatureset-resource"></a>Ресурс DSC WindowsFeatureSet

> Область применения: Windows PowerShell 5.x

Ресурс **WindowsFeatureSet** в DSC Windows PowerShell предоставляет механизм добавления и удаления ролей и компонентов на целевом узле. Он является [составным ресурсом](../../../resources/authoringResourceComposite.md), который вызывает [ресурс WindowsFeature](windowsfeatureResource.md) для каждого компонента, указанного в свойстве **Name**.

Используйте этот ресурс, если нужно настроить одинаковое состояние для нескольких компонентов Windows.

## <a name="syntax"></a>Синтаксис

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
|Имя |Имена ролей или компонентов, которые необходимо добавить или удалить. Это свойство аналогично свойству **Name** командлета [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) и не содержит отображаемые имена ролей или компонентов. |
|Источник |Указывает расположение исходного файла для установки, если он необходим. |
|IncludeAllSubFeature |Присвойте этому свойству значение `$true`, чтобы включить все необходимые дополнительные компоненты для компонентов, указанных в свойстве **Name**. |
|Учетные данные |Учетные данные для добавления или удаления ролей или компонентов. |
|LogPath |Путь к файлу журнала, в котором поставщик ресурсов должен вести журнал работы. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, добавляются ли роли или компоненты. Чтобы гарантировать, что роли или компоненты добавлены, присвойте этому свойству значение **Present**. Чтобы гарантировать, что роли или компоненты удалены, присвойте этому свойству значение **Absent**. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

Приведенная ниже конфигурация обеспечивает установку компонентов **Веб-сервер** (IIS) и **SMTP-сервер**, а также всех их дополнительных компонентов.

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```
