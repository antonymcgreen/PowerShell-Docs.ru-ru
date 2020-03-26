---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 08/06/2018
ms.openlocfilehash: bb0971b6c4ac99bde70b226da2becf2f4ed82083
ms.sourcegitcommit: d36db3a1bc44aee6bc97422b557041c3aece4c67
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80082778"
---
# <a name="installing-powershell-on-windows"></a>Установка PowerShell в Windows

Есть несколько способов установки PowerShell в Windows.

## <a name="prerequisites"></a>Предварительные требования

Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:

- Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в версиях Windows, предшествующих Windows 10. Ее можно скачать самостоятельно или через Центр обновления Windows. Поддерживаемые системы, где установлены все исправления (включая дополнительные пакеты), уже содержат ее.
- Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2. Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).

## <a name="installing-the-msi-package"></a><a id="msi" />Установка пакета MSI

Чтобы установить PowerShell на клиенте Windows или в Windows Server (работает в Windows 7 с пакетом обновления 1 (SP1), Server 2008 R2 и более поздних версий), скачайте пакет MSI из с нашей страницы [выпусков][releases] GitHub. Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить. Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.

MSI-файл имеет следующий вид: `PowerShell-<version>-win-<os-arch>.msi`.

После скачивания дважды щелкните установщик и следуйте инструкциям на экране.

Программа установки создает ярлык в меню Windows "Пуск".

- По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.
- Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.

> [!NOTE]
> PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1. Для PowerShell Core 6.x версия PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.
>
> - PowerShell 7 устанавливается в папке `%programfiles%\PowerShell\7`.
> - Папка `%programfiles%\PowerShell\7` добавляется в переменную `$env:PATH`.
> - Папка `%programfiles%\PowerShell\6` удалена.
>
> Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [ZIP-архива](#zip).

### <a name="administrative-install-from-the-command-line"></a>Установка администратором из командной строки

Пакеты MSI можно установить из командной строки. Это позволяет администраторам развертывать пакеты без участия пользователя. Пакет MSI для PowerShell включает в себя следующие свойства для управления параметрами установки:

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.
- **ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.
- **REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.

В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами установки.

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

См. [полный список параметров командной строки для Msiexec.exe](/windows/desktop/Msi/command-line-options).

## <a name="installing-the-msix-package"></a><a id="msix" />Установка пакета MSIX

Чтобы вручную установить пакет MSIX на клиент Windows 10, скачайте пакет MSIX на странице GitHub с [выпусками][releases]. Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить. Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.

MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`

После скачивания вы не сможете просто дважды щелкнуть установщик, так как для этого пакета требуются невиртуализованные ресурсы.  Для установки используйте командлет `Add-AppxPackage`.

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><a id="zip" />Установка ZIP-пакета

Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell. Следует отметить, что при использовании ZIP-архива проверка предварительных условий, как в случае с пакетом MSI, не производится. Для правильной настройки удаленного взаимодействия с помощью WSMan необходимо выполнить [предварительные требования](#prerequisites).

## <a name="deploying-on-windows-iot"></a>Развертывание в Windows IoT

Windows IoT поставляется с Windows PowerShell, который можно использовать для развертывания PowerShell 7.

1. Создайте `PSSession` для целевого устройства

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
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

4. Удаленное взаимодействие в PowerShell 7

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. Подключение к конечной точке PowerShell 7 на устройстве

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a>Развертывание на Nano Server

Эти инструкции предполагают, что версия PowerShell уже запущена на образе Nano Server и была создана с помощью [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).
Nano Server является "виртуальной" ОС. Двоичные файлы PowerShell можно развернуть двумя разными способами.

1. Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.
2. В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.

В обоих случаях вам понадобится ZIP-пакет выпуска x64 Windows 10 и потребуется выполнять команды в экземпляре PowerShell с правами администратора.

### <a name="offline-deployment-of-powershell"></a>Автономное развертывание PowerShell

1. С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.
2. Отключите образ и загрузите его.
3. Подключитесь к входящему экземпляру Windows PowerShell.
4. Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).

### <a name="online-deployment-of-powershell"></a>Автономное PowerShell в сети

В следующих шагах описываются инструкции развертывания PowerShell на запущенном экземпляре Nano Server, а также настройка его удаленной конечной точки.

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
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).

## <a name="install-as-a-net-global-tool"></a>Установка в качестве глобального средства .NET

Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`. Но в выполняющейся оболочке отсутствует обновленная переменная `$env:PATH`. Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.

## <a name="how-to-create-a-remoting-endpoint"></a>Создание конечной точки удаленного взаимодействия

PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan. Дополнительные сведения см. в разделе:

- [Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]
- [Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
