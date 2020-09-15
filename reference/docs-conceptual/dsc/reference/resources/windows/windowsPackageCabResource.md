---
ms.date: 07/16/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsPackageCab
ms.openlocfilehash: 7205a454d100bb369fd6cf0c5ac419585c8bbe86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464151"
---
# <a name="dsc-windowspackagecab-resource"></a>Ресурс DSC WindowsPackageCab

> Область применения: Windows PowerShell 5.1

Ресурс **WindowsPackageCab** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов CAB-файлов Windows на целевом узле или их удаления.

На целевом узле должен быть установлен модуль DISM PowerShell. Дополнительные сведения см. в статье [Use DISM in Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14) (Использование DISM в Windows PowerShell)

## <a name="syntax"></a>Синтаксис

```Syntax
{
    Name = [string]
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    Ensure = [string] { Absent | Present }
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имя пакета, для которого требуется обеспечить определенное состояние. |
|SourcePath |Указывает путь к файлу пакета. |
|LogPath |Указывает полный путь к папке, где нужно сохранить файл журнала для установки или удаления пакета. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Указывает, установлен ли пакет. Если это свойство имеет значение **Absent**, пакет не устанавливается (а если он уже установлен, то удаляется). Если это свойство имеет значение **Present**, пакет устанавливается. Свойство **Ensure** является обязательным для ресурса **WindowsPackageCab**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

## <a name="example"></a>Пример

Ниже приведен пример конфигурации, которая принимает входные параметры и гарантирует, что CAB-файл, указанный в параметре `$Name`, установлен.

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```
