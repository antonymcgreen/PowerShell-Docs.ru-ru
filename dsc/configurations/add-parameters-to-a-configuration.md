---
ms.date: 12/12/2018
keywords: DSC, powershell, ресурсов, в коллекции, программа установки
title: Добавление параметров в конфигурацию
ms.openlocfilehash: 15213404f0cdd6416baf1f83af91b8f5279cc97f
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402555"
---
# <a name="add-parameters-to-a-configuration"></a>Добавление параметров в конфигурацию

Аналогично функциям, [конфигураций](configurations.md) могут быть параметризованы, чтобы разрешить более динамической конфигурации, на основе ввода пользователя. Шаги похожи на описанные в [функции с параметрами](/powershell/module/microsoft.powershell.core/about/about_functions).

В этом примере запускается с базовую конфигурацию, которая настраивает службу «Spooler», «Выполняется».

```powershell
Configuration TestConfig
{
    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a>Встроенные параметры конфигурации

В отличие от функции, [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) атрибут добавляет функциональные возможности отсутствуют. В дополнение к [общих параметров](/powershell/module/microsoft.powershell.core/about/about_commonparameters), конфигурации можно также использовать следующие встроенные параметры, не требуя их определения.

|Параметр  |Описание  |
|---------|---------|
|`-InstanceName`|Использовать при определении [составного конфигурации](compositeconfigs.md)|
|`-DependsOn`|Использовать при определении [составного конфигурации](compositeconfigs.md)|
|`-PSDSCRunAsCredential`|Использовать при определении [составного конфигурации](compositeconfigs.md)|
|`-ConfigurationData`|Используется для передачи в структурированный [данные конфигурации](configData.md) для использования в конфигурации.|
|`-OutputPath`|Используется, чтобы указать, где в «\<computername\>.mof» компиляции файла|

## <a name="adding-your-own-parameters-to-configurations"></a>Добавление собственных параметров конфигурации

Помимо встроенных параметров можно также добавить собственные параметры для конфигурации. Блок параметров переходит непосредственно в объявлении конфигурации, так же, как функции. Блок параметров конфигурации должны быть вне любого **узел** объявления и более поздних версий, любой *импорта* инструкций. Добавив параметры, конфигурации можно сделать более надежным и динамические.

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a>Добавьте параметр ComputerName

Первый параметр, можно добавить является `-Computername` параметра, поэтому может динамически компилировать MOF «-» файла для любого `-Computername` передать в конфигурацию. Как и функции можно также определить значение по умолчанию, в случае, если пользователь не передать значение для `-ComputerName`

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

В конфигурацию, можно затем указать ваш `-ComputerName` параметров при определении в блоке узла.

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a>Вызов конфигурации с параметрами

После добавления параметров конфигурации, их можно использовать так же, как с помощью командлета.

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a>Компиляция нескольких файлы MOF

В блоке узла также может принять разделенный запятыми список имен компьютеров и автоматически создаст MOF-файлы для каждого. Можно запустить приведенный ниже, для создания MOF-файлы для всех компьютеров, передаваемый `-ComputerName` параметра.

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ComputerName="localhost"
    )

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a>Дополнительные параметры в конфигурации

В дополнение к `-ComputerName` параметр, можно добавить параметры для имени службы и состояние. В следующем примере добавляется параметр блок с `-ServiceName` параметр и использует его для динамического определения **службы** блоке ресурсов. Он также добавляет `-State` параметр для динамического определения **состояние** в **службы** блоке ресурсов.

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> В различных сценариях advacned, может быть более целесообразно для перемещения динамических данных в структурированной [данные конфигурации](configData.md).

Этот пример конфигурации теперь принимает динамический `$ServiceName`, но если тип не задан, компиляция приведет к ошибке. Можно добавить значение по умолчанию, как в следующем примере.

```powershell
[String]
$ServiceName="Spooler"
```

В этом экземпляре, смысл просто заставить пользователю указать значение для `$ServiceName` параметра. `parameter` Атрибут позволяет добавлять дополнительные проверки и конвейера, поддерживают параметрам вашей конфигурации.

Добавьте над любое объявление параметра `parameter` блок атрибутов, как показано в приведенном ниже примере.

```powershell
[parameter()]
[String]
$ServiceName
```

Можно указать аргументы для каждого `parameter` атрибут, чтобы управлять различными аспектами определенный параметр. В нижеследующем примере `$ServiceName` **обязательные** параметра.

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

Для `$State` параметра, мы бы хотели запрет на указание значений за пределами предопределенного набора (например, выполнение, остановлен) `ValidationSet*`атрибут будет запрет на указание значений за пределами предопределенного набора (например, выполнение, Остановлен). В следующем примере добавляется `ValidationSet` атрибут `$State` параметра. Так как мы не хотели бы `$State` параметр **обязательные**, нам нужно будет добавить для него значение по умолчанию.

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> Необходимо указать `parameter` атрибут при использовании `validation` атрибута.

Дополнительные сведения о `parameter` и атрибуты проверки в [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters.md).

## <a name="fully-parameterized-configuration"></a>Полностью параметризованных конфигурации

Теперь у нас есть параметризованные конфигурации, которая вынуждает пользователя для указания `-InstanceName`, `-ServiceName`и проверяет `-State` параметра.

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost",
    )

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a>См. также:

- [Создание справки по конфигурациям DSC](configHelp.md)
- [Динамические конфигурации](flow-control-in-configurations.md)
- [Использовать данные конфигурации в конфигурации](configData.md)
- [Отдельные конфигурации данных и данных среды](separatingEnvData.md)
