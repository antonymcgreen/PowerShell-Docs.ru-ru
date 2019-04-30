---
ms.date: 06/20/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagementSource DSC
ms.openlocfilehash: e51b5318288bef458567dd4b58d17caaea3ed69b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077591"
---
# <a name="dsc-packagemanagementsource-resource"></a>Ресурс PackageManagementSource DSC

> Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1

Ресурс **PackageManagementSource** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм регистрации или ее отмены для источников управления пакетами на целевом узле. **Источники управления пакетами, зарегистрированные этим способом, регистрируются в контексте системы, доступной для учетной записи системы или подсистемы DSC.** Для этого ресурса требуется модуль **PackageManagement**, доступный из http://PowerShellGallery.com.

> [!IMPORTANT]
> Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.

## <a name="syntax"></a>Синтаксис

```
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [InstallationPolicy = [string]{ Trusted | Untrusted }]
    [PsDscRunAsCredential = [PSCredential]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a>Свойства

|  Свойство  |  Описание   |
|---|---|
| Name| Указывает имя источника пакета, который будет зарегистрирован в системе или регистрация которого будет отменена.|
| ProviderName| Указывает имя поставщика OneGet, с помощью которого вы можете взаимодействовать с источником пакета.|
| SourceLocation| Указывает URI источника пакета.|
| Ensure| Определяет, будет ли зарегистрирован источник пакета или его регистрация будет отменена.|
| InstallationPolicy| Используется поставщиками, такими как встроенный поставщик NuGet. Определяет, доверяете ли вы источнику пакета. Одно из двух значений: "Untrusted", "Trusted".|
| SourceCredential| Предоставляет доступ к пакету в удаленном источнике.|

## <a name="example"></a>Пример

В этом примере регистрируется источник пакета http://nuget.org с помощью ресурса DSC **PackageManagementSource**.

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }
}
```