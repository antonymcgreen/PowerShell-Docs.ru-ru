---
ms.date: 06/10/2020
ms.topic: conceptual
keywords: wmf,powershell,установка
contributor: keithb
title: Установка и настройка WMF 5.1
ms.openlocfilehash: 9e0b4b6ed387b0a0d7fcf62a913677986d70de92
ms.sourcegitcommit: 4a283fe5419f47102e6c1de7060880a934842ee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "84671399"
---
# <a name="install-and-configure-wmf-51"></a>Установка и настройка WMF 5.1

> [!IMPORTANT]
> WMF 5.0 заменяется выпуском WMF 5.1. Для получения поддержки пользователям WMF 5.0 необходимо выполнить обновление до WMF 5.1.
> **Для WMF 5.1 требуется .NET Framework 4.5.2** (или более поздняя версия). Если платформа .NET 4.5.2 (или более поздняя версия) не установлена, установка WMF 5.1 будет выполнена, но основные функции работать не будут.

## <a name="download-and-install-the-wmf-51-package"></a>Скачать и установить пакет WMF 5.1

Скачайте пакет WMF 5.1 для той операционной системы и архитектуры, в которой будет производиться установка.

| Операционная система       | Предварительные требования           | Ссылки на пакеты                          |
|------------------------|-------------------------|----------------------------------------|
| Windows Server 2012 R2 |                         | [Win8.1AndW2K12R2-KB3191564-x64.msu][] |
| Windows Server 2012    |                         | [W2K12-KB3191565-x64.msu][]            |
| Windows Server 2008 R2 | [.NET Framework 4.5.2][]| [Win7AndW2K8R2-KB3191566-x64.ZIP][]    |
| Windows 8.1            |                         | **x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</br>**x86:** [Win8.1-KB3191564-x86.msu][] |
| Windows 7 с пакетом обновления 1 (SP1)          | [.NET Framework 4.5.2][]| **x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</br>**x86:** [Win7-KB3191566-x86.ZIP][] |

[.NET Framework 4.5.2]: https://www.microsoft.com/download/details.aspx?id=42642
[W2K12-KB3191565-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839513
[Win7-KB3191566-x86.ZIP]: https://go.microsoft.com/fwlink/?linkid=839522
[Win7AndW2K8R2-KB3191566-x64.ZIP]: https://go.microsoft.com/fwlink/?linkid=839523
[Win8.1-KB3191564-x86.msu]: https://go.microsoft.com/fwlink/?linkid=839521
[Win8.1AndW2K12R2-KB3191564-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839516

- Перед установкой WMF 5.1 RTM нужно удалить предварительную версию WMF 5.1.
- WMF 5.1 можно установить непосредственно на WMF 5.0 или WMF 4.0.
- Устанавливать WMF 4.0 перед установкой WMF 5.1 в Windows 7 и Windows Server 2008 R2 **не требуется**.

## <a name="install-wmf-51-for-windows-server-2008-r2-and-windows-7"></a>Установить WMF 5.1 для Windows Server 2008 R2 и Windows 7

> [!NOTE]
> Инструкции по установке для Windows Server 2008 R2 и Windows 7 изменились и отличаются от инструкций для других пакетов. Инструкции по установке для Windows Server 2012 R2, Windows Server 2012 и Windows 8.1 см. ниже.

### <a name="wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1"></a>Предварительные требования WMF 5.1 для Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1)

Для установки WMF 5.1 на компьютере с ОС Windows Server 2008 R2 с пакетом обновления 1 (SP1) или Windows 7 с пакетом обновления 1 (SP1) необходимо следующее.

- Должен быть установлен последний пакет обновления.
- Платформа WMF 3.0 **не должна** быть установлена. Установка WMF 5.1 поверх WMF 3.0 приведет к потере **PSModulePath** (`$env:PSModulePath`), что может вызвать сбой других приложений. Перед установкой WMF 5.1 нужно удалить WMF 3.0 или сохранить **PSModulePath** и восстановить его вручную после установки WMF 5.1.
- WMF 5.1 требуется по крайней мере [.NET Framework 4.5.2](https://www.microsoft.com/download/details.aspx?id=42642). Вы можете установить Microsoft .NET Framework 4.5.2, выполнив следующие инструкции по месту скачивания.

### <a name="installing-wmf-51-on-windows-server-2008-r2-and-windows-7"></a>Установка WMF 5.1 на Windows Server 2008 R2 и Windows 7

1. Перейдите в папку, куда был скачан ZIP-файл.

1. Щелкните его правой кнопкой мыши и выберите команду **Извлечь все...** ZIP-файл содержит файл MSU и файл скрипта `Install-WMF5.1.ps1`. После распаковки ZIP-файла вы можете скопировать его содержимое на любой компьютер под управлением Windows 7 или Windows Server 2008 R2.

1. После извлечения содержимого ZIP-файла откройте PowerShell от имени администратора, а затем перейдите к папке с содержимым ZIP-файла.

1. Запустите скрипт `Install-WMF5.1.ps1` в этой папке и следуйте инструкциям. Этот скрипт проверит предварительные требования на локальном компьютере: если они выполнены, он установит WMF 5.1. Предварительные требования перечислены ниже.

   `Install-WMF5.1.ps1` принимает следующие параметры для упрощения автоматизации установки в Windows Server 2008 R2 и Windows 7:

   - **AcceptEula**: если этот параметр включен, условия EULA принимаются автоматически и не будут отображены.
   - **AllowRestart**: этот параметр можно использовать, только если указан параметр AcceptEula. Если этот параметр включен и после установки WMF 5.1 требуется перезагрузка, она будет выполнена без запроса сразу после завершения установки.

## <a name="winrm-dependency"></a>Зависимость от WinRM

Служба настройки требуемого состояния (DSC) Windows PowerShell зависит от WinRM. По умолчанию WinRM не включен в Windows Server 2008 R2 и Windows 7. Чтобы включить WinRM, выполните команду `Set-WSManQuickConfig` в сеансе Windows PowerShell с повышенными привилегиями.

## <a name="install-wmf-51-for-windows-server-2012-r2-windows-server-2012-and-windows-81"></a>Установка WMF 5.1 для Windows Server 2012 R2, Windows Server 2012 и Windows 8.1

### <a name="install-from-windows-file-explorer"></a>Установка из проводника Windows

1. Перейдите в папку, куда был скачан MSU-файл.
1. Дважды щелкните этот файл для его запуска.

### <a name="installing-from-the-command-prompt"></a>Установка из командной строки

1. После скачивания подходящего пакета для архитектуры вашего компьютера откройте окно командной строки с повышенными правами (используйте "Запуск от имени администратора"). При выборе варианта "Установка основных серверных компонентов" для Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2 с пакетом обновления 1 (SP1) командная строка по умолчанию открывается с повышенными правами.
1. Перейдите в папку, куда был скачан или скопирован пакет установки WMF 5.1.
1. Выполните одну из следующих команд:
   - На компьютерах с ОС Windows Server 2012 R2 или Windows 8.1 (64-разрядная версия) выполните команду `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet /norestart`.
   - На компьютерах с ОС Windows Server 2012 выполните команду `W2K12-KB3191565-x64.msu /quiet /norestart`.
   - На компьютерах с ОС Windows 8.1 (32-разрядная версия) выполните команду `Win8.1-KB3191564-x86.msu /quiet /norestart`.

   > [!NOTE]
   > При установке WMF 5.1 требуется перезагрузка. Один параметр `/quiet` инициирует перезагрузку системы без предупреждения. Чтобы избежать перезагрузки, используйте параметр `/norestart`. Однако установка WMF 5.1 не будет выполнена, пока вы не перезагрузите систему.
