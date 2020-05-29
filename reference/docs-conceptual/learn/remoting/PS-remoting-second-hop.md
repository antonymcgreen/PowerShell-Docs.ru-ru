---
ms.date: 05/14/2020
keywords: powershell,командлет
title: Выполнение второго прыжка при удаленном взаимодействии PowerShell
ms.openlocfilehash: 3a9db11726d4c02dc69e52c45da304f7422def39
ms.sourcegitcommit: 843756c8277e7afb874867703963248abc8a6c91
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83439382"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a>Выполнение второго прыжка при удаленном взаимодействии PowerShell

"Проблема второго прыжка" относится к ситуации, аналогичной следующей:

1. Вы вошли на сервер _ServerA_.
2. С сервера _ServerA_ вы запускаете удаленный сеанс PowerShell для подключения к серверу _ServerB_.
3. Команда, запущенная вами на сервере _ServerB_ через сеанс удаленного взаимодействия PowerShell, пытается получить доступ к ресурсу на сервере _ServerC_.
4. Доступ к ресурсу на _ServerC_ запрещен, так как учетные данные, используемые вами для создания сеанса удаленного взаимодействия PowerShell, не передаются с сервера _ServerB_ на сервер _ServerC_.

Существует несколько способов для решения этой проблемы. В следующей таблице перечислены методы в порядке предпочтения.

|                      Конфигурация                       |                                  Примечание                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| CredSSP                                                  | Сбалансированное сочетание простоты использования и безопасности                                      |
| Ограниченное делегирование Kerberos на основе ресурсов           | Более высокая безопасность с простой настройкой                             |
| Ограниченное делегирование Kerberos                          | Высокий уровень безопасности, но с необходимостью прав администратора домена                         |
| Делегирование Kerberos (без ограничений)                      | Не рекомендуется                                                        |
| Just Enough Administration (JEA)                         | Потенциально наилучшая безопасность, но с необходимостью тщательной настройки |
| PSSessionConfiguration с использованием RunAs                       | Более простая настройка, но с необходимостью управления учетными данными                |
| Передача учетных данных внутри блока сценария `Invoke-Command` | Максимальная простота использования, но с необходимостью указания учетных данных                       |

## <a name="credssp"></a>CredSSP

Для проверки подлинности можно использовать [протокол CredSSP][credssp].
Протокол CredSSP кэширует учетные данные на удаленном сервере (_ServerB_), что делает их уязвимыми для атак, направленных на кражу учетных данных. Если безопасность удаленного компьютера нарушена, злоумышленник получает доступ к учетным данным пользователя. Протокол CredSSP по умолчанию отключен на компьютерах клиента и сервера. Включать протокол CredSSP следует только в самых надежных средах. Например, при подключении администратора домена к контроллеру домена, так как контроллер домена является высоконадежным.

Дополнительные сведения о вопросах безопасности при использовании протокола CredSSP для удаленного взаимодействия PowerShell см. в статье [Accidental Sabotage: Beware of CredSSP][beware] (Непреднамеренный саботаж: берегитесь CredSSP).

Дополнительные сведения об атаках, направленных на хищение учетных данных, см. в техническом документе [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].

См. пример того, как [включить и использовать CredSSP для удаленного взаимодействия PowerShell][credssp-psblog].

**Преимущества**

- Это работает для всех серверов с Windows Server 2008 или более поздней версии.

**Недостатки**

- Имеет уязвимости.
- Требует настройки как клиентских, так и серверных ролей.
- Не работает с группой "Защищенные пользователи". Дополнительные сведения см. в разделе [Группа безопасности "Защищенные пользователи"][protected-users].

## <a name="kerberos-constrained-delegation"></a>Ограниченное делегирование Kerberos

Для выполнения второго прыжка можно использовать устаревшее ограниченное делегирование (не на основе ресурсов). Настройте ограниченное делегирование Kerberos с параметром "Использовать любой протокол проверки подлинности", чтобы разрешить переход протокола.

**Преимущества**

- Не требует специального кода.
- Учетные данные не сохраняются.

**Недостатки**

- Не поддерживает второй прыжок для WinRM.
- Для настройки требуются права администратора домена.
- Требует настройки для объекта Active Directory удаленного сервера (_ServerB_).
- Ограничен одним доменом. Не может использоваться между доменами или лесами.
- Требует права на обновление объектов и имен субъектов-служб (SPN).
- _ServerB_ может получить билет Kerberos для _ServerC_ от имени пользователя без вмешательства пользователя.

> [!NOTE]
> Учетные записи Active Directory, которые имеют набор свойств **Учетная запись важна и не может быть делегирована**, не могут быть делегированы. Дополнительные сведения см. в статье [Security Focus: Фокус безопасности: анализ свойств "Учетная запись важна и не может быть делегирована" для привилегированных учетных записей][blog] и [Средства и параметры проверки подлинности Kerberos][ktools].

## <a name="resource-based-kerberos-constrained-delegation"></a>Ограниченное делегирование Kerberos на основе ресурсов

С помощью ограниченного делегирования Kerberos на основе ресурсов (которое впервые появилось в Windows Server 2012) можно настроить делегирование учетных данных на объект сервера, где находятся ресурсы. В описанном выше сценарии второго прыжка вы настраиваете сервер _ServerC_, чтобы указать, откуда он будет принимать делегированные учетные данные.

**Преимущества**

- Учетные данные не сохраняются.
- Настраивается с помощью командлетов PowerShell. Не требует написания специального кода.
- Не требует для настройки доступ с правами администратора домена.
- Работает между доменами и лесами.

**Недостатки**

- Требует Windows Server 2012 или более поздней версии.
- Не поддерживает второй прыжок для WinRM.
- Требует права на обновление объектов и имен субъектов-служб (SPN).

> [!NOTE]
> Учетные записи Active Directory, которые имеют набор свойств **Учетная запись важна и не может быть делегирована**, не могут быть делегированы. Дополнительные сведения см. в статье [Security Focus: Фокус безопасности: анализ свойств "Учетная запись важна и не может быть делегирована" для привилегированных учетных записей][blog] и [Средства и параметры проверки подлинности Kerberos][ktools].

### <a name="example"></a>Пример

Рассмотрим пример PowerShell, который настраивает на _ServerC_ ограниченное делегирование на основе ресурсов, разрешающее использовать делегированные учетные данные с _ServerB_. В этом примере предполагается, что все серверы работают под управлением Windows Server 2012 или более поздней версии и существует по меньшей мере один контроллер домена Windows Server 2012 в каждом домене, к которому относятся какие-либо из серверов.

Перед настройкой ограниченного делегирования следует добавить компонент `RSAT-AD-PowerShell`, чтобы установить модуль Active Directory PowerShell, а затем импортировать этот модуль в сеанс:

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

Сейчас параметр несколько доступных командлетов имеют параметр **PrincipalsAllowedToDelegateToAccount**:

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

Параметр **PrincipalsAllowedToDelegateToAccount** задает атрибут объекта Active Directory **msDS-AllowedToActOnBehalfOfOtherIdentity**, содержащий список управления доступом (ACL), который указывает, какие учетные записи имеют разрешение на делегирование учетных данных для связанной учетной записи (в нашем примере это будет учетная запись компьютера для _ServerA_).

Теперь давайте настроим переменные, которые будем использовать для представления серверов:

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

WinRM (и поэтому удаленное взаимодействие PowerShell) по умолчанию выполняется как учетная запись компьютера. Это можно проверить, просмотрев свойство **StartName** службы `winrm`:

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

Чтобы _ServerC_ разрешал делегирование из сеанса удаленного взаимодействия PowerShell на _ServerB_, мы должны задать в качестве значения параметра **PrincipalsAllowedToDelegateToAccount** на _ServerC_ объект компьютера _ServerB_:

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

[Центр распространения ключей](/windows/win32/secauthn/key-distribution-center) Kerberos кэширует отклоненные попытки доступа (негативный кэш) в течение 15 минут. Если сервер _ServerB_ ранее пытался получить доступ к серверу _ServerC_, потребуется очистить кэш на сервере _ServerB_, вызвав следующую команду:

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

Можно также перезагрузить компьютер или подождать не менее 15 минут для очистки кэша.

После очистки кэша можно запустить код с _ServerA_ через _ServerB_ и до _ServerC_:

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

В этом примере переменная `$using` используется, чтобы сделать переменную `$ServerC` видимой для сервера _ServerB_.
Дополнительные сведения о переменной `$using` см. в разделе [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).

Чтобы разрешить нескольким серверам делегировать учетные данные серверу _ServerC_, задайте в качестве значения параметра **PrincipalsAllowedToDelegateToAccount** на сервере _ServerC_ в массив:

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

Если вы хотите сделать второй прыжок между доменами, добавьте полное доменное имя (FQDN) контроллера домена для того домена, к которому принадлежит _ServerB_:

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

Чтобы запретить нескольким серверам делегировать учетные данные серверу ServerC, задайте для параметра **PrincipalsAllowedToDelegateToAccount** на сервере _ServerC_ значение `$null`:

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a>Информация об ограниченном делегировании Kerberos на основе ресурсов

- [Новые возможности проверки подлинности Kerberos][whats-new]
- [Как Windows Server 2012 упрощает работу с ограниченным делегированием Kerberos, часть 1][kcd2012-1]
- [Как Windows Server 2012 упрощает работу с ограниченным делегированием Kerberos, часть 2][kcd2012-2]
- [Основные сведения об ограниченном делегировании Kerberos для развертывания прокси приложения Azure Active Directory со встроенной проверкой подлинности Windows][kcdpaper]
- [[MS-ADA2] Атрибуты схемы Active Directory на букву M — 2.210. Атрибут msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]
- [[MS-SFU] Расширения протокола Kerberos: Service for User и протокол ограниченного делегирования — 1.3.2. S4U2proxy][MS-SFU]
- [Удаленное администрирование без ограниченного делегирования с помощью PrincipalsAllowedToDelegateToAccount][remote-admin]

## <a name="kerberos-delegation-unconstrained"></a>Делегирование Kerberos (без ограничений)

Для выполнения второго прыжка можно также использовать делегирование Kerberos без ограничений. Как и во всех сценариях Kerberos, учетные данные не сохраняются. Этот метод не поддерживает второй прыжок для WinRM.

> [!WARNING]
> Этот метод не позволяет контролировать, где используются делегированные учетные данные. Он менее безопасен, чем CredSSP. Этот метод следует использовать только для сценариев тестирования.

## <a name="just-enough-administration-jea"></a>Just Enough Administration (JEA)

JEA позволяет ограничить команды, доступные администратору во время сеанса PowerShell. Это позволяет решить проблему второго прыжка.

Сведения о JEA см. в разделе [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).

**Преимущества**

- При использовании виртуальной учетной записи обслуживание паролей не требуется.

**Недостатки**

- Требуется WMF 5.0 или более поздней версии.
- Требует настройки на каждом промежуточном сервере (_ServerB_).

## <a name="pssessionconfiguration-using-runas"></a>PSSessionConfiguration с использованием RunAs

Можно создать конфигурацию сеанса на сервере _ServerB_ и задать ее параметр **RunAsCredential**.

Сведения об использовании **PSSessionConfiguration** и **RunAs** для решения проблемы второго прыжка см. в статье [Another solution to multi-hop PowerShell remoting][pssessionconfig] (Другое решение для удаленного взаимодействия PowerShell с несколькими прыжками).

**Преимущества**

- Работает для любого сервера с WMF 3.0 или более поздней версии.

**Недостатки**

- Требует настройки **PSSessionConfiguration** и **RunAs** на каждом промежуточном сервере (_ServerB_).
- Требуется обслуживание паролей при использовании учетной записи **запуска от имени** домена.

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a>Передача учетных данных внутри блока сценария Invoke-Command

Можно передать учетные данные внутри параметра **ScriptBlock** вызова командлета [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).

**Преимущества**

- Не требуется специальной настройки серверов.
- Работает на любом сервере с WMF 2.0 или более поздней версии.

**Недостатки**

- Требует внимательного составления кода.
- При использовании WMF 2.0 требуется использовать иной синтаксис для передачи аргументов в удаленный сеанс.

### <a name="example"></a>Пример

Следующий пример показывает, как передать учетные данные внутри блока сценария **Invoke-Command**:

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a>См. также раздел

[Вопросы обеспечения безопасности для удаленного взаимодействия PowerShell](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group
