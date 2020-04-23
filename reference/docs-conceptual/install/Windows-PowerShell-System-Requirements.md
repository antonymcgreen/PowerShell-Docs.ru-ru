---
ms.date: 12/06/2019
keywords: powershell,командлет
title: Требования к системе для Windows PowerShell
ms.openlocfilehash: 713b062916fec0c5c70ea9a7f95fea3570afb64a
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "74953795"
---
# <a name="windows-powershell-system-requirements"></a>Требования к системе для Windows PowerShell

В этой статье перечислены требования к системе для Windows PowerShell 3.0, Windows PowerShell 4.0, Windows PowerShell 5.0 и Windows PowerShell 5.1. А также специальные функции, такие как интегрированная среда сценариев Windows PowerShell (ISE), команды модели CIM и рабочие процессы.

Windows® 8.1 и Windows Server® 2012 R2 включают все необходимые программы. Эта статья предназначена для пользователей более ранних версий Windows.

## <a name="operating-system-requirements"></a>Требования к операционной системе

### <a name="windows-powershell-51"></a>Windows PowerShell 5.1

Windows PowerShell 5.1 выполняется в следующих версиях Windows: Для запуска Windows PowerShell 5.1 установите Windows Management Framework 5.1. Дополнительные сведения см. в статье [Установка и настройка WMF 5.1](../wmf/setup/install-configure.md).

| Версия Windows | Требования к системе |
| ----- | ----- |
| Windows Server 2019 | Устанавливается по умолчанию |
| Windows Server 2016 | Устанавливается по умолчанию |
| Windows Server 2012 R2 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2012 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2008 R2 с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 10 версии 1607 и выше | Устанавливается по умолчанию |
| Windows 10 версии 1507, 1511 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 8.1 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 7 с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |

### <a name="windows-powershell-50"></a>Windows PowerShell 5.0

Windows PowerShell 5.0 работает в следующих версиях Windows. Для запуска Windows PowerShell 5.0 установите Windows Management Framework 5.1. Дополнительные сведения см. в статье [Установка и настройка WMF 5.1](../wmf/setup/install-configure.md). Windows Management Framework 5.1 заменяет Windows Management Framework 5.0.

| Версия Windows | Требования к системе |
| ----- | ----- |
| Windows Server 2019 | Более поздняя версия устанавливается по умолчанию |
| Windows Server 2016 | Более поздняя версия устанавливается по умолчанию |
| Windows Server 2012 R2 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2012 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2008 R2 с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 10 версии 1607 и выше | Более поздняя версия устанавливается по умолчанию |
| Windows 10 версии 1507, 1511 | Устанавливается по умолчанию |
| Windows 8.1 | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 7 с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 5.1](https://aka.ms/wmf5download) |

### <a name="windows-powershell-40"></a>Windows PowerShell 4.0

Windows PowerShell 4.0 выполняется в следующих версиях Windows: Чтобы запустить Windows PowerShell 4.0, установите указанную версию Windows Management Framework для вашей операционной системы.

| Версия Windows | Требования к системе |
| ----- | ----- |
| Windows 8.1 | Устанавливается по умолчанию |
| Windows Server 2012 R2 | Устанавливается по умолчанию |
| Windows 7® с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) |
| Windows Server® 2008 R2 с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) |

### <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3.0 выполняется в следующих версиях Windows: Чтобы запустить Windows PowerShell 3.0, установите указанную версию Windows Management Framework для вашей операционной системы.

| Версия Windows | Требования к системе |
| ----- | ----- |
| Windows 8 | Устанавливается по умолчанию |
| Windows Server 2012 | Устанавливается по умолчанию |
| Windows 7® с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) |
| Windows Server® 2008 R2 с пакетом обновления 1 (SP1) | Установите [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) |
| Windows Server 2008 с пакетом обновления 2 (SP2) | Установите [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) |

## <a name="microsoft-net-framework-requirements"></a>Требования к Microsoft .NET Framework

В следующей таблице приведены требования к .NET Framework для Windows PowerShell.

| Версия | Требование к .NET |
| ----- | ----- |
| Windows PowerShell 5.1 | Требует полную установку Microsoft .NET Framework 4.5. Windows 8.1 и Windows Server 2012 R2 включают Microsoft .NET Framework 4.5 по умолчанию. |
| Windows PowerShell 5.0 | Требует полную установку Microsoft .NET Framework 4.5. Windows 8.1 и Windows Server 2012 R2 включают Microsoft .NET Framework 4.5 по умолчанию. |
| Windows PowerShell 4.0 | Требует полную установку Microsoft .NET Framework 4.5. Windows 8.1 и Windows Server 2012 R2 включают Microsoft .NET Framework 4.5 по умолчанию. |
| Windows PowerShell 3.0 | Требует полную установку Microsoft .NET Framework 4. Windows 8 и Windows Server 2012 содержат Microsoft .NET Framework 4.5 по умолчанию, что удовлетворяет этому требованию. |

Используйте следующие ссылки, чтобы загрузить Microsoft .NET Framework из центра загрузки Майкрософт.

| Версия | Ссылка |
| ----- | ----- |
| .NET Framework 4.5 (`dotNetFx45_Full_setup.exe`) | [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkID=242919) |
| .NET Framework 4 (`dotNetFx40_Full_setup.exe`) | [Microsoft .NET Framework 4 (веб-установщик)](https://www.microsoft.com/en-us/download/details.aspx?id=17851) |

## <a name="windows-management-framework-40"></a>Windows Management Framework 4.0

Для работы Windows PowerShell 5.0 необходимо установить Windows Management Framework 4.0 в Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1).

## <a name="ws-management-30"></a>WS-Management 3.0

Windows PowerShell 3.0 и Windows PowerShell 4.0 требуют наличия WS-Management 3.0, поддерживающей службу WinRM и протокол WSMan. Эта программа входит в Windows 8.1, Windows Server 2012 R2, Windows 8, Windows Server 2012, Windows Management Framework 4.0 и Windows Management Framework 3.0.

## <a name="windows-management-instrumentation-30"></a>Инструментарий управления Windows 3.0

Windows PowerShell 3.0 и Windows PowerShell 4.0 требуют инструментарий управления Windows (WMI) 3.0. Эта программа входит в Windows 8.1, Windows Server 2012 R2, Windows 8, Windows Server 2012, Windows Management Framework 4.0 и Windows Management Framework 3.0. Если эта программа не установлена на компьютере, компоненты, нуждающиеся в инструментарии WMI, например команды CIM, не выполняются.

## <a name="common-language-runtime-40"></a>Среда CLR 4.0

Windows PowerShell 3.0, Windows PowerShell 4.0 и Windows PowerShell 5.0 компилируются для среды CLR версии 4.0.

## <a name="graphical-user-interface-requirements"></a>Требования к графическому пользовательскому интерфейсу

Windows PowerShell — это основанное на консоли приложение, для работы которого не требуется графический пользовательский интерфейс.
Оно хорошо подходит для компьютеров без экранов или мониторов либо пользовательского интерфейса, таких как Windows Server 2012 R2 или Windows Server 2012, с установкой основных серверных компонентов.

Для некоторых элементов необходим графический пользовательский интерфейс. Дополнительные сведения см. в разделе справки для каждого элемента.

- Интегрированная среда сценариев (ISE) Windows PowerShell. Дополнительные сведения см. в обзорной статье об [интегрированной среде сценариев Windows PowerShell](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).
- Командлеты
  - [Out-GridView](/powershell/module/microsoft.powershell.utility/out-gridview)
  - [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)
  - [Show-ControlPanelItem](/powershell/module/Microsoft.PowerShell.Management/Show-ControlPanelItem)
  - [Show-EventLog](/powershell/module/Microsoft.PowerShell.Management/Show-EventLog)
- Параметры
  - Параметр **ShowWindow** командлета [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help).
  - Параметр **ShowSecurityDescriptorUI** командлетов [Register-PSSessionConfiguration](/powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration) и [Set-PSSessionConfiguration](/powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration).

## <a name="windows-powershell-engine-requirements"></a>Требования к подсистеме Windows PowerShell

Windows PowerShell 4.0 предназначен для обратной совместимости с Windows PowerShell 3.0 и Windows PowerShell 2.0. Командлеты, поставщики, оснастки, модули и сценарии, написанные для Windows PowerShell 2.0, выполняются и в Windows PowerShell 3.0, и в Windows PowerShell 4.0 без изменений.

Однако из-за изменений в политике активации среды выполнения в Microsoft .NET Framework 4 основные программы Windows PowerShell, написанные для Windows PowerShell 2.0 и скомпилированные с помощью среды CLR 2.0, не могут выполняться без изменения в Windows PowerShell 3.0, которые компилируются в среде CLR 4.0.

Подсистеме Windows PowerShell 2.0 требуется Microsoft .NET Framework версии не ниже 2.0.50727. Этому требованию удовлетворяет Microsoft .NET Framework 3.5 с пакетом обновления 1 (SP1). Этому требованию не удовлетворяет Microsoft .NET Framework 4 и более поздних версий.

Дополнительные сведения о добавлении или установке подсистемы Windows PowerShell 2.0 и требуемых версий Microsoft .NET Framework см. в статье [Установка подсистемы Windows PowerShell 2.0](Installing-the-Windows-PowerShell-2.0-Engine.md). Дополнительные сведения о запуске подсистемы Windows PowerShell 2.0 см. в статье [Запуск подсистемы Windows PowerShell 2.0](../getting-started/Starting-the-Windows-PowerShell-2.0-Engine.md).

## <a name="windows-preinstallation-environment"></a>Среда предустановки Windows

Windows PowerShell 2.0, Windows PowerShell 3.0 и Windows PowerShell 4.0 выполняются в среде предустановки Windows (Windows PE). Однако не поддерживаются следующие командлеты.

- Командлеты фоновой интеллектуальной службы передачи (BITS). Дополнительные сведения см. в статье [BitsTransfer](/powershell/module/bitstransfer/?view=win10-ps).
- [Get-EventLog](/powershell/module/Microsoft.PowerShell.Management/Get-EventLog)
- [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)
- [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)
- [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)

В Windows PE отсутствует служба **WinRM**.

## <a name="see-also"></a>См. также раздел

[Начало работы с Windows PowerShell](../getting-started/Getting-Started-with-Windows-PowerShell.md)

[Установка Windows PowerShell](Installing-Windows-PowerShell.md)

[Запуск Windows PowerShell](../getting-started/Starting-Windows-PowerShell.md)

[Windows Management Framework](../wmf/overview.md)
