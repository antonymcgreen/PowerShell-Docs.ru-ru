---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
ms.openlocfilehash: 1f77b5e6630a2e3de6e1d1a05638f94d2df039ae
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54046697"
---
# <a name="dsc-resources"></a>Ресурсы DSC

>Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC. В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).

Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS.  Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.

Каждый ресурс имеет * схему, которая определяет синтаксис, необходимые для использования ресурса в [конфигурации](../configurations/configurations.md). Схема ресурса, может быть определена следующим образом:

- **«Schema.Mof»** файла: Определить больше всего ресурсов их *схемы* в schema.mof файле, с использованием [формат управляющих объектов](/windows/desktop/wmisdk/managed-object-format--mof-).
- **"\<Имя ресурса\>. schema.psm1"** файла: [Составные ресурсы](../configurations/compositeConfigs.md) определить их *схемы* в "<ResourceName>. schema.psm1" файл с помощью [блок параметров](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).
- **"\<Имя ресурса\>.psm1"** файла: Класс на основе ресурсов DSC определяют их *схемы* в определении класса. Элементы синтаксиса, обозначаются как свойства класса. Дополнительные сведения см. в разделе [статье "about_classes"](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).

Чтобы получить синтаксис для ресурсов DSC, используйте [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) командлет с `-Syntax` параметра. Это похоже на использование [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с `-Syntax` параметра, чтобы получить синтаксис командлета. Шаблон, используемый для блока ресурсов для ресурса, указанную вами будут показаны результаты, вы увидите.

```powershell
Get-DscResource -Syntax Service
```

Выходные данные, которые вы видите должен соответствовать приведенному ниже, на то, что этот ресурс синтаксис может измениться в будущем. Синтаксис командлета, такие как *ключи* видно в квадратные скобки, являются необязательными. Типы укажите тип данных, которые ожидаются процессом каждого ключа.

> [!NOTE]
> **Убедитесь, что** ключа является необязательным, так как по умолчанию используется «Отсутствует».

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

Внутри конфигурации **службы** блоке ресурсов может выглядеть так, чтобы **убедитесь, что** , на котором работает служба диспетчера очереди печати.

> [!NOTE]
> Прежде чем использовать ресурс в конфигурации, необходимо импортировать его с помощью [Import-DSCResource](../configurations/import-dscresource.md).

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

Конфигурации может содержать несколько экземпляров одного типа ресурсов. Каждый экземпляр должен иметь имя уникально. В следующем примере второй **службы** блоке ресурсов добавляется для настройки службы «DHCP».

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
> Начиная с PowerShell 5.0, был добавлен intellisense для DSC. Эта новая функция позволяет использовать \<ВКЛАДКЕ\> и \<Ctrl + пробел\> для автозаполнения имен ключей.

![Ресурс нажатием клавиши TAB](../media/resource-tabcompletion.png)

## <a name="built-in-resources"></a>Встроенные ресурсы

Помимо ресурсы сообщества существуют встроенные ресурсы для Windows, ресурсы для Linux и ресурсы для зависимостей между узлами. Описанные выше действия можно использовать для определения синтаксис этих ресурсов и их использование. Страницы, которые обслуживает эти ресурсы были архивированы в разделе **ссылку**.

Встроенные ресурсы Windows

* [Ресурс Archive](../reference/resources/windows/archiveResource.md)
* [Ресурс Environment](../reference/resources/windows/environmentResource.md)
* [Ресурс File](../reference/resources/windows/fileResource.md)
* [Ресурс Group](../reference/resources/windows/groupResource.md)
* [Ресурс GroupSet](../reference/resources/windows/groupSetResource.md)
* [Ресурс Log](../reference/resources/windows/logResource.md)
* [Ресурс Package](../reference/resources/windows/packageResource.md)
* [Ресурс ProcessSet](../reference/resources/windows/ProcessSetResource.md)
* [Ресурс Registry](../reference/resources/windows/registryResource.md)
* [Ресурс Script](../reference/resources/windows/scriptResource.md)
* [Ресурс Service](../reference/resources/windows/serviceResource.md)
* [Ресурс ServiceSet](../reference/resources/windows/serviceSetResource.md)
* [Ресурс User](../reference/resources/windows/userResource.md)
* [Ресурс WindowsFeature](../reference/resources/windows/windowsFeatureResource.md)
* [Ресурс WindowsFeatureSet](../reference/resources/windows/windowsFeatureSetResource.md)
* [Ресурс WindowsOptionalFeature](../reference/resources/windows/windowsOptionalFeatureResource.md)
* [Ресурс WindowsOptionalFeatureSet](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
* [WindowsPackageCabResource ресурсов](../reference/resources/windows/windowsPackageCabResource.md)
* [Ресурс WindowsProcess](../reference/resources/windows/windowsProcessResource.md)

[Зависимость между узлами](../configurations/crossNodeDependencies.md) ресурсы

* [WaitForAll ресурсов](../reference/resources/windows/waitForAllResource.md)
* [WaitForSome ресурсов](../reference/resources/windows/waitForSomeResource.md)
* [WaitForAny ресурсов](../reference/resources/windows/waitForAnyResource.md)

Ресурсы пакета управления

* [Ресурс PackageManagement](../reference/resources/packagemanagement/PackageManagementDscResource.md)
* [Ресурс PackageManagementSource](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

Ресурсов под управлением Linux

* [Ресурс Linux Archive](../reference/resources/linux/lnxArchiveResource.md)
* [Ресурс Environment Linux](../reference/resources/linux/lnxEnvironmentResource.md)
* [Linux FileLine ресурсов](../reference/resources/linux/lnxFileLineResource.md)
* [Ресурс Linux File](../reference/resources/linux/lnxFileResource.md)
* [Ресурс группы Linux](../reference/resources/linux/lnxGroupResource.md)
* [Ресурс Linux Package](../reference/resources/linux/lnxPackageResource.md)
* [Ресурс Script для Linux](../reference/resources/linux/lnxScriptResource.md)
* [Ресурс службы Linux](../reference/resources/linux/lnxServiceResource.md)
* [Linux SshAuthorizedKeys ресурсов](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
* [Ресурс пользователя Linux](../reference/resources/linux/lnxUserResource.md)
