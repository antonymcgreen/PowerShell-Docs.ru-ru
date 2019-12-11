---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)
ms.openlocfilehash: 3b094308338e62c783b19f4d3bb41634feee63f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417259"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a>Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)

В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер. Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии. В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически. Когда узел получает назначенную конфигурацию с помощью команды **Pull** или **Push** (версия 5), он автоматически загружает любые ресурсы, требуемые для конфигурации, из расположения, указанного в локальном диспетчере конфигураций (LCM)

## <a name="compile-configurations"></a>Компиляция конфигураций

Первый шаг к сохранению [конфигураций](../configurations/configurations.md) на опрашиваемом сервере — скомпилировать их в файлы `.mof`. Чтобы сделать конфигурацию универсальной и применимой к большему количеству клиентов, используйте `localhost` в блоке узла. В приведенном ниже примере показана оболочка конфигурации, которая использует `localhost` вместо имени конкретного клиента.

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

После компиляции универсальной конфигурации вы должны получить файл `localhost.mof`.

## <a name="renaming-the-mof-file"></a>Переименование MOF-файла

Конфигурации файлов `.mof` можно хранить на опрашиваемом сервере, указывая параметр **ConfigurationName** или **ConfigurationID**. В зависимости от того, как вы планируете настроить опрашиваемые клиенты, можно выбрать раздел ниже, чтобы корректно переименовать скомпилированные файлы `.mof`.

### <a name="configuration-ids-guid"></a>Идентификаторы конфигурации (GUID)

Вам потребуется переименовать файл `localhost.mof` в `<GUID>.mof`. Можно создать случайный **GUID** в примере ниже или с помощью командлета [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).

```powershell
[System.Guid]::NewGuid()
```

Пример вывода

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

Затем можно переименовать файл `.mof` любым приемлемым способом. В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

Дополнительные сведения об использовании **идентификаторов GUID** в вашей среде см. в разделе [Планирование для идентификаторов GUID](/powershell/scripting/dsc/secureserver#guids).

### <a name="configuration-names"></a>Имена файлов конфигурации

Вам потребуется переименовать файл `localhost.mof` в `<Configuration Name>.mof`. В следующем примере используется имя конфигурации из предыдущего раздела. Затем можно переименовать файл `.mof` любым приемлемым способом. В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a>Создание контрольной суммы

С каждым файлом `.mof`, который хранится на опрашиваемом сервере или в общей папке SMB, должен быть связан файл `.checksum`.
Этот файл позволяет клиентам узнать, что связанный файл `.mof` был изменен и должен быть загружен снова.

Вы можете создать **контрольную сумму** с помощью командлета [New-DscChecksum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum). Можно также запустить `New-DSCCheckSum` для каталога файлов с помощью параметра `-Path`.
Если контрольная сумма уже существует, вы можете принудительно создать ее заново с помощью параметра `-Force`. В следующем примере указан каталог, которые содержит файл `.mof` из предыдущего раздела, и используется параметр `-Force`.

```powershell
New-DscChecksum -Path '.\' -Force
```

Выходные данные не будут отображаться, но теперь должен отобразиться файл `<GUID or Configuration Name>.mof.checksum`.

## <a name="where-to-store-mof-files-and-checksums"></a>Где хранить MOF-файлы и контрольные суммы

### <a name="on-a-dsc-http-pull-server"></a>На опрашиваемом HTTP-сервере DSC

Когда вы настраиваете опрашиваемый HTTP-сервер, как описано в статье [Опрашивающая служба Desired State Configuration](pullServer.md), вы указываете ключи для **ModulePath** и **ConfigurationPath**. Ключ **ModulePath** указывает, где должны храниться упакованные файлы модуля `.zip`. Ключ **ConfigurationPath** указывает, где должны храниться все файлы `.mof` и файлы `.checksum`.

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a>В общей папке SMB

При настройке опрашивающего клиента для использования общей папки SMB укажите **ConfigurationRepositoryShare**.
Все файлы `.mof` и файлы `.checksum` следует хранить в каталоге **SourcePath** из блока **ConfigurationRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a>Дальнейшие действия

Далее необходимо настроить опрашиваемый клиент, чтобы получить конкретную конфигурацию. Дополнительные сведения см. в следующих руководствах.

- [Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0](pullClientConfigId4.md)
- [Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше](pullClientConfigId.md)
- [Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше](pullClientConfigNames.md)

## <a name="see-also"></a>См. также:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)
- [Упаковка и передача ресурсов на опрашиваемый сервер](package-upload-resources.md)
