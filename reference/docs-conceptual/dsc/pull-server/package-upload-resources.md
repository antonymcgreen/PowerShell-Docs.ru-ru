---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Упаковка и передача ресурсов на опрашиваемый сервер
ms.openlocfilehash: 29a62f96393a53c9e7da57a5e51732dcb0937194
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954381"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a>Упаковка и передача ресурсов на опрашиваемый сервер

В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер. Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии. В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически. Когда Узел получает назначенную конфигурацию с помощью команды **получить** или **отправить** (v5), он автоматически загружает любые ресурсы, требуемые конфигурацией, из расположения, указанного в LCM.

## <a name="package-resource-modules"></a>Модули ресурса Package

Каждый ресурс, доступный пользователю для загрузки, должен храниться в ZIP-файле. В приведенном ниже примере показаны необходимые шаги с использованием ресурса [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0).

> [!NOTE]
> Если у вас есть клиенты, использующие PowerShell 4.0, вам потребуется расширить структуру папок ресурсов и удалить все папки версий. Дополнительные сведения см. в разделе [Несколько версий ресурса](../configurations/import-dscresource.md#multiple-resource-versions).

Вы можете сжать каталог ресурсов, используя любую программу, сценарий или метод. В Windows вы можете *щелкнуть правой кнопкой мыши* каталог xPSDesiredStateConfiguration и выбрать "Отправить", а затем "Сжатая папка".

![Щелчок правой кнопкой мыши](../media/right-click.gif)

### <a name="naming-the-resource-archive"></a>Именование ресурса Archive

Ресурс Archive должен иметь имя в следующем формате.

```
{ModuleName}_{Version}.zip
```

В приведенном выше примере xPSDesiredStateConfiguration.zip необходимо переименовать в xPSDesiredStateConfiguration_8.4.4.0.zip.

### <a name="create-checksums"></a>Создание контрольных сумм

После сжатия и переименования модуля Resource вам необходимо создать **контрольную сумму**.  **Контрольная сумма** используется LCM на клиенте, чтобы определить, был ли изменен ресурс и нужно ли его загрузить снова. Вы можете создать **контрольную сумму** с помощью командлета [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum), как показано в примере ниже.

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

Выходные данные не отображаются, но вы увидите xPSDesiredStateConfiguration_8.4.4.0.zip.checksum. Можно также запустить `New-DSCCheckSum` для каталога файлов с помощью параметра `-Path`. Если контрольная сумма уже существует, вы можете принудительно создать ее заново с помощью параметра `-Force`.

### <a name="where-to-store-resource-archives"></a>Где хранить ресурсы Archive

#### <a name="on-a-dsc-http-pull-server"></a>На опрашиваемом HTTP-сервере DSC

Когда вы настраиваете опрашиваемый HTTP-сервер, как описано в статье [Опрашивающая служба Desired State Configuration](pullServer.md), вы указываете ключи для **ModulePath** и **ConfigurationPath**. Ключ **ConfigurationPath** указывает, где должны храниться все MOF-файлы. **ModulePath** указывает, где должны храниться модули ресурсов DSC.

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a>В общей папке SMB

Если при настройке своего клиента — получателя данных вы указали **ResourceRepositoryShare**, храните архивы и контрольные суммы в каталоге **SourcePath** в блоке **ResourceRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

Если при настройке своего клиента — получателя данных вы указали только **ConfigurationRepositoryShare**, храните архивы и контрольные суммы в каталоге **SourcePath** в блоке **ConfigurationRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a>Обновление ресурсов

Вы можете заставить узел обновлять свои ресурсы, изменив номер версии в имени архива или создав новую контрольную сумму. Клиент — получатель данных будет проверять наличие новых версий из необходимых ресурсов, а также обновлять контрольные суммы при обновлении его LCM.

## <a name="see-also"></a>См. также:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)
