---
description: Сертификат
keywords: powershell,командлет
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Поставщик Certificate
ms.openlocfilehash: b3ac701f18ba57d9108a76b7c478b8514075b3ee
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231654"
---
# <a name="certificate-provider"></a>Поставщик Certificate

## <a name="provider-name"></a>Имя поставщика

Сертификат

## <a name="drives"></a>Диски

`Cert:`

## <a name="capabilities"></a>Характеристики

**ShouldProcess**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к хранилищам сертификатов X. 509 и сертификатам в PowerShell.

## <a name="detailed-description"></a>Подробное описание

Поставщик **сертификатов** PowerShell позволяет получать, добавлять, изменять, очищать и удалять сертификаты и хранилища сертификатов в PowerShell.

Диск **сертификата** — это иерархическое пространство имен, содержащее хранилища сертификатов и сертификаты на компьютере.

Поставщик **сертификатов** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Диск сертификата предоставляет следующие типы.

- Расположения магазинов (Microsoft. PowerShell. Commands. X509StoreLocation) — это контейнеры высокого уровня, которые группируют сертификаты для текущего пользователя и для всех пользователей. В каждой системе существует расположение хранилищ CurrentUser и LocalMachine (все пользователи).

- Хранилища сертификатов (System. Security. Cryptography. X509Certificates. X509Store), которые являются физическими хранилищами, в которых сохраняются и управляются сертификаты.

- Сертификат x. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** , каждый из которых представляет сертификат X. 509 на компьютере.
  Сертификаты идентифицируются по их отпечаткам.

## <a name="navigating-the-certificate-drive"></a>Навигация по диску сертификатов

Поставщик **сертификата** предоставляет пространство имен сертификата `Cert:` в качестве диска в PowerShell. Эта команда использует `Set-Location` команду, чтобы изменить текущее расположение на корневое хранилище сертификатов в расположении хранилища LocalMachine. Используйте обратную косую черту ( \\ ) или косую черту (/), чтобы указать уровень `Cert:` диска.

```powershell
Set-Location Cert:
```

Вы также можете работать с поставщиком сертификата с любого другого диска PowerShell. Чтобы сослаться на псевдоним из другого расположения, используйте `Cert:` имя диска в пути.

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

Чтобы вернуться к диску файловой системы, введите имя диска. Например, введите:

```powershell
Set-Location C:
```

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).
> и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="displaying-the-contents-of-the-cert-drive"></a>Отображение содержимого диска Cert:

Эта команда использует `Get-ChildItem` командлет для вывода хранилищ сертификатов в расположении хранилища сертификатов CurrentUser.

Если вы не используете `Cert:` диск, используйте абсолютный путь.

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a>Отображение свойств сертификата на диске CERT:

Этот пример получает сертификат с `Get-Item` и сохраняет его в переменной.
В примере показаны новые свойства сценария сертификата ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) с помощью `Select-Object` .

```powershell
$c = Get-Item cert:\LocalMachine\My\52A149D0393CE8A8D4AF0B172ED667A9E3A1F44E
$c | Format-List DnsNameList, EnhancedKeyUsageList, SendAsTrustedIssuer
```

```output
DnsNameList          : {SERVER01.contoso.com}
EnhancedKeyUsageList : {WiFi-Machine (1.3.6.1.4.1.311.42.2.6),
                       Client Authentication (1.3.6.1.5.5.7.3.2)}
SendAsTrustedIssuer  : False
```

### <a name="find-all-codesigning-certificates"></a>Найти все сертификаты соразработки

Эта команда использует **CodeSigningCert** и **Рекурсивные** параметры `Get-ChildItem` командлета, чтобы получить все сертификаты на компьютере с центром подписывания кода.

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a>Поиск сертификатов с истекшим сроком действия

Эта команда использует параметр **ExpiringInDays** `Get-ChildItem` командлета для получения сертификатов, срок действия которых истекает в течение следующих 30 дней.

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a>Поиск SSL-сертификатов сервера

Эта команда использует параметр **SSLServerAuthentication** `Get-ChildItem` командлета для получения всех SSL-сертификатов сервера в хранилищах My и WebHost.

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a>Поиск сертификатов с истекшим сроком действия на удаленных компьютерах

Эта команда использует `Invoke-Command` командлет для выполнения `Get-ChildItem` команды на компьютерах SRV01 и Srv02. Нулевое значение (0) в параметре **ExpiringInDays** возвращает сертификаты на компьютерах SRV01 и Srv02, срок действия которых истек.

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a>Объединение фильтров для поиска определенного набора сертификатов

Эта команда возвращает все сертификаты в расположении хранилища LocalMachine, которые имеют следующие атрибуты:

- "Fabrikam" в своем DNS-имени
- "Проверка подлинности клиента" в EKU
- значение `$true` для свойства **SendAsTrustedIssuer**
- срок действия не истекает в течение следующих 30 дней.

Свойство **NotAfter** хранит дату окончания срока действия сертификата.

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a>Открытие оснастки "Сертификаты" консоли MMC

`Invoke-Item`Командлет будет использовать приложение по умолчанию, чтобы открыть указанный путь. Для сертификатов приложение по умолчанию — оснастка MMC "сертификаты".

Эта команда открывает оснастку "Сертификаты" MMC для управления указанным сертификатом.

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a>Копирование сертификатов

Копирование сертификатов не поддерживается поставщиком **сертификатов** . При попытке скопировать сертификат появляется сообщение об ошибке.

```
$path = "Cert:\LocalMachine\Root\E2C0F6662D3C569705B4B31FE2CBF3434094B254"
PS Cert:\LocalMachine\> Copy-Item -Path $path -Destination .\CA\
Copy-Item : Provider operation stopped because the provider does not support
this operation.
At line:1 char:1
+ Copy-Item -Path $path -Destination .\CA\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Copy-Item],
                              PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,
                              Microsoft.PowerShell.Commands.CopyItemCommand
```

## <a name="moving-certificates"></a>Перемещение сертификатов

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a>Перемещение всех сертификатов проверки подлинности сервера SSL в хранилище веб-узлов

Эта команда использует `Move-Item` командлет для перемещения сертификата из хранилища My в хранилище веб-узлов.

`Move-Item` не будет перемещать хранилища сертификатов и не будет переносить сертификаты в другое расположение, например переместить сертификат из хранилища LocalMachine в CurrentUser. `Move-Item`Командлет перемещает сертификаты, но не перемещает закрытые ключи.

Эта команда использует параметр **SSLServerAuthentication** `Get-ChildItem` командлета для получения сертификатов проверки подлинности сервера SSL в хранилище сертификатов My.

Возвращенные сертификаты передаются в `Move-Item` командлет, который перемещает сертификаты в хранилище WebHost.

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a>Удаление сертификатов и закрытых ключей

`Remove-Item`Командлет удалит указанные сертификаты. `-DeleteKey`Динамический параметр удаляет закрытый ключ.

### <a name="delete-a-certificate-from-the-ca-store"></a>Удаление сертификата из хранилища ЦС

Эта команда удаляет сертификат из хранилища сертификатов центра сертификации, но не затрагивает связанный закрытый ключ.

На `Cert:` диске `Remove-Item` командлет поддерживает только параметры **DeleteKey** , **path** , **WhatIf** и **Confirm** . Все остальные параметры игнорируются.

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a>Удаление сертификата с помощью подстановочных знаков в DNS-имени

Эта команда удаляет все сертификаты с именем DNS, содержащим "Fabrikam". **DNSName** `Get-ChildItem` Для получения сертификатов и `Remove-Item` командлета для их удаления используется параметр dnsName командлета.

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a>Удаление закрытых ключей с удаленного компьютера

Эта серия команд включает делегирование, а затем удаляет сертификат и связанный закрытый ключ на удаленном компьютере. Чтобы удалить закрытый ключ на удаленном компьютере, необходимо использовать делегированные учетные данные.

Используйте `Enable-WSManCredSSP` командлет, чтобы включить проверку подлинности на стороне поставщика службы безопасности учетных данных на клиенте на удаленном компьютере S1.
CredSSP разрешает делегирование проверки подлинности.

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

С помощью `Connect-WSMan` командлета Подключите компьютер S1 к службе WinRM на локальном компьютере. После выполнения этой команды компьютер S1 отображается на локальном `WSMan:` диске в PowerShell.

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

Теперь можно использовать командлет Set-Item на диске WSMan:, чтобы включить атрибут CredSSP для службы WinRM.

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

Запустите удаленный сеанс на компьютере S1 с помощью `New-PSSession` командлета и укажите проверку подлинности CredSSP. Сохраняет сеанс в `$s` переменной.

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

Наконец, используйте `Invoke-Command` командлет для выполнения `Remove-Item` команды в сеансе в `$s` переменной. `Remove-Item`Команда использует параметр **DeleteKey** для удаления закрытого ключа вместе с указанным сертификатом.

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a>Удаление просроченных сертификатов

Эта команда использует параметр **ExpiringInDays** `Get-ChildItem` командлета со значением 0 для получения сертификатов в хранилище веб-размещения с истекшим сроком действия.

Переменная, содержащая возвращенные сертификаты, передается в `Remove-Item` командлет, который удаляет их. Команда использует параметр **DeleteKey** для удаления закрытого ключа вместе с сертификатом.

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a>Создание сертификатов

`New-Item`Командлет не создает новые сертификаты в поставщике **сертификатов** . Используйте командлет [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) , чтобы создать сертификат для целей тестирования.

## <a name="creating-certificate-stores"></a>Создание хранилищ сертификатов

На диске CERT: `New-Item` командлет создает хранилища сертификатов в расположении хранилища LocalMachine. Он поддерживает параметры **Name** , **path** , **WhatIf** и **Confirm** . Все остальные параметры игнорируются. Команда возвращает **System. Security. Cryptography. X509Certificates. X509Store** , представляющий новое хранилище сертификатов.

Эта команда создает новое хранилище сертификатов с именем "CustomStore" в расположении хранилищ LocalMachine.

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a>Создание нового хранилища сертификатов на удаленном компьютере

Эта команда создает новое хранилище сертификатов с именем "HostingStore" в расположении хранилищ LocalMachine на компьютере Server01.

Команда использует `Invoke-Command` командлет для выполнения `New-Item` команды на компьютере Server01. Команда возвращает **System. Security. Cryptography. X509Certificates. X509Store** , представляющий новое хранилище сертификатов.

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a>Создание сертификатов клиента для WS-Man

Эта команда создает запись **clientcertificate** , которая может использоваться клиентом **WS-Management** . Новый **clientcertificate** будет отображаться в каталоге **ClientCertificate** как "ClientCertificate_1234567890". Все параметры являются обязательными. **Издатель** должен быть отпечаткой сертификата издателя.

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a>Удаление хранилищ сертификатов

### <a name="delete-a-certificate-store-from-a-remote-computer"></a>Удаление хранилища сертификатов с удаленного компьютера

Эта команда использует `Invoke-Command` командлет для выполнения `Remove-Item` команды на компьютерах S1 и S2. `Remove-Item`Команда включает параметр **рекурсии** , который удаляет сертификаты из хранилища перед удалением хранилища.

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика. Эти параметры действительны во всех подкаталогах поставщика сертификатов, но действуют только для сертификатов.

> [!NOTE]
> Параметры, выполняющие фильтрацию по `EnhancedKeyUsageList` свойству, также возвращают элементы с пустым `EnhancedKeyUsageList` значением свойства.
> Сертификаты с пустым **EnhancedKeyUsageList** можно использовать для всех целей.

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a>CodeSigningCert <System.Management.Automation.SwitchParameter>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Этот параметр возвращает сертификаты с подписыванием кода в значении свойства **EnhancedKeyUsageList** .

### <a name="deletekey-systemmanagementautomationswitchparameter"></a>DeleteKey <System.Management.Automation.SwitchParameter>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)

Этот параметр удаляет связанный закрытый ключ при удалении сертификата.

> [!IMPORTANT]
> Чтобы удалить закрытый ключ, связанный с сертификатом пользователя в `Cert:\CurrentUser` хранилище на удаленном компьютере, необходимо использовать делегированные учетные данные. `Invoke-Command`Командлет поддерживает делегирование учетных данных с помощью параметра **CredSSP** . Перед использованием `Remove-Item` с `Invoke-Command` делегированием учетных данных следует учитывать все риски безопасности.

Этот параметр появился в PowerShell 3,0.

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a>DnsName <Microsoft.PowerShell.Commands.DnsNameRepresentation>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Этот параметр возвращает сертификаты с указанным именем домена или шаблоном имени в свойстве **DNSNameList** сертификата. Значение этого параметра может быть либо "Unicode", либо "ASCII". Значения Punycode преобразуются в формат Юникода. Допускаются подстановочные знаки ( `*` ).

Этот параметр появился в PowerShell 3,0.

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a>Документенкриптионцерт <System. Management. Automation. переключатель>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Этот параметр возвращает сертификаты с "шифрованием документа" в значении свойства **EnhancedKeyUsageList** .

### <a name="eku-systemstring"></a>EKU <System.String>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Этот параметр возвращает сертификаты с указанным текстом или текстовым шаблоном в `EnhancedKeyUsageList` свойстве сертификата. Допускаются подстановочные знаки ( `*` ). `EnhancedKeyUsageList`Свойство содержит понятное имя и поля OID EKU.

Этот параметр появился в PowerShell 3,0.

### <a name="expiringindays-systemint32"></a>ExpiringInDays <System.Int32>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Этот параметр возвращает сертификаты, срок действия которых истекает через указанное число дней или до него. Значение 0 (нуль) возвращает сертификаты, срок действия которых истек.

Этот параметр появился в PowerShell 3,0.

### <a name="itemtype-string"></a>ItemType \<String\>

Этот параметр позволяет указать тип элемента, созданного `New-Item` .

В `Certificate` диске допустимы следующие значения:

- Поставщик Certificate
- Сертификат
- Магазин
- StoreLocation

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a>SSLServerAuthentication <System.Management.Automation.SwitchParameter>

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Возвращает только сертификаты сервера для размещения веб-сайтов SSL. Этот параметр возвращает сертификаты, для которых в значении свойства задано значение "Проверка подлинности сервера" `EnhancedKeyUsageList` .

Этот параметр появился в PowerShell 3,0.

## <a name="script-properties"></a>Свойства скрипта

В объект **x509Certificate2** , представляющий сертификаты, были добавлены новые свойства скрипта, которые упрощают поиск сертификатов и управление ими.

- `DnsNameList`: Для заполнения `DnsNameList` свойства поставщик сертификата копирует содержимое из записи dnsName в расширении субжекталтернативенаме (SAN). Если расширение SAN пусто, свойство заполняется содержимым из поля Subject сертификата.

- `EnhancedKeyUsageList`. Чтобы заполнить `EnhancedKeyUsageList` свойство, поставщик сертификата копирует свойства Oid поля енханцедкэйусаже (EKU) в сертификате и создает для него понятное имя.

- `SendAsTrustedIssuer`: Для заполнения `SendAsTrustedIssuer` свойства поставщик сертификата копирует `SendAsTrustedIssuer` свойство из сертификата.  Дополнительные сведения см. в разделе [Управление доверенными издателями для проверки подлинности клиента](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).

Эти новые функции позволяют выполнять поиск сертификатов на основе их DNS-имен и дат истечения срока действия сертификатов и различать сертификаты проверки подлинности клиента и сервера по значению свойств расширенного использования ключа (EKU).

## <a name="using-the-pipeline"></a>Использование конвейера

Командлеты поставщика принимают входные данные конвейера. Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.
Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.

## <a name="getting-help"></a>Получение справки

Начиная с PowerShell 3,0 можно получить настраиваемые разделы справки для командлетов поставщиков, которые объясняют, как эти командлеты ведут себя на диске файловой системы.

Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте `-Path` параметр параметра, `Get-Help` чтобы указать диск файловой системы.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a>См. также статью

[about_Providers](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Signing](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[Get-PfxCertificate](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
