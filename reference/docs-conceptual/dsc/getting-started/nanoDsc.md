---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Использование DSC на сервере Nano Server
ms.openlocfilehash: fb826455c21833ae4c8dc2ecd731ffce6bf7eaba
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953861"
---
# <a name="using-dsc-on-nano-server"></a>Использование DSC на сервере Nano Server

> Область применения: Windows PowerShell 5.0

**DSC для Nano Server** — это дополнительный пакет в папке `NanoServer\Packages` носителей Windows Server 2016. Пакет можно установить при создании виртуального жесткого диска для сервера Nano Server, указав значение **Microsoft-NanoServer-DSC-Package** для параметра **Packages** функции **New-NanoServerImage**. Например, при создании виртуального жесткого диска для виртуальной машины команда будет выглядеть следующим образом.

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

Сведения об установке и использовании сервера Nano Server, а также об управлении этим сервером с помощью удаленного взаимодействия PowerShell см. в статье [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server) (Приступая к работе с сервером Nano Server).

## <a name="dsc-features-available-on-nano-server"></a>Функции DSC, доступные на сервере Nano Server

Так как сервер Nano Server поддерживает только ограниченный набор API по сравнению с полной версией Windows Server, набор функций DSC в системе Nano Server на данный момент несравним с DSC в полнофункциональных SKU. DSC для Nano Server в настоящее время активно разрабатывается и не является законченным компонентом.

Следующие функции DSC в настоящее время доступны для Nano Server:

Режимы опроса и принудительной отправки

- Все командлеты DSC, которые существуют в полной версии Windows Server, включая следующие:
- [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager)
- [Set-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager)
- [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
- [Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug)
- [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)
- [Stop-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)
- [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)
- [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)
- [Publish-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)
- [Update-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration)
- [Restore-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Restore-DscConfiguration)
- [Remove-DscConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)
- [Get-DscConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)
- [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
- [Find-DscResource](/powershell/module/powershellget/find-dscresource?view=powershell-6)
- [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)
- [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)

- Компиляция конфигураций (см. раздел [Конфигурации DSC](../configurations/configurations.md)).

  **Проблема**. Не работает шифрование паролей (см. раздел [Защита MOF-файла](../pull-server/secureMOF.md)) во время компиляции конфигурации.

- Компиляция метаконфигураций (см. раздел [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md)).

- Выполнение ресурса в контексте пользователя (см. раздел [Запуск DSC с учетными данными пользователя (запуск от имени)](../configurations/runAsUser.md)).

- Ресурсы на основе класса (см. раздел [Написание пользовательских ресурсов DSC с использованием классов PowerShell](/previous-versions//dn948461(v=technet.10))).

- Отладка ресурсов DSC (см. раздел [Отладка ресурсов DSC](../troubleshooting/debugResource.md)).

  **Проблема**. Отладка не работает, если ресурс использует PsDscRunAsCredential (см. раздел [Запуск DSC с учетными данными пользователя](../configurations/runAsUser.md)).

- [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md)

- [Управление версиями ресурсов](../configurations/sxsResource.md)

- Опрашивающий клиент (конфигурации и ресурсы) (см. раздел [Настройка опрашивающего клиента с помощью имен конфигураций](../pull-server/pullClientConfigNames.md)).

- [Частичные конфигурации (по запросу и принудительная отправка)](../pull-server/partialConfigs.md)

- [Передача отчетов на опрашивающий сервер](../pull-server/reportServer.md)

- Шифрование MOF-файлов

- ведение журнала событий.

- Отчеты DSC службы автоматизации Azure

- Полнофункциональные ресурсы.

- **Архив**
- **Среда**
- **Файл**
- **Журнал**
- **ProcessSet**
- **Реестр**
- **Скрипт**
- **WindowsPackageCab**
- **WindowsProcess**
- **WaitForAll** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))
- **WaitForAny** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))
- **WaitForSome** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))

- Ресурсы, функциональность которых не полная.
- **Группирование**
- **GroupSet**

  **Проблема**. Приведенные выше ресурсы не работают, если определенный экземпляр вызывается дважды (дважды запускается одна и та же конфигурация).

- **Служба**
- **ServiceSet**

  **Проблема**. Работает только для запуска или остановки службы (атрибут status). Не работает при попытке изменить другие атрибуты службы, например startuptype, credentials, description и т. д. Возникает ошибка такого вида.

  *Не удается найти тип [management.managementobject]: убедитесь в том, что сборка, содержащая этот тип, загружена.*

- Нефункционирующие ресурсы.
- **Пользователь**

## <a name="dsc-features-not-available-on-nano-server"></a>Функции DSC, недоступные на сервере Nano Server

Следующие функции DSC в настоящее время недоступны для Nano Server:

- Расшифровка документа MOF с помощью зашифрованных паролей.
- Опрашивающий сервер — в настоящее время опрашивающий сервер нельзя настроить на сервере Nano Server.
- Все компоненты, не указанные в списке функций, работают.

## <a name="using-custom-dsc-resources-on-nano-server"></a>Использование настраиваемых ресурсов DSC на сервере Nano Server

Поскольку набор API Windows и библиотек CLR, доступный на сервере Nano Server, ограничен, ресурсы DSC, работающие в полной версии среды выполнения Windows, не всегда работают в Nano Server.
Перед развертыванием каких-либо настраиваемых ресурсов DSC в рабочей среде рекомендуется выполнять их полное и всестороннее тестирование.

## <a name="see-also"></a>См. также:

- [Начало работы с сервером Nano Server](/windows-server/get-started/getting-started-with-nano-server)
