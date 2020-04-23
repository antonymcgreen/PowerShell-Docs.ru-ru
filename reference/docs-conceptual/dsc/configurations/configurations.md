---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Конфигурации DSC
ms.openlocfilehash: d7749ec88f9cca3e29c6b38d61fb73776af7ceb4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954501"
---
# <a name="dsc-configurations"></a>Конфигурации DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Конфигурации DSC — это сценарии PowerShell, определяющие особый тип функции.
Для определения конфигурации используйте ключевое слово PowerShell **Configuration**.

```powershell
Configuration MyDscConfiguration {
    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = 'Present'
            Name = 'RSAT'
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}
MyDscConfiguration
```

Сохраните скрипт в виде файла `.ps1`.

## <a name="configuration-syntax"></a>Синтаксис конфигурации

Сценарий конфигурации состоит из следующих элементов:

- Блок **Configuration**. Это основной блок сценария. Для его определения необходимо использовать ключевое слово **Configuration** и указать имя. В этом случае имя конфигурации — MyDscConfiguration.
- Один блок **Node** или несколько. Определяют настраиваемые вами узлы (компьютеры или виртуальные машины). В представленной выше конфигурации присутствует один блок **Node**, соответствующий компьютеру с именем TEST-PC1. Блок Node может принимать несколько имен компьютеров.
- Один блок ресурсов или несколько. В этих блоках конфигурация определяет свойства настраиваемых ресурсов. В данном случае используются два блока ресурсов, каждый из которых вызывает ресурс WindowsFeature.

В блоке **Configuration** можно делать все то же самое, что и в функции PowerShell. Например, в предыдущем примере вместо того, чтобы прописывать имя целевого компьютера конфигурации в коде, можно добавить в имя узла соответствующий параметр:

В этом примере вы указываете имя узла, передавая его как параметр **ComputerName** при компиляции конфигурации. По умолчанию используется имя localhost.

```powershell
Configuration MyDscConfiguration
{
    param
    (
        [string[]]$ComputerName='localhost'
    )

    Node $ComputerName
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

Блок **Node** также может принимать несколько имен компьютеров. В приведенном выше примере вы можете использовать параметр `-ComputerName` или передать разделенный запятыми список компьютеров непосредственно в блок **Node**.

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

При указании списка компьютеров для блока **Node** из конфигурации необходимо использовать нотацию массива.

```powershell
Configuration MyDscConfiguration
{
    Node @('localhost', 'Server01')
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

## <a name="compiling-the-configuration"></a>Компиляция конфигурации

Прежде чем активировать конфигурацию, необходимо скомпилировать ее в MOF-документ.
Для этого нужно вызвать конфигурацию так же, как вы вызывали функцию PowerShell.
Последняя строка примера, содержащего только имя конфигурации, вызывает конфигурацию.

> [!NOTE]
> Для вызова конфигурации функция должна находиться в глобальной области видимости (как и любая другая функция PowerShell).
> Для этого нужно либо использовать вызов сценария с точкой, либо выполнить сценарий конфигурации, нажав клавишу F5 или кнопку **Выполнить сценарий** в интегрированной среде сценариев.
> Чтобы использовать вызов сценария с точкой, выполните команду `. .\myConfig.ps1`, где `myConfig.ps1` — это имя файла сценария, который содержит конфигурацию.

При вызове конфигурации она выполняет следующие действия:

- разрешает все переменные;
- создает папку в текущем каталоге с тем же именем, что и у конфигурации;
- создает файл с именем _имя_узла_.mof в новой папке, где _имя_узла_ — это имя целевого узла конфигурации.
  Если узлов несколько, MOF-файл создается для каждого из них.

> [!NOTE]
> MOF-файл содержит все сведения о конфигурации целевого узла. Поэтому его необходимо хранить в безопасном месте.
> Дополнительные сведения см. в статье [Защита MOF-файла](../pull-server/secureMOF.md).

При компиляции первой приведенной конфигурации создается следующая структура папок:

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 localhost.mof
```

Если конфигурация принимает какой-либо параметр, как во втором примере, его необходимо указывать во время компиляции. Вот как это выглядит:

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration -ComputerName 'MyTestNode'
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 MyTestNode.mof
```

## <a name="using-new-resources-in-your-configuration"></a>Использование новых ресурсов в конфигурации

Выполняя предыдущие примеры, вы могли заметить предупреждение о том, что используемый ресурс не импортирован.
Сейчас DSC поставляется с модулем PSDesiredStateConfiguration, в который входят 12 ресурсов.

Командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) позволяет определить, какие ресурсы установлены в системе и доступны для использования LCM.
После добавления в `$env:PSModulePath` и правильного распознавания командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) эти модули нужно будет загрузить в конфигурацию.

**Import-DscResource** — это динамическое ключевое слово, распознаваемое только в блоке **Configuration**, и оно не является командлетом.
**Import-DscResource** поддерживает два параметра:

- Параметр **ModuleName** — рекомендуемый способ применения **Import-DscResource**. Он принимает имя модуля, содержащего ресурсы для импорта (а также массив строк с именами модулей).
- Параметр **Name** — имя импортируемого ресурса. Это не то понятное имя, которое возвращается командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), а имя класса, используемое при определении схемы ресурса (возвращается как параметр **ResourceType** командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).

Дополнительные сведения об использовании `Import-DSCResource` см. в статье об [использовании Import-DSCResource](import-dscresource.md).

## <a name="powershell-v4-and-v5-differences"></a>Различия PowerShell версий 4 и 5

Из-за существующих различий ресурсы DSC должны храниться в PowerShell 4.0. Дополнительные сведения см. в разделе о [расположении ресурса](import-dscresource.md#resource-location).

## <a name="see-also"></a>См. также:

- [Обзор Windows PowerShell Desired State Configuration](../overview/overview.md)
- [Ресурсы DSC](../resources/resources.md)
- [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md)
