---
title: Установка PowerShell Core в Windows
description: Сведения об установке PowerShell Core в Windows
ms.date: 08/06/2018
ms.openlocfilehash: e716e24ba47c0c109ab302b4b1a9254d7110ddef
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2019
ms.locfileid: "66471006"
---
# <a name="installing-powershell-core-on-windows"></a>Установка PowerShell Core в Windows

Есть несколько способов установки PowerShell Core в Windows.

## <a name="prerequisites"></a>Необходимые компоненты

Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:

- Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в версиях Windows, предшествующих Windows 10. Ее можно скачать самостоятельно или через Центр обновления Windows. Поддерживаемые системы, где установлены все исправления (включая дополнительные пакеты), уже содержат ее.
- Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2. Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/wmf/overview).

## <a name="a-idmsi-installing-the-msi-package"></a><a id="msi" />Установка пакета MSI

Чтобы установить PowerShell на клиент Windows или сервер Windows Server (поддерживаются Windows 7 с пакетом обновления 1 (SP1), Server 2008 R2 и более поздние версии), скачайте пакет MSI с нашей страницы [выпусков][] GitHub. Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить. Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.

MSI-файл имеет следующий вид: `PowerShell-<version>-win-<os-arch>.msi`.
<!-- TODO: should be updated to point to the Download Center as well -->

После скачивания дважды щелкните установщик и следуйте инструкциям на экране.

Программа установки создает ярлык в меню Windows "Пуск".

- По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.
- Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.

### <a name="administrative-install-from-the-command-line"></a>Установка администратором из командной строки

Пакеты MSI можно установить из командной строки. Это позволяет администраторам развертывать пакеты без участия пользователя. Пакет MSI для PowerShell включает в себя следующие свойства для управления параметрами установки:

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.
- **ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.
- **REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.

В следующих примерах показано, как выполнить автоматическую установку PowerShell Core со всеми включенными параметрами установки.

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

См. [полный список параметров командной строки для Msiexec.exe](/windows/desktop/Msi/command-line-options).

## <a name="a-idzip-installing-the-zip-package"></a><a id="zip" />Установка ZIP-пакета

Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell. Следует отметить, что при использовании ZIP-архива проверка предварительных условий, как в случае с пакетом MSI, не производится. Для правильной настройки удаленного взаимодействия с помощью WSMan необходимо выполнить [предварительные требования](#prerequisites).

## <a name="deploying-on-windows-iot"></a>Развертывание в Windows IoT

Windows IoT поставляется с Windows PowerShell, который будет использоваться для развертывания PowerShell Core 6.

1. Создайте `PSSession` для целевого устройства

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. Скопируйте ZIP-файл на устройство

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. Присоединитесь к устройству и извлеките архив

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. Удаленное взаимодействие в PowerShell Core 6

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. Подключение к конечной точке PowerShell Core 6 на устройстве

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a>Развертывание на Nano Server

Эти инструкции предполагают, что версия PowerShell уже запущена на образе Nano Server и была создана с помощью [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).
Nano Server является "виртуальной" ОС. Двоичные файлы ядра можно развернуть двумя разными методами.

1. Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.
2. В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.

В обоих случаях вам понадобится ZIP-пакет выпуска x64 Windows 10 и потребуется выполнять команды в экземпляре PowerShell с правами администратора.

### <a name="offline-deployment-of-powershell-core"></a>Автономное развертывание PowerShell Core

1. С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.
2. Отключите образ и загрузите его.
3. Подключитесь к входящему экземпляру Windows PowerShell.
4. Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).

### <a name="online-deployment-of-powershell-core"></a>Автономное PowerShell Core в сети

В следующих шагах описываются инструкции развертывания PowerShell Core в запущенном экземпляре Nano Server, а также настройка его удаленной конечной точки.

- Подключитесь к входящему экземпляру Windows PowerShell:

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- Скопируйте файл на экземпляр Nano Server:

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- Войдите в сеанс:

  ```powershell
  Enter-PSSession $session
  ```

- Извлеките ZIP-файл

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).

## <a name="how-to-create-a-remoting-endpoint"></a>Создание конечной точки удаленного взаимодействия

PowerShell Core поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan. Дополнительная информация:

- [Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]
- [Удаленное взаимодействие с WSMan в PowerShell Core][wsman-remoting]

<!-- [download-center]: TODO -->
[releases]: https://github.com/PowerShell/PowerShell/releases [ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md [wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md [AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
