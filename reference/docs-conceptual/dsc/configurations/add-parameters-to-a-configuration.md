---
ms.date: 12/12/2018
keywords: dsc,powershell,resource,gallery,setup
title: Добавление параметров в конфигурацию
ms.openlocfilehash: 9aa4c746042e89d7767e1b326233dcca1e5c4c24
ms.sourcegitcommit: b80ce0396550d0896189d0205d6c4b4372ac2015
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141404"
---
# <a name="add-parameters-to-a-configuration"></a>Добавление параметров в конфигурацию

Как и функции, [конфигурации](configurations.md) могут быть параметризованы. Так они становятся более динамичными на основе данных, вводимых пользователем. Шаги похожи на описанные в разделе о [функциях с параметрами](/powershell/module/microsoft.powershell.core/about/about_functions).

Этот пример начинается с базовой конфигурации, которая настраивает службу "Диспетчер очереди печати" (Spooler) в состояние Running (Выполняется).

```powershell
Configuration TestConfig
{
    # It is best practice to explicitly import any required resources or modules.
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

В отличие от функции, атрибут [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) не добавляет функциональных возможностей. Помимо [общих параметров](/powershell/module/microsoft.powershell.core/about/about_commonparameters), конфигурации могут также использовать следующие встроенные параметры, не требуя их определения пользователем.

|        Параметр        |                                         Description                                          |
| ----------------------- | -------------------------------------------------------------------------------------------- |
| `-InstanceName`         | Используется при определении [составных конфигураций](compositeconfigs.md)                             |
| `-DependsOn`            | Используется при определении [составных конфигураций](compositeconfigs.md)                             |
| `-PSDSCRunAsCredential` | Используется при определении [составных конфигураций](compositeconfigs.md)                             |
| `-ConfigurationData`    | Используется для передачи структурированных [данных конфигурации](configData.md), применяемых в конфигурации. |
| `-OutputPath`           | Используется, чтобы указать, где будет скомпилирован файл \<имя_компьютера\>.mof.                      |

## <a name="adding-your-own-parameters-to-configurations"></a>Добавление собственных параметров в конфигурации

Помимо встроенных параметров, вы можете также добавить в конфигурации собственные параметры.
Блок параметров помещается непосредственно в объявлении конфигурации, как и функция. Блок параметров конфигурации должен быть вне любых объявлений **узла** и выше любых инструкций *import*. Добавив параметры, вы можете сделать конфигурации более надежными и динамическими.

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a>Добавление параметра ComputerName

Первым параметром, который можно добавить, является `-Computername`. Так вы сможете динамически компилировать MOF-файл для любого параметра `-Computername`, который передается в конфигурацию. Аналогично функциям, вы также можете определить значение по умолчанию в случае, если пользователь не передаст значение для параметра `-ComputerName`.

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

Затем в конфигурации вы можете указать параметр `-ComputerName` при определении блока узла.

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a>Вызов конфигурации с параметрами

После добавления параметров в конфигурацию их можно использовать так же, как с командлетом.

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a>Компиляция нескольких MOF-файлов

Блок узла также может принимать разделенный запятыми список имен компьютеров и будет автоматически создавать MOF-файлы для каждого компьютера. Вы также можете запустить приведенный ниже пример для создания MOF-файлов для всех компьютеров, передаваемых параметру `-ComputerName`.

```powershell
Configuration TestConfig
{
    param
    (
        [String[]]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
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

## <a name="advanced-parameters-in-configurations"></a>Расширенные параметры в конфигурациях

В дополнение к параметру `-ComputerName`, вы можете добавить параметры для имени и состояния службы.
В следующем примере добавляется блок параметров с параметром `-ServiceName`. Этот блок используется для динамического определения блока ресурса **Service**. В нем также добавляется параметр `-State` для динамического определения **состояния** в блоке ресурса **Service**.

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

    # It is best practice to explicitly import any required resources or modules.
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
> В расширенных сценариях может быть более целесообразно переместить динамические данные в структурированные [данные конфигурации](configData.md).

Этот пример конфигурации теперь принимает динамическое значение `$ServiceName`, но если оно не задано, компиляция приведет к ошибке. Вы также можете добавить значение по умолчанию, как в следующем примере.

```powershell
[String]
$ServiceName="Spooler"
```

Хотя в этом экземпляре может быть более целесообразно просто заставить пользователя указать значение для параметра `$ServiceName`. Атрибут `parameter` позволяет добавлять дополнительную поддержку проверки и конвейера для параметров конфигурации.

Над какими-либо объявлениями параметров добавьте блок атрибутов `parameter`, как показано в приведенном ниже примере.

```powershell
[parameter()]
[String]
$ServiceName
```

Вы можете указать аргументы для каждого атрибута `parameter`, чтобы управлять аспектами определенного параметра. В следующем примере параметр `$ServiceName` изменяется на **обязательный**.

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

Для параметра `$State` мы бы хотели запретить пользователю указывать значения за пределами предопределенного набора (например, Running, Stopped). Атрибут `ValidationSet*` будет запрещать пользователю указывать значения за пределами определенного набора (например, Running, Stopped). В следующем примере добавляется атрибут `ValidationSet` для параметра `$State`. Так как мы не хотим изменять параметр `$State` на **обязательный**, нам нужно будет добавить для него значение по умолчанию.

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> Вам не нужно указывать атрибут `parameter` при использовании атрибута `validation`.

Дополнительные сведения об атрибуте `parameter` и атрибутах проверки см. в разделе о [расширенных параметрах функций](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).

## <a name="fully-parameterized-configuration"></a>Полностью параметризованная конфигурация

Теперь у нас есть параметризованная конфигурация, которая вынуждает пользователя указывать параметры `-InstanceName`, `-ServiceName` и проверяет параметр `-State`.

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

    # It is best practice to explicitly import any required resources or modules.
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

## <a name="see-also"></a>См. также раздел

- [Создание справки по конфигурациям DSC](configHelp.md)
- [Условные операторы и циклы в конфигурациях](flow-control-in-configurations.md)
- [Using configuration data in DSC](configData.md) (Использование данных конфигурации в DSC)
- [Разделение данных конфигурации и данных среды](separatingEnvData.md)
