---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование Import-DSCResource
ms.openlocfilehash: 6bc3c1aa1d34a05e3188666da825322235c0672e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402771"
---
# <a name="using-import-dscresource"></a>Использование Import-DSCResource

`Import-DScResource` — Это динамическое ключевое слово, который может использоваться только внутри блока сценария для конфигурации. `Import-DSCResource` Ключевое слово, чтобы импортировать все ресурсы, необходимые в конфигурации. Ресурсы в группе `$phsome` импортируются автоматически, но он по-прежнему считается наилучшим решением будет явно импортировать все ресурсы, используемые в вашей [конфигурации](Configurations.md).

Синтаксис `Import-DSCResource` показан ниже.

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName(s)>]
```

|Параметр  |Описание  |
|---------|---------|
|`-Name`|Имена ресурсов DSC, который необходимо импортировать. Если указано имя модуля, команда ищет эти ресурсы DSC в этом модуле. в противном случае команда ищет ресурсы DSC во всех путях ресурсов DSC. Поддерживаются подстановочные знаки.|
|`-ModuleName`|Имена контейнеров модуль или модуль спецификацию (спецификации).  Если указать ресурсы для импорта из модуля, команда будет предпринята попытка импортировать только те ресурсы. Если указать только модуль, команда импортирует все ресурсы DSC в модуле.|

Можно использовать подстановочные знаки с `-Name` при использовании командлета `Import-DSCResource`.

```powershell
Import-DscResource -Name * -ModuleName xActiveDirectory;
```

## <a name="example-use-import-dscresource-within-a-configuration"></a>Пример: Использовать Import-DSCResource в конфигурации

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName MS_DSC1 -name Service, File, Registry

    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    Import-DSCResource -Name File, TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
...
```

> [!NOTE]
> Указание нескольких значений для имен ресурсов и модулей в одной команде не поддерживаются. Он может иметь неопределенное поведение, о какие ресурсы для загрузки из какой модуль, если же ресурс существует в нескольких модулях. Указанную ниже команду, приведет к ошибке во время компиляции.
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

Что следует учитывать при использовании только имя параметра:

- Это — ресурсоемкая операция, в зависимости от количества модулей, установленных на компьютере.
- Он загрузит первый ресурс с заданным именем. В случае, если существует более одного ресурса с тем же именем установлен, его удалось загрузить неправильный ресурс.

Рекомендуется использовать для указания `–ModuleName` с `-Name` параметра, как описано ниже.

Такое использование имеет следующие преимущества:

- Он уменьшает влияние на производительность, ограничивая область поиска для указанного ресурса.
- Он явно определяет модуль определения ресурса, убедитесь, что загружается необходимого ресурса.

> [!NOTE]
> В PowerShell 5.0 ресурсы DSC могут иметь несколько версий, и эти версии можно устанавливать на компьютере параллельно. Это реализуется благодаря наличию нескольких версий модуля ресурсов, которые содержатся в одной папке модуля.
> Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](sxsresource.md).

## <a name="intellisense-with-import-dscresource"></a>IntelliSense с Import-DSCResource

При создании конфигурации DSC в интегрированной среде Сценариев, PowerShell предоставляет IntelliSence для ресурсов и их свойств. Определения ресурсов в группе `$pshome` путь к модулю загружаются автоматически. При импорте ресурсов с помощью `Import-DSCResource` ключевое слово, добавляются определения указанного ресурса и Intellisense расширяется для включения схемы импортируемых ресурсов.

![Intellisense ресурсов](/media/resource-intellisense.png)

> [!NOTE]
> Начиная с PowerShell 5.0, был добавлен нажатием клавиши TAB в интегрированную среду сценариев для ресурсов DSC и их свойства. Дополнительные сведения см. в разделе [ресурсы](../resources/resources.md).

При компиляции конфигурации, PowerShell использует определения импортируемого ресурса для проверки всех блоков ресурсов в конфигурации.
Проверяется каждый блок ресурсов, с помощью определения схемы ресурса, для следующих правил.

- Используются только свойства, определенные в схеме.
- Типы данных для каждого свойства заданы правильно.
- Указаны свойства ключей.
- Используется не свойство только для чтения.
- Проверки на значение сопоставляет типы.

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
            Name = “Telnet-Client”
            Ensure = “Invalid”
        }
    }
}
```

Компиляция этой конфигурации приведет к ошибке.

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values ‘Invalid’ is not supported or valid for property ‘Ensure’ on class ‘WindowsFeature’. Please specify only supported values: Present, Absent.
```

IntelliSense и схемы проверки можно перехватить больше ошибок во время синтаксического анализа и компиляции, как избежать сложностей во время выполнения.

> [!NOTE]
> Каждый ресурс DSC может иметь имя и **FriendlyName** определением схемы ресурса. Ниже приведены две первые строки «MSFT_ServiceResource.shema.mof».
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> При использовании этого ресурса в конфигурации, можно указать **MSFT_ServiceResource** или **службы**.

## <a name="powershell-v4-and-v5-differences"></a>PowerShell v4 и v5 различия

Существует несколько различий, получаемых при создании конфигурации в PowerShell 4.0 Visual Studio. PowerShell 5.0 и более поздних версий. В этом разделе будут указаны различия, отображается отношение к этой статье.

### <a name="multiple-resource-versions"></a>Несколько версий ресурсов

Установка и использование нескольких версий ресурсы параллельно не поддерживается в PowerShell 4.0. Если вы заметили проблемы при импорте ресурсов в вашей конфигурации, убедитесь, что имеется только одна версия установки ресурсов.

На рисунке ниже, две версии **xPSDesiredStateConfiguration** устанавливаются модуля.

![Несколько версий ресурсов исправлена](/media/multiple-resource-versions-broken.md)

Скопируйте содержимое версии нужный модуль на верхний уровень каталога модуля.

![Несколько версий ресурсов исправлена](/media/multiple-resource-versions-fixed.md)

### <a name="resource-location"></a>Расположение ресурса

При разработке и компилирование конфигураций, ресурсы могут храниться в любой каталог, указанный в вашей [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path). В PowerShell 4.0, LCM требуются все модули ресурсов DSC для сохранения в разделе «Программы Files\WindowsPowerShell\Modules» или `$pshome\Modules`. Начиная с PowerShell 5.0, и это требование было удалено, а модули ресурсов, которые могут храниться в любой каталог, заданный параметром `PSModulePath`.

## <a name="see-also"></a>См. также:

- [Ресурсы](../resources/resources.md)
