---
ms.date: 07/15/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagementSource DSC
ms.openlocfilehash: b24558574f192347aace5a809d57385e01d9acb3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463896"
---
# <a name="dsc-packagemanagementsource-resource"></a>Ресурс PackageManagementSource DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x

Ресурс **PackageManagementSource** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм регистрации или ее отмены для источников управления пакетами на целевом узле.
**Источники управления пакетами, зарегистрированные этим способом, регистрируются в контексте системы, доступной для учетной записи системы или подсистемы DSC.** Для этого ресурса требуется модуль **PackageManagement** из [Коллекции PowerShell](https://PowerShellGallery.com).

> [!IMPORTANT]
> Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.

## <a name="syntax"></a>Синтаксис

```Syntax
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [ InstallationPolicy = [string]{ Trusted | Untrusted } ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Свойства

|Свойство |Описание |
|---|---|
|Имя |Указывает имя источника пакета, который будет зарегистрирован в системе или регистрация которого будет отменена. |
|ProviderName |Указывает имя поставщика OneGet, с помощью которого вы можете взаимодействовать с источником пакета. |
|SourceLocation |Указывает URI источника пакета. |
|InstallationPolicy |Используется поставщиками, такими как встроенный поставщик NuGet. Определяет, доверяете ли вы источнику пакета. Одно из двух значений: **Untrusted** или **Trusted**. |
|SourceCredential |Предоставляет доступ к пакету в удаленном источнике. |

## <a name="common-properties"></a>Общие свойства

|Свойство |Описание |
|---|---|
|DependsOn |Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Определяет, будет ли зарегистрирован источник пакета или его регистрация будет отменена. Значение по умолчанию — **Present**. |
|PsDscRunAsCredential |Задает учетные данные для выполнения всего ресурса от другого имени. |

> [!NOTE]
> В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных. Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Пример

В этом примере регистрируется источник пакета `https://nuget.org` с помощью ресурса DSC **PackageManagementSource**.

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "https://api.nuget.org/api/v3/"
        InstallationPolicy ="Trusted"
    }
}
```
