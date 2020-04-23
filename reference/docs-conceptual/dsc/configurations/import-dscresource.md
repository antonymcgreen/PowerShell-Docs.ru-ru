---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование Import-DSCResource
ms.openlocfilehash: a041169ad557becf7ca87641d9ce5222ee8f6beb
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "79402451"
---
# <a name="using-import-dscresource"></a>Использование Import-DSCResource

`Import-DScResource` — это динамическое ключевое слово, которое может использоваться только внутри блока сценария конфигурации. Ключевое слово `Import-DSCResource` используется для импорта всех ресурсов, необходимых в конфигурации. Ресурсы в `$pshome` импортируются автоматически, но по-прежнему рекомендуется явным образом импортировать все ресурсы, используемые в [конфигурации](Configurations.md).

Ниже показан синтаксис для ключевого слова `Import-DSCResource`.  При указании модулей по имени необходимо перечислять каждый модуль в новой строке.

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>] [-ModuleVersion <ModuleVersion>]
```

|Параметр  |Описание  |
|---------|---------|
|`-Name`|Имена ресурсов DSC, которые необходимо импортировать. Если указано имя модуля, команда ищет эти ресурсы DSC в этом модуле. В противном случае команда ищет ресурсы DSC во всех путях ресурсов DSC. Поддерживаются подстановочные знаки.|
|`-ModuleName`|Имя или спецификация модуля.  Если указать ресурсы для импорта из модуля, команда предпримет попытку импортировать только эти ресурсы. Если указать только модуль, команда импортирует все ресурсы DSC в модуле.|
|`-ModuleVersion`|Начиная с PowerShell 5.0, можно указать версию модуля, который должна использовать конфигурация. Дополнительные сведения см. в статье [Импорт определенной версии установленного ресурса](sxsresource.md).|

```powershell
Import-DscResource -ModuleName xActiveDirectory
```

## <a name="example-use-import-dscresource-within-a-configuration"></a>Пример использование Import-DSCResource в конфигурации

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration -Name Service, File, Registry

    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    # As a best practice, list each requirement on a different line if possible.  This makes reviewing
    # multiple changes in source control a bit easier.
    Import-DSCResource -Name File
    Import-DSCResource -Name TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    # When specifying the modulename parameter, it is a requirement to list each on a new line.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
    # In PowerShell 5.0 and later, you can specify a ModuleVersion parameter
    Import-DSCResource -ModuleName ComputerManagementDsc -ModuleVersion 6.0.0.0
...
```

> [!NOTE]
> Указание нескольких значений для имен ресурсов и модулей в одной команде не поддерживается. Это может привести к недетерминированному поведению относительно того, с какого ресурса необходимо загружать тот или иной модуль, в случае если один и тот же ресурс существует в нескольких модулях. Приведенная ниже команда вызовет ошибку во время компиляции.
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

Аспекты, которые следует учитывать при использовании только параметра имени:

- Это может быть ресурсоемкая операция в зависимости от количества установленных на компьютере модулей.
- Она загрузит первый найденный ресурс с заданным именем. В случае если существует несколько ресурсов с одним именем, она может загрузить не тот ресурс.

Рекомендуется указать `–ModuleName` с параметром `-Name`, как показано ниже.

Это обеспечивает следующие преимущества:

- Уменьшается влияние на производительность за счет ограничения области поиска для указанного ресурса.
- В этом случае явно задается определяющий ресурс модуль, обеспечивая загрузку нужного ресурса.

> [!NOTE]
> В PowerShell 5.0 ресурсы DSC могут иметь несколько версий, и эти версии можно устанавливать на компьютере параллельно. Это реализуется благодаря наличию нескольких версий модуля ресурсов, которые содержатся в одной папке модуля.
> Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](sxsresource.md).

## <a name="intellisense-with-import-dscresource"></a>Технология IntelliSense с Import-DSCResource

При создании конфигурации DSC в ISE программа PowerShell предоставляет IntelliSence для ресурсов и их свойств. Определения ресурсов в пути модуля `$pshome` загружаются автоматически. При импорте ресурсов с использованием ключевого слова `Import-DSCResource` добавляются определения указанного ресурса и в Intellisense добавляется схема импортируемых ресурсов.

![Применение технологии Intellisense для ресурса](media/import-dscresource/resource-intellisense.png)

> [!NOTE]
> Начиная с PowerShell 5.0 в ISE было добавлено завершение нажатием клавиши TAB для ресурсов DSC и их свойств. Дополнительные сведения см. в статье о [ресурсах DSC](../resources/resources.md).

При компиляции конфигурации PowerShell использует импортированные определения ресурсов, чтобы проверить все блоки ресурсов в конфигурации.
Каждый блок ресурсов проверяется с использованием определения схемы ресурса на соответствие следующим правилам:

- используются только свойства, определенные в схеме;
- типы данных для каждого свойства заданы правильно;
- свойства ключей заданы;
- свойство только для чтения не используется;
- проверка типов сопоставлений значения.

Рассмотрим следующую конфигурацию:

```powershell
Configuration SchemaValidationInCorrectEnumValue
{
    # It is best practice to explicitly import all resources used in your Configuration.
    # This includes resources that are imported automatically, like WindowsFeature.
    Import-DSCResource -Name WindowsFeature
    Node localhost
    {
        WindowsFeature ROLE1
        {
            Name = "Telnet-Client"
            Ensure = "Invalid"
        }
    }
}
```

Компиляция этой конфигурации приведет к ошибке.

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values 'Invalid' is not supported or valid for property 'Ensure' on class 'WindowsFeature'. Please specify only supported values: Present, Absent.
```

IntelliSense и проверка схемы позволяют обнаруживать больше ошибок во время анализа и компиляции, избегая осложнений во время выполнения.

> [!NOTE]
> Каждый ресурс DSC может иметь имя и **FriendlyName**, определенное схемой ресурса. Ниже приведены две первые строки файла MSFT_ServiceResource.shema.mof.
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> При использовании этого ресурса в конфигурации можно указать **MSFT_ServiceResource** или **Service**.

## <a name="powershell-v4-and-v5-differences"></a>Различия PowerShell версий 4 и 5

Существует несколько различий, заметных при создании конфигураций в PowerShell версии 4.0, 5.0 и более поздних. В этом разделе освещены различия, которые имеют отношение к этой статье.

### <a name="multiple-resource-versions"></a>Несколько версий ресурсов

Установка нескольких версий ресурсов и их параллельное использование не поддерживаются в PowerShell 4.0. Если вы заметили проблемы при импорте ресурсов в свою конфигурацию, убедитесь, что установлена только одна версия ресурса.

На рисунке ниже показано, что установлены две версии модуля **xPSDesiredStateConfiguration**.

![Исправление нескольких версий ресурсов](media/import-dscresource/multiple-resource-versions-broken.png)

Скопируйте содержимое нужной версии модуля на верхний уровень каталога модуля.

![Исправление нескольких версий ресурсов](media/import-dscresource/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a>Расположение ресурса

При разработке и компилировании конфигураций ваши ресурсы можно хранить в любом каталоге, указанном в параметре [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path). В PowerShell 4.0 диспетчер LCM требовал, чтобы все модули ресурсов DSC хранились по пути Program Files\WindowsPowerShell\Modules или `$pshome\Modules`. Начиная с PowerShell 5.0 это требование было удалено, а модули ресурсов могут храниться в любом каталоге, заданном с помощью параметра `PSModulePath`.

### <a name="moduleversion-added"></a>Добавлен параметр ModuleVersion

Начиная с версии PowerShell 5.0, параметр `-ModuleVersion` позволяет указать версию модуля для использования в конфигурации.

## <a name="see-also"></a>См. также раздел

- [Ресурсы](../resources/resources.md)
