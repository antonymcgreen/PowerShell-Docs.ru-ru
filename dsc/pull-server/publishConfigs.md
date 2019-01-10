---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Публикация опрашивающий сервер, используя идентификаторы конфигурации (v4/v5)
ms.openlocfilehash: 0144fec43d7a8d65b79891567cc0dc3952175343
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402400"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a>Публикация опрашивающий сервер, используя идентификаторы конфигурации (v4/v5)

В следующих разделах предполагается, что вы уже настроили опрашивающего сервера. Если ваш сервер на включение внесенных изменений не установлен, можно использовать со следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии. В этой статье показано, как передать ресурсы, чтобы они были доступны, которые требуется загрузить и настроить клиенты для загрузки ресурсов автоматически. Когда узел получает назначенной конфигурации, с помощью **на включение внесенных изменений** или **Push** (v5), он автоматически скачивает все ресурсы, требования конфигурации из местоположения, указанного в LCM.

## <a name="compile-configurations"></a>Компилировать конфигурации

Первым шагом к хранению [конфигураций](../configurations/configurations.md) на опрашивающем сервере — скомпилировать их в MOF-файлы. Чтобы сделать конфигурацию универсальных и применимые на большее количество клиентов, используйте `localhost` в блок узла. В приведенном ниже примере показано оболочку настройки, который использует `localhost` вместо имени конкретного клиента.

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

После компиляции конфигурацию универсального должны иметь файл «localhost.mof».

## <a name="renaming-the-mof-file"></a>Переименование MOF-файл

Можно хранить «MOF-файлы конфигурации на опрашивающем сервере с **ConfigurationName** или **ConfigurationID**. В зависимости от того, как вы планируете настроить клиенты на включение внесенных изменений можно выбрать раздел для должным образом переименовать ваш скомпилированный MOF-файлы.

### <a name="configuration-ids-guid"></a>Конфигурация идентификаторы (GUID)

Необходимо будет переименовать файл «localhost.mof» для "<GUID>.mof» файла. Можно создать случайный **Guid** в примере ниже, или с помощью [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) командлета.

```powershell
[System.Guid]::NewGuid()
```

Пример вывода

```output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

Затем можно ввести имя файла «.mof» любым приемлемым способом. В примере ниже используется [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) командлета.

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

Дополнительные сведения об использовании **идентификаторы GUID** в вашей среде, см. в разделе [планирование идентификаторы GUID](/powershell/dsc/secureserver#guids).

### <a name="configuration-names"></a>Имена параметров конфигурации

Необходимо будет переименовать файл «localhost.mof» для "<Configuration Name>.mof» файла. В следующем примере используется имя конфигурации из предыдущего раздела. Затем можно ввести имя файла «.mof» любым приемлемым способом. В примере ниже используется [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) командлета.

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a>Создать контрольную сумму

Каждый файл «.mof» хранятся на опрашивающий сервер или общий ресурс SMB должен быть файлом связанный «.checksum». Этот файл позволяет клиентам узнать, когда связанный MOF «-» файл был изменен и должен загружаться снова.

Можно создать **контрольной суммы** с [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) командлета. Можно также запустить `New-DSCCheckSum` от каталога с файлами с помощью `-Path` параметра. Если контрольная сумма уже существует, можно будет применить его повторного создания с `-Force` параметра. В следующем примере указан каталог, содержащий файл «.mof» из предыдущего раздела и использует `-Force` параметра.

```powershell
New-DscChecksum -Path '.\' -Force
```

Выходные данные не отображаются, но теперь вы увидите "<GUID or Configuration Name>. mof.checksum» файла.

## <a name="where-to-store-mof-files-and-checksums"></a>Где хранить файлы MOF и контрольные суммы

### <a name="on-a-dsc-http-pull-server"></a>На HTTP опрашивающего сервера DSC

При настройке сервера по запросу HTTP, как описано в [Настройка опрашивающего сервера DSC HTTP](pullServer.md), укажите каталоги для **ModulePath** и **ConfigurationPath** ключи. **ConfigurationPath** ключ указывает, где должны храниться все MOF-файлы. **ConfigurationPath** указывает, где должны храниться все MOF-файлы и файлы «.checksum».

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a>В общем ресурсе SMB

При настройке опрашивающий клиент использовать общую папку SMB, укажите **ConfigurationRepositoryShare**. Все MOF-файлы и файлы «.checksum» следует хранить в **SourcePath** каталог из **ConfigurationRepositoryShare** блока.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a>Дальнейшие действия

Далее необходимо настроить на клиентах по запросу на включение внесенных изменений указанной конфигурации. Дополнительные сведения см. в одном из следующих руководств:

- [Настройте опрашивающий клиент, используя идентификаторы конфигурации (версия 4)](pullClientConfigId4.md)
- [Настройте опрашивающий клиент, используя идентификаторы конфигурации (v5)](pullClientConfigId.md)
- [Настройка клиента на включение внесенных изменений с помощью имен конфигураций (v5)](pullClientConfigNames.md)

## <a name="see-also"></a>См. также:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)
- [Пакет и ресурсы передачи к опрашивающему серверу](package-upload-resources.md)
