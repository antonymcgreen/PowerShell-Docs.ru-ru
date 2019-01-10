---
ms.date: 12/12/2018
keywords: DSC, powershell, службы, конфигурации программы установки
title: Создание, компиляция и применение конфигурации
ms.openlocfilehash: fa4d98fd12202439ba7025fd8af3fa398653ca05
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402347"
---
> Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0

# <a name="write-compile-and-apply-a-configuration"></a>Создание, компиляция и применение конфигурации

В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).
В следующем примере вы узнаете, как написать и применить очень простой конфигурации. Конфигурация будет убедитесь, что файл «HelloWorld.txt» существует на локальном компьютере. При удалении файла, DSC будет создать его заново в следующий раз она обновляет.

Общие сведения о DSC и как это работает, см. в разделе [Desired State Configuration Обзор для разработчиков](../overview/overview.md).

## <a name="requirements"></a>Требования

Для выполнения этого примера требуется компьютер под управлением PowerShell 4.0 или более поздней версии.

## <a name="write-the-configuration"></a>Запись конфигурации

[Конфигурация](configurations.md) DSC — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).

В интегрированной среде Сценариев PowerShell или другой редактор PowerShell введите следующее:

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

Сохраните файл как «HelloWorld.ps1».

Определение конфигурации — как определение функции. Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.

Конфигурация вызывает один [ресурсы](../resources/resources.md), `File` ресурсов. Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.

## <a name="compile-the-configuration"></a>Компиляция конфигурации

Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.
Выполнение конфигурации, как функция, для каждого узла, определенного параметром компиляции один файл «.mof» `Node` блока.
Чтобы запустить конфигурацию, необходимо *точкой* «HelloWorld.ps1» сценарий в текущей области.
Дополнительные сведения см. в разделе [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).

*Точкой* «HelloWorld.ps1» скрипта, введя в путь, где вы сохранили его, после `. ` (точка, места). Затем можно запустить конфигурацию, вызвав его как функцию.

```powershell
. C:\Scripts\WebsiteTest.ps1
HelloWolrd
```

Будут созданы следующие выходные данные:

```output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a>Применение конфигурации

Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).

`Start-DscConfiguration` Командлет сообщает об [локальный диспетчер конфигураций (LCM)](../managing-nodes/metaConfig.md), подсистемы DSC для применения конфигурации.
LCM вызывает ресурсы DSC для применения конфигурации.

Используйте приведенный ниже код для выполнения `Start-DSCConfiguration` командлета. Укажите путь к каталогу, где «localhost.mof» хранятся в `-Path` параметра. `Start-DSCConfiguration` Командлет просматривает каталог, указанный для любых "\<computername\>.mof» файлы. `Start-DSCConfiguration` Командлет пытается применить каждой «.mof» файл, найдет к computername, указанный в параметре filename («localhost», «server01», «dc-02", и т.д.).

> [!NOTE]
> Если `-Wait` параметр не указан, `Start-DSCConfiguration` создает фоновое задание для выполнения операции. Указание `-Verbose` позволяет наблюдать **Verbose** результаты операции. `-Wait`, и `-Verbose` — оба необязательные параметры.

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a>Тестирование конфигурации

Один раз `Start-DSCConfiguration` командлет будет завершена, вы увидите файл «HelloWorld.txt» в указанном месте. Можно проверить содержимое с [Get-Content](/powershell/module/microsoft.powershell.management/get-content) командлета.

Вы также можете *тестирования* текущее состояние с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).

Требуется «True», является ли узел в настоящее время соответствуют применяемой конфигурации.

```powershell
Test-DSCConfiguration
```

```output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a>Повторное применение конфигурации

Чтобы просмотреть конфигурацию применяться еще раз, можно удалить текстовый файл, созданный вашей конфигурации. Использование `Start-DSCConfiguration` командлет с `-UseExisting` параметра. `-UseExisting` Указывает `Start-DSCConfiguration` повторно применить файл «current.mof», который представляет наиболее недавно успешно применения конфигурации.

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a>Дальнейшие действия

- См. дополнительные сведения о [конфигурации DSC](configurations.md).
- См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).
- Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).
