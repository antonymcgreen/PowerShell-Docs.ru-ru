---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WindowsPackageCab
ms.openlocfilehash: 1b1b8b6d065882400608d26a991318fec9ad5747
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563950"
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
