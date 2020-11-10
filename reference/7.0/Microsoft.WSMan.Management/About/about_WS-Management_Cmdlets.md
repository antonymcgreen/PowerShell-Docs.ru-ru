---
description: Содержит общие сведения о веб-службах для управления (WS-Management) в качестве фона для использования командлетов WS-Management в Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: d11b8ca72951409a1b9a508623b3f39cae46e318
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390479"
---
# <a name="about-ws-management-cmdlets"></a>О командлетах WS-Management

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Содержит общие сведения о веб-службах для управления (WS-Management) в качестве фона для использования командлетов WS-Management в Windows PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

В этом разделе представлен обзор веб-служб для управления (WS-Management) в качестве фона для использования командлетов WS-Management в Windows PowerShell. В этом разделе также приведены ссылки на дополнительные сведения о WS-Management. Реализация WS-Management Майкрософт также называется служба удаленного управления Windows (WinRM).

## <a name="about-ws-management"></a>О WS-Management

Служба удаленного управления Windows является реализацией протокола WS-Management (Майкрософт), стандартным протоколом на основе протокола SOAP, который позволяет различным поставщикам взаимодействовать с оборудованием и операционными системами различных поставщиков. Спецификация протокола WS-Management предоставляет системам общий способ доступа и обмена данными управления в инфраструктуре информационных технологий (ИТ). WS-Management и интеллектуальный интерфейс управления платформой (IPMI) вместе с сборщиком событий являются компонентами функций управления оборудованием Windows.

Протокол WS-Management основан на следующих стандартных спецификациях веб-служб: HTTPS, SOAP по HTTP (WS-I Profile), SOAP 1,2, WS-Addressing, WS-передачи, WS-enumeration и WS-Eventing.

## <a name="ws-management-and-wmi"></a>WS-Management и WMI

WS-Management можно использовать для получения данных, предоставляемых инструментарий управления Windows (WMI) (WMI). Данные WMI можно получить с помощью скриптов или приложений, использующих API WS-Management сценариев или с помощью средства командной строки WinRM. WS-Management поддерживает большинство знакомых классов и операций WMI, включая внедренные объекты. WS-Management может использовать инструментарий WMI для получения данных о ресурсах или управлении ресурсами на компьютерах под управлением Windows. Это означает, что вы можете получать данные об объектах, таких как диски, сетевые адаптеры, службы или процессы в Организации, с помощью существующего набора классов WMI. Вы также можете получить доступ к данным оборудования, доступным в стандартном поставщике IPMI WMI.

## <a name="ws-management-windows-powershell-provider-wsman"></a>WS-Management поставщика Windows PowerShell (WSMan)

Поставщик WSMan предоставляет иерархическое представление о доступных параметрах конфигурации WS-Management. Поставщик позволяет исследовать и задавать различные параметры конфигурации WS-Management.

## <a name="ws-management-configuration"></a>Конфигурация WS-Management

Если WS-Management не установлен и не настроен, удаленное взаимодействие Windows PowerShell недоступно, командлеты WS-Management не выполняются, WS-Management сценарии не выполняются, а поставщик WSMan не может выполнять операции с данными. WS-Management программа командной строки, WinRM и пересылка событий также зависят от конфигурации WS-Management.

## <a name="ws-management-cmdlets"></a>Командлеты WS-Management

Функции WS-Management реализованы в Windows PowerShell с помощью модуля, содержащего набор командлетов и поставщика WSMan. Эти командлеты можно использовать для выполнения комплексных задач, необходимых для управления параметрами WS-Management на локальных и удаленных компьютерах.

Доступны следующие командлеты WS-Management.

## <a name="connection-cmdlets"></a>Командлеты подключения

- Connect-WSMan: подключает локальный компьютер к службе WS-Management (WinRM) на удаленном компьютере.

- Disconnect-WSMan: отключает локальный компьютер от службы WS-Management (WinRM) на удаленном компьютере.

## <a name="management-data-cmdlets"></a>Командлеты Management-Data

- Get-WSManInstance: отображает сведения об управлении для экземпляра ресурса, который указан с помощью URI ресурса.

- Invoke-WSManAction: вызывает действие для целевого объекта, заданного универсальным кодом ресурса (URI) и селекторами.

- New-WSManInstance: создает новый экземпляр ресурса управления.

- Remove-WSManInstance — удаляет экземпляр ресурса управления.

- Set-WSManInstance: изменяет сведения об управлении, связанные с ресурсом.

## <a name="setup-and-configuration-cmdlets"></a>Командлеты установки и настройки

- Set-WSManQuickConfig: настраивает локальный компьютер для удаленного управления.
  С помощью командлета Set-WSManQuickConfig можно настроить WS-Management, чтобы разрешить удаленные подключения к службе WS-Management (WinRM). Командлет Set-WSManQuickConfig выполняет следующие операции:
  - Он определяет, запущена ли служба WS-Management (WinRM). Если служба WinRM не запущена, командлет Set-WSManQuickConfig запускает службу.
  - Он задает автоматический тип запуска службы WS-Management (WinRM).
  - Он создает прослушиватель, который принимает запросы с любого IP-адреса. Транспортным протоколом по умолчанию является HTTP.
  - Он включает исключение брандмауэра для трафика WS-Management.

  Примечание. для запуска этого командлета в Windows Vista, Windows Server 2008 и более поздних версиях Windows необходимо запустить Windows PowerShell с параметром "Запуск от имени администратора".

- Test-WSMan: проверяет, что WS-Management установлен и настроен. Командлет Test-WSMan проверяет, работает ли служба WS-Management (WinRM) и настроена на локальном или удаленном компьютере.

- Disable-WSManCredSSP: отключает проверку подлинности CredSSP на клиентском компьютере.

- Enable-WSManCredSSP: включает проверку подлинности CredSSP на клиентском компьютере.

- Get-WSManCredSSP: получает конфигурацию, связанную с CredSSP, для клиентского компьютера.

## <a name="ws-management-specific-cmdlets"></a>Командлеты, относящиеся к службе WS-Management

- New-WSManSessionOption: создает объект WSManSessionOption для использования в качестве входных данных для одного или нескольких параметров командлета WS-Management.

## <a name="additional-ws-management-information"></a>Дополнительные сведения о WS-Management

Дополнительные сведения о WS-Management см. в следующих разделах документации по Windows.

[Удаленное управление Windows](/windows/win32/winrm/portal)

[О служба удаленного управления Windows](/windows/win32/winrm/about-windows-remote-management)

[Установка и настройка для служба удаленного управления Windows](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[Архитектура служба удаленного управления Windows](/windows/win32/winrm/windows-remote-management-architecture)

[Протокол WS-Management](/windows/win32/winrm/ws-management-protocol)

[служба удаленного управления Windows и WMI](/windows/win32/winrm/windows-remote-management-and-wmi)

[URI ресурсов](/windows/win32/winrm/resource-uris)

[Удаленное управление оборудованием](/windows/win32/winrm/remote-hardware-management)

[События](/windows/win32/winrm/events)

## <a name="see-also"></a>СМ. ТАКЖЕ

[Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan)

[Disable-WSManCredSSP](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[Disconnect-WSMan](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[Enable-WSManCredSSP](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[Get-WSManCredSSP](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[Get-WSManInstance](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[Invoke-WSManAction](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[New-WSManInstance](xref:Microsoft.WSMan.Management.New-WSManInstance)

[Remove-WSManInstance](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[Set-WSManInstance](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[Set-WSManQuickConfig](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[Test-WSMan](xref:Microsoft.WSMan.Management.Test-WSMan)
