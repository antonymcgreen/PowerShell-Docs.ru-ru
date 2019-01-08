---
ms.date: 06/20/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagement DSC
ms.openlocfilehash: 18cbbfe0715c82dcfdf4a5fb6ee36ee814e43d3b
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047716"
---
# <a name="dsc-packagemanagement-resource"></a>Ресурс PackageManagement DSC

Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1

Ресурс **PackageManagement** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов управления пакетами на целевом узле или их удаления. Для этого ресурса требуется модуль **PackageManagement**, доступный из [http://PowerShellGallery.com](http://PowerShellGallery.com).

> [!IMPORTANT]
> Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.

## <a name="syntax"></a>Синтаксис

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [AdditionalParameters = [HashTable]]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [MaximumVersion = [string]]
    [MinimumVersion = [string]]
    [ProviderName = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [RequiredVersion = [string]]
    [Source = [string]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a>Свойства

| Свойство | Описание |
| --- | --- |
| Name| Указывает имя устанавливаемого или удаляемого пакета.|
| AdditionalParameters| Предоставляет определенную хэш-таблицу параметров, которые передаются в аргумент `Get-Package -AdditionalArguments`. Например, для поставщика NuGet можно передать дополнительные параметры, такие как DestinationPath.|
| Ensure| Определяет, следует ли установить или удалить пакет.|
| MaximumVersion|Указывает максимальную версию пакета, которую требуется найти. Если этот параметр не указан, ресурс находит новейшую версию пакета.|
| MinimumVersion|Указывает минимальную версию пакета, которую требуется найти. Если этот параметр не указан, ресурс находит новейшую доступную версию пакета, номер которой не превышает тот, что указан в параметре _MaximumVersion_.|
| ProviderName| Указывает имя поставщика пакетов, на который распространяется область поиска пакетов. Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.|
| RequiredVersion| Указывает точную версию пакета, который вы хотите установить. Если этот параметр не указан, ресурс DSC устанавливает новейшую версию пакета, номер которой не превышает тот, что указан в параметре _MaximumVersion_.|
| Источник| Указывает имя источника пакета, в котором его можно найти. Это может быть универсальный код ресурса (URI) или источник, зарегистрированный с помощью командлета `Register-PackageSource` или ресурса DSC PackageManagementSource.|
| SourceCredential | Указывает учетную запись пользователя с правами для установки пакета для заданного поставщика или источника пакетов.|

## <a name="additional-parameters"></a>Дополнительные параметры

В следующей таблице перечислены параметры свойства AdditionalParameters.

| Параметр | Описание |
| --- | --- |
| DestinationPath| Используется поставщиками, такими как встроенный поставщик NuGet. Указывает расположение файла, в котором вы хотите установить пакет.|
| InstallationPolicy| Используется поставщиками, такими как встроенный поставщик NuGet. Определяет, доверяете ли вы источнику пакета. `Untrusted` или `Trusted`.|

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
        SourceLocation   = "https://www.powershellgallery.com/api/v2/"
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