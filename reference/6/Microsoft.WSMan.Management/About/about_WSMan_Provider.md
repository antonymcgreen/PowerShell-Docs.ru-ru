---
description: WSMan
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WSMan Provider
ms.openlocfilehash: 011383112d453a4fa88745c69b52e432709aa9d3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231178"
---
# <a name="wsman-provider"></a>WSMan Provider

## <a name="provider-name"></a>Имя поставщика

WSMan

## <a name="drives"></a>Диски

`WSMan:`

## <a name="short-description"></a>Краткое описание

Обеспечивает доступ к конфигурационной информации веб-служб WS-Management.

## <a name="detailed-description"></a>Подробное описание

Поставщик **WSMan** для PowerShell позволяет добавлять, изменять, очищать и удалять WS-Management данные конфигурации на локальных и удаленных компьютерах.

Поставщик **WSMan** предоставляет диск PowerShell со структурой каталогов, соответствующей логической группировке параметров конфигурации WS-Management. Эти группы называются контейнерами.

Начиная с Windows PowerShell 3,0, поставщик **WSMan** был обновлен для поддержки новых свойств конфигураций сеансов, таких как **аутпутбуфферингмоде**. Конфигурации сеансов отображаются как элементы в каталоге подключаемого модуля `WSMan:` диска, и свойства отображаются в виде элементов в каждой конфигурации сеанса.

Поставщик **WSMan** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> `WSMan:`Для изменения значений новых свойств можно использовать команды на диске. Однако вы не можете использовать `WSMan:` диск в PowerShell 2,0, чтобы изменить свойства, появившиеся в Windows PowerShell 3,0.
> Несмотря на то, что ошибки не возникают, команды не могут изменить эти параметры, используйте диск **WSMan** в Windows PowerShell 3,0.

### <a name="organization-of-the-wsman-drive"></a>Организация диска WSMan:

- **Клиент**. можно настроить различные аспекты клиента WS-Management. Сведения о конфигурации сохраняются в реестре.

- **Служба**. можно настроить различные аспекты службы WS-Management.
  Сведения о конфигурации сохраняются в реестре.
  > [!NOTE]
  > Конфигурация службы иногда называется конфигурацией сервера.

- **Shell** : можно настроить различные аспекты оболочки WS-Management, такие как параметр, разрешающий доступ к удаленной оболочке ( **алловремотешеллакцесс** ), и максимальное разрешенное число пользователей ( **максконкуррентусерс** ).

- **Прослушиватель**. Вы можете создать и настроить прослушиватель. Прослушиватель — это служба управления, реализующая протокол WS-Management для отправки и получения сообщений.

- **Подключаемый модуль**. подключаемые модули загружаются и используются службой WS-Management для предоставления различных функций. По умолчанию PowerShell предоставляет три подключаемых модуля:
  - Подключаемый модуль пересылки событий.
  - Подключаемый модуль Microsoft. PowerShell.
  - Подключаемый модуль поставщика инструментарий управления Windows (WMI) (WMI).
  Эти три подключаемые модули поддерживают пересылку событий, конфигурацию и доступ к WMI.

- **Clientcertificate**. Вы можете создать и настроить сертификат клиента.
  Сертификат клиента применяется в том случае, если клиент WS-Management настроен для использования проверки подлинности сертификата.

### <a name="directory-hierarchy-of-the-wsman-provider"></a>Иерархия каталогов поставщика WSMan

Иерархия каталогов поставщика WSMan для локального компьютера выглядит следующим образом.

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

Иерархия каталогов поставщика WS-Management для удаленного компьютера аналогична иерархии каталогов для локального компьютера. Однако для доступа к параметрам конфигурации удаленного компьютера необходимо установить подключение к удаленному компьютеру с помощью командлета [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan). После установления подключения к удаленному компьютеру имя удаленного компьютера появляется в поставщике.

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a>Навигация по диску WSMan:

Эта команда использует `Set-Location` командлет для изменения текущего расположения на `WSMan:` диск.

```powershell
Set-Location WSMan:
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите.

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a>Переход к расположению удаленного системного хранилища

Эта команда использует `Set-Location` команду, чтобы изменить текущее расположение на корневое расположение в расположении удаленного хранилища системы. Используйте обратную косую черту или косую `\` черту, `/` чтобы указать уровень `WSMan:` диска.

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> Приведенная выше команда предполагает наличие подключения к удаленному компьютеру.

## <a name="displaying-the-contents-of-the-wsman-drive"></a>Отображение содержимого диска WSMan:

Эта команда использует `Get-Childitem` командлет для вывода хранилищ WS-Management в расположении хранилища localhost.

```powershell
Get-ChildItem -path WSMan:\Localhost
```

Если вы используете `WSMan:` диск, можно опустить имя диска.

Эта команда использует `Get-Childitem` командлет для показа WS-Management хранилищ в расположении хранилища на удаленном компьютере "Server01".

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> Приведенная выше команда предполагает наличие подключения к удаленному компьютеру.

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a>Установка значения элементов на диске WSMAN:

`Set-Item`С помощью командлета можно изменить параметры конфигурации на `WSMAN` диске. В следующем примере задается значение **TrustedHosts** , которое принимает все узлы с суффиксом "contoso.com".

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

`Set-Item`Командлет поддерживает дополнительный параметр `-Concatenate` , который добавляет значение вместо изменения. В следующем примере новое значение "*. domain2.com" добавляется к старому значению, хранящемуся в `TrustedHost:`

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a>Создание элементов на диске WSMAN:

### <a name="creating-a-new-listener"></a>Создание нового прослушивателя

`New-Item`Командлет создает элементы на диске поставщика. Каждый поставщик имеет различные типы элементов, которые можно создать. На `WSMAN:` диске можно создавать *прослушиватели* , настроенные для получения и реагирования на удаленные запросы. Следующая команда создает новый прослушиватель HTTP с помощью `New-Item` командлета.

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a>Создание нового подключаемого модуля

Эта команда создает (регистрирует) подключаемый модуль для службы WS-Management.

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a>Создание новой записи ресурса

Эта команда создает запись ресурса в каталоге Resources объекта Тестплугин. Эта команда предполагает, что Тестплугин был создан с помощью отдельной команды.

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a>Создание новой записи безопасности для ресурса

Эта команда создает запись безопасности в каталоге Security ресурса Resource_5967683 (конкретного ресурса). Эта команда предполагает, что запись ресурса была создана с помощью отдельной команды.

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a>Создание нового сертификата клиента

Эта команда создает запись **clientcertificate** , которая может использоваться клиентом WS-Management. Новый **clientcertificate** будет отображаться в каталоге **ClientCertificate** как "ClientCertificate_1234567890". Все параметры являются обязательными. **Издатель** должен быть отпечаткой сертификата издателя.

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a>Создание нового параметра инициализации

Эта команда создает параметр инициализации с именем "тестпараметернаме" в каталоге "Инитиализатионпараметерс". Эта команда предполагает, что "Тестплугин" был создан с помощью отдельной команды.

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.

### <a name="address-string"></a>Address \<String\>

Задает адрес, для которого был создан данный прослушиватель. Он может иметь одно из следующих значений:

- Строка литерала "*". (Подстановочный знак ( `*` ) делает команду привязать все IP-адреса ко всем сетевым адаптерам.)
- Строка литерала "IP:", за которой следует допустимый IP-адрес в точечно-десятичном формате IPv4 или в шестнадцатеричном формате IPv6.
- Строка литерала "MAC:", за которой следует MAC-адрес адаптера.
  Например: MAC: 32-a3-58 -90-to-CC.

> [!NOTE]
> Значение параметра Address задается при создании прослушивателя.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a>Capability \<Enumeration\>

При работе с *подключаемыми модулями* этот параметр указывает операцию, которая поддерживается для этого универсального кода ресурса (URI). Необходимо создать по одной записи для каждого типа операций, поддерживаемого URI. Можно указать любые допустимые атрибуты для данной операции, если она поддерживается операцией.

Эти атрибуты включают **SupportsFiltering имеет** и **суппортсфрагмент**.

- **CREATE** : операции создания поддерживаются в URI.
  - Атрибут **суппортфрагмент**  используется, если операция создания поддерживает концепцию.
  - Атрибут **суппортфилтеринг** недопустим для операций создания и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- **Delete** : операции Delete поддерживаются в URI.
  - Атрибут **суппортфрагмент** используется, если операция удаления поддерживает концепцию.
  - Атрибут **суппортфилтеринг** недопустим для операций DELETE и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- **Перечисление**. операции перечисления поддерживаются в URI.
  - Атрибут **СУППОРТФРАГМЕНТ** не поддерживается для операций перечисления и должен иметь значение false.
  - Атрибут **суппортфилтеринг** является допустимым, и если подключаемый модуль поддерживает фильтрацию, этот атрибут должен иметь значение true.
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- **Get** : операции Get поддерживаются в URI.
  - Атрибут **суппортфрагмент** используется, если операция get поддерживает концепцию.
  - Атрибут **суппортфилтеринг** недопустим для операций Get и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- **Invoke** : операции Invoke поддерживаются в URI.
  - Атрибут **суппортфрагмент** не поддерживается для операций Invoke и должен иметь значение false.
  - Атрибут **суппортфилтеринг** является недопустимым и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- Операция **размещения** : операции размещения поддерживаются в URI.
  - Атрибут **суппортфрагмент** используется, если операция размещения поддерживает концепцию.
  - Атрибут **суппортфилтеринг** недопустим для операций размещения и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- **Subscribe** : операции подписки поддерживаются в URI.
  - Атрибут **суппортфрагмент** не поддерживается для операций подписки и должен иметь значение false.
  - Атрибут **суппортфилтеринг** недопустим для операций Subscribe и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если поддерживаются операции Shell.
- **Shell** : операции оболочки поддерживаются в URI.
  - Атрибут **суппортфрагмент** не поддерживается для операций оболочки и должен иметь значение "false".
  - Атрибут **суппортфилтеринг** недопустим для операций оболочки и должен иметь значение "false".
  > [!NOTE]
  > Эта операция недопустима для URI, если также поддерживается любая другая операция.
  > [!NOTE]
  > Если для URI настроена операция Shell, операции Get, Put, Create, Delete, Invoke и Enumerate обрабатываются в рамках службы WS-Management (WinRM) для управления оболочками. В результате подключаемый модуль не может обрабатывать операции.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a>CertificateThumbprint \<String\>

Указывает отпечаток сертификата службы.

Это значение представляет собой строку двузначных шестнадцатеричных значений в поле Thumbprint сертификата. Оно задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя с разрешением на выполнение этого действия. Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с локальными учетными записями пользователей и не работают с учетными записями доменов. Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` командлеты или на `Cert:` диске PowerShell.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a>Enabled \<Boolean\>

Указывает, включен или отключен прослушиватель. Значение по умолчанию равно True.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a>FileName (Plugin) \<String\>

Указывает имя файла подключаемого модуля операций. Все переменные среды, помещаемые в эту запись, будут развернуты в контексте пользователей при получении запроса. Так как каждый пользователь может иметь другую версию одной и той же переменной среды, у каждого пользователя может быть другой подключаемый модуль. Эта запись не может быть пустой и должна указывать на допустимый подключаемый модуль.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a>HostName \<String\>

Указывает имя компьютера, на котором выполняется служба WS-Management (WinRM).

Значением должно быть полное доменное имя, символьная строка IPv4 или IPv6 или подстановочный знак.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a>Issuer \<String\>

Задает имя центра сертификации, выдавшего сертификат.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a>\<\>Подключаемые модули WS-Management подключаемых модулей — это собственные библиотеки динамической компоновки (DLL)

который подключается к и расширяет функциональные возможности WS-Management. Интерфейс API подключаемого модуля WSW-Management предоставляет функции, позволяющие пользователю создавать подключаемые модули, реализуя определенные API для поддерживаемых URI и операций с ресурсами. После настройки подключаемых модулей под службу WS-Management (WinRM) или службы IIS подключаемые модули загружаются на узел WS-Management или узел служб IIS соответственно. Удаленные запросы передаются входным точкам этих подключаемых модулей для выполнения операций.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a>Port \<Unsigned Short Integer\>

Задает TCP-порт, для которого создается данный прослушиватель. Можно указать любое значение от 1 до 65535.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a>Resource \<String\>

Задает конечную точку, которая представляет определенный тип операции управления или значение. Служба предоставляет один или несколько ресурсов, и некоторые ресурсы могут иметь более одного экземпляра. Ресурс управления сходен с классом WMI или с таблицей базы данных, а экземпляр сходен с экземпляром класса или со строкой в таблице. Например, класс **Win32_LogicalDisk** представляет ресурс. `Win32_LogicalDisk="C:\\"` — Это конкретный экземпляр ресурса.

URI состоит из префикса и пути к ресурсу.
Пример:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a>Resource \<String\>

Задает универсальный идентификатор ресурса (URI), который идентифицирует конкретный тип ресурса, например диск или процесс, на компьютере.

URI состоит из префикса и пути к ресурсу. Пример:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a>SDKVersion \<String\>

Указывает версию пакета SDK подключаемого модуля WS-Management. Единственное допустимое значение:
1.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a>Subject \<String\>

Задает сущность, которая идентифицируется с помощью сертификата.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a>Transport \<String\>

Указывает транспорт для отправки и получения запросов и ответов протокола WS-Management. Значением должен быть протокол HTTP или HTTPS.

Примечание. значение транспорта задается при создании прослушивателя.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a>URI \<String\>

Определяет URI, доступ к которому авторизуется на основании значения параметра.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a>URLPrefix \<String\>

Префикс URL-адреса для получения HTTP- или HTTPS-запросов. Это строка, содержащая только символы `[a-z]` , `[A-Z]` ,, символы `[9-0]` подчеркивания ( `_` ) и обратную косую черту ( `/` ). Строка не должна начинаться с или заканчиваться обратной косой чертой ( `/` ). Например, если имя компьютера — "Самплекомпутер", клиент WS-Management будет указывать `http://SampleMachine/URLPrefix` в адресе назначения.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a>Value \<String\>

Задает значение параметра инициализации, которое является специфичным для подключаемого модуля и используется для указания параметров конфигурации.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a>XMLRenderingType \<String\>

Указывает формат, в котором XML передается подключаемым модулям через объект **WSMAN_DATA** . Допустимыми значениями являются:

- Text: входящие XML-данные содержатся в структуре **WSMAN_DATA_TYPE_TEXT** , которая представляет XML в качестве буфера памяти **пквстр** .
- XMLReader: входящие XML-данные содержатся в структуре **WSMAN_DATA_TYPE_WS_XML_READER** , которая представляет XML как объект **XmlReader** , который определен в файле заголовка "WebService. h".

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a>Использование конвейера

Командлеты поставщика принимают входные данные конвейера. Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.
Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.

## <a name="getting-help"></a>Получение справки

Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.

Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a>См. также статью

[about_Providers](../../Microsoft.PowerShell.Core/About/about_Providers.md)
