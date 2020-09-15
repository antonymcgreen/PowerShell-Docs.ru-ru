---
ms.date: 07/15/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagement DSC
ms.openlocfilehash: 983a288398f710ecc5d2bc557028282ccd58561b
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464270"
---
# <a name="dsc-packagemanagement-resource"></a>Ресурс PackageManagement DSC

Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1

Ресурс **PackageManagement** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов управления пакетами на целевом узле или их удаления. Для этого ресурса требуется модуль **PackageManagement**, доступный из [https://PowerShellGallery.com](https://PowerShellGallery.com).

> [!IMPORTANT]
> Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.

## <a name="syntax"></a>Синтаксис

```Syntax
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ AdditionalParameters = [HashTable] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ MaximumVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ ProviderName = [string] ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ RequiredVersion = [string] ]
    [ Source = [string] ]
    [ SourceCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имя устанавливаемого или удаляемого пакета. |
|AdditionalParameters |Предоставляет определенную хэш-таблицу параметров, которые передаются в аргумент `Get-Package -AdditionalArguments`. Например, для поставщика NuGet можно передать дополнительные параметры, такие как DestinationPath. |
|MaximumVersion |Указывает максимальную версию пакета, которую требуется найти. Если этот параметр не указан, ресурс находит новейшую версию пакета. |
|MinimumVersion |Указывает минимальную версию пакета, которую требуется найти. Если этот параметр не указан, ресурс находит новейшую доступную версию пакета, номер которой не превышает тот, что указан в параметре **MaximumVersion**. |
|ProviderName |Указывает имя поставщика пакетов, на который распространяется область поиска пакетов. Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`. |
|RequiredVersion |Указывает точную версию пакета, который вы хотите установить. Если этот параметр не указан, ресурс DSC устанавливает новейшую версию пакета, номер которой не превышает тот, что указан в параметре **MaximumVersion**. |
|Источник |Указывает имя источника пакета, в котором его можно найти. Это может быть универсальный код ресурса (URI) или источник, зарегистрированный с помощью командлета `Register-PackageSource` или ресурса DSC PackageManagementSource. |
|SourceCredential |Указывает учетную запись пользователя с правами для установки пакета для заданного поставщика или источника пакетов. |

## <a name="additional-parameters"></a>Дополнительные параметры

В следующей таблице перечислены параметры свойства AdditionalParameters.

|Параметр |Описание |
|---|---|
|DestinationPath |Используется поставщиками, такими как встроенный поставщик NuGet. Указывает расположение файла, в котором вы хотите установить пакет. |
|InstallationPolicy |Используется поставщиками, такими как встроенный поставщик NuGet. Определяет, доверяете ли вы источнику пакета. Одно из двух значений: **Untrusted** или **Trusted**. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Определяет, следует ли установить или удалить пакет. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

В этом примере устанавливается пакет NuGet **JQuery** и модуль PowerShell **GistProvider** с помощью ресурса DSC **PackageManagement**. В этом примере сначала обеспечивается доступность нужных источников пакета, а затем определяется ожидаемое состояние пакетов **JQuery** и **GistProvider** (для NuGet и PowerShell).

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceLocation   = "https://www.powershellgallery.com/api/v2"
        InstallationPolicy ="Trusted"
    }

    PackageManagement NugetPackage
    {
        Ensure               = "Present"
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1"
        DependsOn            = "[PackageManagementSource]SourceRepository"
    }

    PackageManagement PSModule
    {
        Ensure               = "Present"
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery"
    }
}
```
