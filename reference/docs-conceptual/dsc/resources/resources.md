---
ms.date: 07/23/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
ms.openlocfilehash: 6ab831c9d423c6189951b43bfab92f800366ceca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87777925"
---
# <a name="dsc-resources"></a>Ресурсы DSC

> Относится к Windows PowerShell 4.0 и более поздним версиям.

## <a name="overview"></a>Обзор

Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC. В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).

Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS. Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.

Каждый ресурс содержит *схему, которая определяет синтаксис, используемый ресурсом при [конфигурации](../configurations/configurations.md).
Схема ресурса может быть определена следующими способами.

- Файл `Schema.Mof`. Большинство ресурсов определяет свою _схему_ в файле `schema.mof` с помощью [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).
- Файл `<Resource Name>.schema.psm1`. [Составные ресурсы](../configurations/compositeConfigs.md) определяют свою _схему_ в файле `<ResourceName>.schema.psm1` с помощью [блока параметров](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).
- Файл `<Resource Name>.psm1`. Ресурсы DSC, основанные на классе, определяют свою _схему_ в описании класса. Элементы синтаксиса обозначаются как свойства класса. Дополнительные сведения см. в статье [About Classes and Desired State Configuration](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc) (О классах и настройке требуемого состояния).

Чтобы получить синтаксис из ресурса DSC, используйте командлет [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) с параметром **Syntax**. Это похоже на использование командлета [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с параметром **Syntax** для получения синтаксиса командлета. В выходных данных будет показан шаблон, используемый в указанном блоке ресурса.

```powershell
Get-DscResource -Syntax Service
```

Выходные данные должны соответствовать выходным данным, приведенным ниже, так как в будущем этот ресурс может измениться. Например, синтаксис командлета, для которого _ключи_ в квадратных скобках являются необязательными. Типы указывают типы данных для каждого ключа в списке ожидания.

> [!NOTE]
> Ключ **Ensure** является необязательным, так как Present является его значением по умолчанию.

```output
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

> [!NOTE]
> В версиях PowerShell до 7.0 `Get-DscResource` не находит ресурсы DSC на основе класса.

Блок ресурсов **Служба** внутри конфигурации может выглядеть следующим образом. Это необходимо, чтобы **убедиться**, что служба подсистемы печати работает.

> [!NOTE]
> Перед использованием ресурса в конфигурации его необходимо импортировать с помощью командлета [Import-DSCResource](../configurations/import-dscresource.md).

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

Конфигурации могут содержать несколько экземпляров одного типа ресурса. Имя каждого экземпляра должно быть уникально. В следующем примере второй блок ресурсов **Служба** добавляется для настройки службы DHCP.

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> Начиная с PowerShell 5.0, технология IntelliSense включена в DSC. Новая функция позволяет использовать клавиши <kbd>TAB</kbd> и <kbd>CTRL</kbd>+<kbd>ПРОБЕЛ</kbd> для автозаполнения имен ключей.

![Технология IntelliSense с использованием заполнения нажатием клавиши TAB](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a>Типы ресурсов

В Windows имеются встроенные ресурсы. Кроме того, существуют ресурсы для ОС Linux. Имеются ресурсы для [межузловых зависимостей](../configurations/crossNodeDependencies.md), ресурсы для управления пакетами, а также [ресурсы, принадлежащие сообществу и поддерживаемые им](https://github.com/dsccommunity). Шаги, описанные выше, можно использовать для определения синтаксиса этих ресурсов и способов их использования. Страницы, на которых было описано использование этих ресурсов, собраны в разделе **Справочные материалы**.

### <a name="windows-built-in-resources"></a>Встроенные ресурсы Windows

- [Ресурс Archive](../reference/resources/windows/archiveResource.md)
- [Ресурс Environment](../reference/resources/windows/environmentResource.md)
- [Ресурс File](../reference/resources/windows/fileResource.md)
- [Ресурс Group](../reference/resources/windows/groupResource.md)
- [Ресурс GroupSet](../reference/resources/windows/groupSetResource.md)
- [Ресурс Log](../reference/resources/windows/logResource.md)
- [Ресурс Package](../reference/resources/windows/packageResource.md)
- [Ресурс ProcessSet](../reference/resources/windows/ProcessSetResource.md)
- [Ресурс Registry](../reference/resources/windows/registryResource.md)
- [Ресурс Script](../reference/resources/windows/scriptResource.md)
- [Ресурс Service](../reference/resources/windows/serviceResource.md)
- [Ресурс ServiceSet](../reference/resources/windows/serviceSetResource.md)
- [Ресурс User](../reference/resources/windows/userResource.md)
- [Ресурс WindowsFeature](../reference/resources/windows/windowsFeatureResource.md)
- [Ресурс WindowsFeatureSet](../reference/resources/windows/windowsFeatureSetResource.md)
- [Ресурс WindowsOptionalFeature](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [Ресурс WindowsOptionalFeatureSet](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [Ресурс WindowsPackageCabResource](../reference/resources/windows/windowsPackageCabResource.md)
- [Ресурс WindowsProcess](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a>Ресурсы межузловых зависимостей

- [Ресурс WaitForAll](../reference/resources/windows/waitForAllResource.md)
- [Ресурс WaitForSome](../reference/resources/windows/waitForSomeResource.md)
- [Ресурс WaitForAny](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a>Ресурсы управления пакетами

- [Ресурс PackageManagement](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [Ресурс PackageManagementSource](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a>Ресурсы Linux

- [Ресурс Linux Archive](../reference/resources/linux/lnxArchiveResource.md)
- Ресурс [Linux Environment](../reference/resources/linux/lnxEnvironmentResource.md)
- [Ресурс Linux FileLine](../reference/resources/linux/lnxFileLineResource.md)
- [Ресурс Linux File](../reference/resources/linux/lnxFileResource.md)
- [Ресурс Linux Group](../reference/resources/linux/lnxGroupResource.md)
- [Ресурс Linux Package](../reference/resources/linux/lnxPackageResource.md)
- [Ресурс Linux Script](../reference/resources/linux/lnxScriptResource.md)
- [Ресурс Linux Service](../reference/resources/linux/lnxServiceResource.md)
- [Ресурс Linux SshAuthorizedKeys](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [Ресурс Linux User](../reference/resources/linux/lnxUserResource.md)
