---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Пакет и ресурсы передачи к опрашивающему серверу
ms.openlocfilehash: 29a62f96393a53c9e7da57a5e51732dcb0937194
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402299"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a>Пакет и ресурсы передачи к опрашивающему серверу

В следующих разделах предполагается, что вы уже настроили опрашивающего сервера. Если ваш сервер на включение внесенных изменений не установлен, можно использовать со следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии. В этой статье показано, как передать ресурсы, чтобы они были доступны, которые требуется загрузить и настроить клиенты для загрузки ресурсов автоматически. Когда узел получает назначенной конфигурации, с помощью **на включение внесенных изменений** или **Push** (v5), он автоматически скачивает все ресурсы, требования конфигурации из местоположения, указанного в LCM.

## <a name="package-resource-modules"></a>Модули ресурсов пакета

Каждый ресурс, доступный для клиента для загрузки должен храниться в файл «ZIP». В приведенном ниже примере отображается с помощью действия, необходимые [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) ресурсов.

> [!NOTE]
> При наличии любых клиентов, с помощью PowerShell 4.0, будет необходимо flaten структуру папки ресурсов и удалите все версии папки. Дополнительные сведения см. в разделе [нескольких версий ресурса](../configurations/import-dscresource.md#multiple-resource-versions).

Каталог ресурсов, с помощью любой служебной программы, скрипт или метод, который вы предпочитаете, можно сжать. В Windows, вы можете *щелкните правой кнопкой мыши* каталог «xPSDesiredStateConfiguration», и выберите «Отправить», а затем «Сжатую папку».

![Щелчок правой кнопкой мыши](../media/right-click.gif)

### <a name="naming-the-resource-archive"></a>Именование ресурсов архива

Архив ресурса должен иметь имя в следующем формате:

```
{ModuleName}_{Version}.zip
```

В приведенном выше примере «xPSDesiredStateConfiguration.zip» должен быть переименован «xPSDesiredStateConfiguration_8.4.4.0.zip».

### <a name="create-checksums"></a>Создание контрольных сумм

После модуля ресурсов были сжаты и переименован, необходимо создать **контрольной суммы**.  **Контрольной суммы** используется, LCM на клиенте, чтобы определить, если ресурс был изменен и должен быть загружен снова. Можно создать **контрольной суммы** с [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) командлет, как показано в следующем примере.

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

Выходные данные не отображаются, но теперь вы увидите «xPSDesiredStateConfiguration_8.4.4.0.zip.checksum». Можно также запустить `New-DSCCheckSum` от каталога с файлами с помощью `-Path` параметра. Если контрольная сумма уже существует, можно будет применить его повторного создания с `-Force` параметра.

### <a name="where-to-store-resource-archives"></a>Где хранить архивы ресурсов

#### <a name="on-a-dsc-http-pull-server"></a>На HTTP опрашивающего сервера DSC

При настройке сервера по запросу HTTP, как описано в [Настройка опрашивающего сервера DSC HTTP](pullServer.md), укажите каталоги для **ModulePath** и **ConfigurationPath** ключи. **ConfigurationPath** ключ указывает, где должны храниться все MOF-файлы. **ModulePath** указывает, где должно храниться модули ресурсов DSC.

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a>В общем ресурсе SMB

Если вы указали **ResourceRepositoryShare**, при настройке клиента на включение внесенных изменений, хранить архивы и контрольные суммы в **SourcePath** каталог из **ResourceRepositoryShare** блока.

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

Если вы указали только **ConfigurationRepositoryShare**, при настройке клиента на включение внесенных изменений, хранить архивы и контрольные суммы в **SourcePath** каталог из  **ConfigurationRepositoryShare** блока.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a>Обновление ресурсов

Вы можете принудительно узла для обновления ресурсов путем изменения номера версии в имя архива или путем создания новой контрольной суммы. Опрашивающий клиент будет проверять наличие новых версий из необходимых ресурсов, а также обновляется контрольные суммы, в том случае, когда обновляет его LCM.

## <a name="see-also"></a>См. также:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)
