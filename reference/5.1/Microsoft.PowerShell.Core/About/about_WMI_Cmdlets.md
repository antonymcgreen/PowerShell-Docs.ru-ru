---
description: Содержит общие сведения об инструментарии управления Windows (WMI) и Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232261"
---
# <a name="about-wmi-cmdlets"></a>Сведения о командлетах WMI

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Содержит общие сведения об инструментарии управления Windows (WMI) и Windows PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

В этом разделе содержатся сведения о технологии WMI, командлетах WMI для Windows PowerShell, удаленном взаимодействии на основе WMI, ускорителях WMI и устранении неполадок WMI. В этом разделе также приведены ссылки на дополнительные сведения об инструментарии WMI.

### <a name="about-wmi"></a>СВЕДЕНИЯ ОБ ИНСТРУМЕНТАРИИ WMI

Инструментарий управления Windows (WMI) разработан корпорацией Майкрософт в рамках отраслевой инициативы управления предприятием через Интернет (WBEM), целью которой является создание стандартной технологии получения доступа к информации по управлению в среде предприятия. В инструментарии WMI используется модель CIM — отраслевой стандарт, служащий для представления систем, приложений, сетей, устройств и других управляемых компонентов. Модель CIM разработана и обслуживается организацией Distributed Management Task Force (DMTF). Инструментарий WMI можно использовать для управления локальными и удаленными компьютерами. Например, Инструментарий WMI можно использовать для следующих задач:

- Запуск процесса на удаленном компьютере.
- Удаленная перезагрузка компьютера.
- Получение списка приложений, установленных на локальном или удаленном компьютере.
- Запросите журналы событий Windows на локальном или удаленном компьютере.

### <a name="the-wmi-cmdlets-for-windows-powershell"></a>КОМАНДЛЕТЫ WMI ДЛЯ WINDOWS POWERSHELL

Windows PowerShell реализует функциональные возможности WMI с помощью набора командлетов, которые по умолчанию доступны в Windows PowerShell. Эти командлеты можно использовать для выполнения комплексных задач, необходимых для управления локальными и удаленными компьютерами.

Включены следующие командлеты WMI.

|Командлет           |Описание                                   |
|-----------------|----------------------------------------------|
|Get-WmiObject    |Возвращает экземпляры классов или сведений WMI  |
|                 |сведения о доступных классах.                  |
|Invoke-WmiMethod |Вызывает методы WMI.                            |
|Register-WmiEvent|Подписывается на событие WMI.                    |
|Remove-WmiObject |Удаляет классы и экземпляры WMI.            |
|Set-WmiInstance  |Создает или изменяет экземпляры классов WMI. |

### <a name="sample-commands"></a>ПРИМЕРЫ КОМАНД
Следующая команда отображает сведения о BIOS для локального компьютера.

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

Следующая команда отображает сведения о службе WinRM для трех удаленных компьютеров.

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

Следующая более сложная команда завершает работу всех экземпляров программы.

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a>УДАЛЕННОЕ ВЗАИМОДЕЙСТВИЕ НА ОСНОВЕ ИНСТРУМЕНТАРИЯ WMI

Хотя возможность управлять локальной системой через WMI полезна, она является возможностью удаленного взаимодействия, которая делает инструментарий WMI мощным средством администрирования. WMI использует распределенную модель объектов (DCOM) Майкрософт для подключения к системам и управления ими. Возможно, потребуется настроить некоторые системы, чтобы разрешить подключения DCOM.
Параметры брандмауэра и заблокированные разрешения DCOM могут блокировать возможность инструментария WMI удаленно управлять системами.

### <a name="wmi-type-accelerators"></a>УСКОРИТЕЛИ ТИПОВ WMI

Windows PowerShell включает в себя ускорители типов WMI. Эти ускорители типов WMI (ярлыки) обеспечивают более прямой доступ к объектам WMI, чем при использовании ускорителя, отличного от типа.

Инструментарий WMI поддерживает следующие ускорители типов:

[ВМИСЕАРЧЕР] — ярлык для поиска объектов WMI.

[WMICLASS] — ярлык для доступа к статическим свойствам и методам класса.

[WMI] — ярлык для получения одного экземпляра класса.

[ВМИСЕАРЧЕР] — это ускоритель типов для Манажементобжектсеарчер. Для создания поискового запроса, который затем можно выполнить с помощью инструкции GET (), можно воспользоваться конструктором строк.

Пример:

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

[WMICLASS] — это ускоритель типов для Манажементкласс. Он имеет конструктор строк, который принимает локальный или абсолютный путь WMI к классу WMI и возвращает объект, привязанный к этому классу.

Пример:

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

[WMI] является ускорителем типов для ManagementObject. Он имеет конструктор строк, который принимает локальный или абсолютный путь WMI к экземпляру WMI и возвращает объект, привязанный к этому экземпляру.

Пример:

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a>УСТРАНЕНИЕ НЕПОЛАДОК WMI

Ниже перечислены наиболее распространенные проблемы, которые могут возникнуть при попытке подключения к удаленному компьютеру.

Проблема 1. удаленный компьютер не подключен к сети.

Если компьютер находится в автономном режиме, вы не сможете подключиться к нему с помощью инструментария WMI.
Может появиться следующее сообщение об ошибке:

```
Remote server machine does not exist or is unavailable
```

При появлении этого сообщения об ошибке убедитесь, что компьютер подключен к сети. Попробуйте проверить связь с удаленным компьютером.

Проблема 2. у вас нет прав локального администратора на удаленном компьютере.

Чтобы использовать инструментарий WMI удаленно, необходимо иметь права локального администратора на удаленном компьютере. В противном случае доступ к этому компьютеру будет запрещен.

Чтобы проверить безопасность пространства имен, сделайте следующее:

1. Нажмите кнопку Пуск, щелкните правой кнопкой мыши Мой компьютер, а затем выберите пункт Управление.
2. В окне "Управление компьютером" разверните узел "службы и приложения", щелкните правой кнопкой мыши элемент управления WMI и выберите пункт "Свойства".
3. В диалоговом окне Свойства элемента управления WMI перейдите на вкладку Безопасность.

Проблема 3. брандмауэр блокирует доступ к удаленному компьютеру.

Для обхода сети Инструментарий WMI использует протокол DCOM (Distributed COM) и RPC (удаленный вызов процедур). По умолчанию многие брандмауэры блокируют трафик DCOM и RPC. Если брандмауэр блокирует эти протоколы, произойдет сбой подключения. Например, брандмауэр Windows в Microsoft Windows XP с пакетом обновления 2 (SP2) настроен на автоматическую блокировку всех нежелательных сетевых трафика, включая DCOM и WMI. В конфигурации по умолчанию брандмауэр Windows отклоняет входящий запрос WMI и появляется следующее сообщение об ошибке:

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[Сведения об инструментарии WMI](/windows/win32/wmisdk/about-wmi)

[Устранение неполадок WMI](/windows/win32/wmisdk/wmi-troubleshooting).

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[Invoke-WmiMethod](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[Register-WmiEvent](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[Remove-WmiObject](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[Set-WmiInstance](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
