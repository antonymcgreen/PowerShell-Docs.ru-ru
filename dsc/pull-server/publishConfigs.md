---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)
ms.openlocfilehash: 0144fec43d7a8d65b79891567cc0dc3952175343
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62079512"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a>Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)

В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер. Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии. В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически. Когда Узел получает назначенную конфигурацию с помощью команды **получить** или **отправить** (v5), он автоматически загружает любые ресурсы, требуемые конфигурацией, из расположения, указанного в LCM.

## <a name="compile-configurations"></a>Скомпилированные конфигурации

Первый шаг к сохранению [конфигураций](../configurations/configurations.md) на опрашиваемом сервере — скомпилировать их в MOF-файлы. Чтобы сделать конфигурацию универсальной и применимой к большему количеству клиентов, используйте `localhost` в блоке узла. В приведенном ниже примере показана оболочка конфигурации, которая использует `localhost` вместо имени конкретного клиента.

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

После компиляции универсальной конфигурации вы должны получить файл localhost.mof.

## <a name="renaming-the-mof-file"></a>Переименование MOF-файла

Конфигурации MOF-файлов можно хранить на опрашиваемом сервере по параметру **ConfigurationName** или **ConfigurationID**. В зависимости от того, как планируется настроить клиенты на прием, можно выбрать раздел ниже, чтобы корректно переименовать скомпилированные MOF-файлы.

### <a name="configuration-ids-guid"></a>Идентификаторы конфигурации (GUID)

Необходимо будет переименовать файл localhost.mof на <GUID>.mof. Можно создать случайный **GUID** в примере ниже или с помощью командлета [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).

```powershell
[System.Guid]::NewGuid()
```

Пример вывода

```output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

Затем можно переименовать MOF-файл любым приемлемым способом. В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

Дополнительные сведения об использовании **идентификаторов GUID** в вашей среде см. в разделе [Планирование для идентификаторов GUID](/powershell/dsc/secureserver#guids).

### <a name="configuration-names"></a>Имена параметров конфигурации

Необходимо будет переименовать файл localhost.mof на <Configuration Name>.mof. В следующем примере используется имя конфигурации из предыдущего раздела. Затем можно переименовать MOF-файл любым приемлемым способом. В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a>Создание контрольной суммы

Каждый MOF-файл хранится на опрашиваемом сервере или в общей папке SMB, чтобы иметь связанный файл CHECKSUM. Этот файл позволяет клиентам узнать, что связанный MOF-файл был изменен и должен быть загружен снова.

Вы можете создать **контрольную сумму** с помощью командлета [New-DscChecksum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum). Можно также запустить `New-DSCCheckSum` для каталога файлов с помощью параметра `-Path`. Если контрольная сумма уже существует, вы можете принудительно создать ее заново с помощью параметра `-Force`. В следующем примере указан каталог, содержащий MOF-файл из предыдущего раздела и использующий параметр `-Force`.

```powershell
New-DscChecksum -Path '.\' -Force
```

Вывод не будет показан, но теперь вы должны увидеть файл <GUID or Configuration Name>.mof.checksum.

## <a name="where-to-store-mof-files-and-checksums"></a>Где хранить MOF-файлы и контрольные суммы

### <a name="on-a-dsc-http-pull-server"></a>На опрашиваемом HTTP-сервере DSC

Когда вы настраиваете опрашиваемый HTTP-сервер, как описано в статье [Опрашивающая служба Desired State Configuration](pullServer.md), вы указываете ключи для **ModulePath** и **ConfigurationPath**. Ключ **ConfigurationPath** указывает, где должны храниться все MOF-файлы. Ключ **ConfigurationPath** указывает, где должны храниться все MOF-файлы и файлы CHECKSUM.

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

При настройке опрашивающего клиента для использования общей папки SMB укажите **ConfigurationRepositoryShare**. Все MOF-файлы и файлы CHECKSUM следует хранить в каталоге **SourcePath** из блока **ConfigurationRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a>Дальнейшие действия

Далее необходимо настроить опрашивающий клиент, чтобы получить конкретные конфигурации. Дополнительные сведения см. в следующих руководствах.

- [Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0](pullClientConfigId4.md)
- [Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше](pullClientConfigId.md)
- [Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше](pullClientConfigNames.md)

## <a name="see-also"></a>См. также:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)
- [Упаковка и передача ресурсов на опрашиваемый сервер](package-upload-resources.md)
