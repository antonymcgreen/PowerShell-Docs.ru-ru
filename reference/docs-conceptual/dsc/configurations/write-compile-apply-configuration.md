---
ms.date: 12/12/2018
keywords: dsc,powershell,настройка,служба,установка
title: Создание, компиляция и применение конфигурации
ms.openlocfilehash: eb61e518762b9f13e617ecd4711bfef7a86814ec
ms.sourcegitcommit: ea7d87a7a56f368e3175219686dfa2870053c644
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818164"
---
> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

# <a name="write-compile-and-apply-a-configuration"></a>Создание, компиляция и применение конфигурации

В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).
В следующем примере вы узнаете, как написать и применить очень простую конфигурацию. Конфигурация будет гарантировать, что файл "HelloWorld.txt" существует на локальном компьютере. В случае удаления файла DSC будет создавать его заново при очередном обновлении.

См. дополнительные сведения об особенностях работы с DSC в [обзоре платформы Desired State Configuration для разработчиков](../overview/overview.md).

## <a name="requirements"></a>Требования

Для выполнения этого примера вам понадобится компьютер с PowerShell 4.0 или более поздней версии.

## <a name="write-the-configuration"></a>Запись конфигурации

[Конфигурация](configurations.md) DSC — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).

В интегрированной среде сценариев PowerShell или другом редакторе PowerShell введите следующее:

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

> Важно! В более сложных сценариях, когда нужно импортировать несколько модулей, чтобы работать с множеством ресурсов DSC в одной конфигурации, обязательно помещайте каждый модуль в отдельную строку с помощью `Import-DscResource`.
> Такое поведение проще поддерживать в системе управления версиями. Оно требуется при работе с DSC в Azure State Configuration.
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

Сохраните файл как "HelloWorld.ps1".

Определение конфигурации аналогично определению функции. Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.

Конфигурация вызывает один элемент [resources](../resources/resources.md), а именно ресурс `File`. Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.

## <a name="compile-the-configuration"></a>Компиляция конфигурации

Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.
Выполнение конфигурации, как и функции, скомпилирует один MOF-файл для каждого узла, определенного в блоке `Node`.
Чтобы запустить конфигурацию, необходимо *ввести по префиксу-точке* скрипт "HelloWorld.ps1" в текущей области.
Дополнительные сведения см. в статье [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).

<!-- markdownlint-disable MD038 -->
*Введите по префиксу-точке* скрипт "HelloWorld.ps1", указав путь, где вы сохранили его, после `. ` (точка, пробел). Затем можно запустить конфигурацию, вызвав ее как функцию.
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
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

Командлет `Start-DscConfiguration` сообщает [локальному диспетчеру конфигураций (LCM)](../managing-nodes/metaConfig.md) (ядру DSC) о необходимости применить конфигурацию.
LCM вызывает ресурсы DSC для применения конфигурации.

Используйте приведенный ниже код для выполнения командлета `Start-DSCConfiguration`. Укажите путь к каталогу, где хранится "localhost.mof", в параметре `-Path`. Командлет `Start-DSCConfiguration` просматривает каталог, указанный для любых файлов вида "\<имя компьютера\>.mof". Командлет `Start-DSCConfiguration` пытается применить каждый MOF-файл, который найдет, к компьютеру, указанному в имени файла ("localhost", "server01", "dc-02" и т. д.).

> [!NOTE]
> Если параметр `-Wait` не указан, `Start-DSCConfiguration` создает фоновое задание для выполнения операции. Указание параметра `-Verbose` позволяет наблюдать **подробные** результаты операции. И `-Wait`, и `-Verbose` — необязательные параметры.

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a>Тестирование конфигурации

Когда командлет `Start-DSCConfiguration` будет завершен, вы увидите файл "HelloWorld.txt" в указанном месте. Можно проверить его содержимое с помощью командлета [Get-Content](/powershell/module/microsoft.powershell.management/get-content).

Вы также можете *протестировать* текущее состояние с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).

Результат должен быть равен "True", если узел в настоящее время соответствует применяемой конфигурации.

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

Чтобы повторно применить конфигурацию, можно удалить текстовый файл, созданный вашей конфигурацией. Затем используйте командлет `Start-DSCConfiguration` с параметром `-UseExisting`. Параметр `-UseExisting` указывает `Start-DSCConfiguration` повторно применить файл "current.mof", который представляет последнюю успешно примененную конфигурацию.

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a>Дальнейшие действия

- См. дополнительные сведения о [конфигурации DSC](configurations.md).
- См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).
- Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).
