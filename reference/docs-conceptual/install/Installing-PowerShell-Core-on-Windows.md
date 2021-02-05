---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 02/02/2021
ms.openlocfilehash: befc5ff156cb7c3843d89e394e903778682ba28e
ms.sourcegitcommit: 40b6d8e9b6d791ac69e2ff85224e900b21552bc1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "99536496"
---
# <a name="installing-powershell-on-windows"></a>Установка PowerShell в Windows

Есть несколько способов установки PowerShell в Windows.

## <a name="prerequisites"></a>Предварительные требования

Последний выпуск PowerShell поддерживается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 R2 и более поздних версий.

Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:

- Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в Windows предшествующих Windows 10 версий. Ее можно скачать самостоятельно или через Центр обновления Windows. Этот пакет уже установлен в полностью исправленных системах.
- Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2. Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).

## <a name="download-the-installer-package"></a>Скачивание скрипта установщика

Чтобы установить PowerShell в Windows скачайте [актуальный][] пакет установки с GitHub. Также доступна актуальная [предварительная версия][]. Прокрутите страницу вниз до раздела **ресурсов**. Раздел **ресурсов** может быть свернут. В таком случае щелкните его, чтобы развернуть.

## <a name="installing-the-msi-package"></a><a id="msi" />Установка пакета MSI

MSI-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msi`. Пример:

- `PowerShell-7.1.1-win-x64.msi`
- `PowerShell-7.1.1-win-x86.msi`

После скачивания дважды щелкните установщик и следуйте инструкциям на экране.

Программа установки создает ярлык в меню Windows "Пуск".

- По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.
- Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.

> [!NOTE]
> PowerShell 7.1 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.
> PowerShell 7.1 устанавливается как обновление на месте взамен PowerShell 6.x или PowerShell 7.0.
>
> - PowerShell 7.1 устанавливается в папке `$env:ProgramFiles\PowerShell\7`.
> - Папка `$env:ProgramFiles\PowerShell\7` добавляется в переменную `$env:PATH`.
> - Папка `$env:ProgramFiles\PowerShell\6` удалена.
>
> Если вам нужно запустить PowerShell 7.1 параллельно с другими версиями, используйте метод [установки ZIP-архива](#zip), чтобы установить новую версию в другую папку.

### <a name="administrative-install-from-the-command-line"></a>Установка администратором из командной строки

MSI-пакеты можно устанавливать из командной строки, что позволяет администраторам развертывать их без взаимодействия с пользователем. MSI-пакет включает в себя следующие свойства для управления параметрами установки:

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.
- **ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL**. Это свойство позволяет добавлять пункт **Выполнить с помощью PowerShell** в контекстное меню проводника Windows.
- **ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.
- **REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.

В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами.

```powershell
msiexec.exe /package PowerShell-7.1.1-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

Полный список параметров командной строки для `Msiexec.exe` см. [здесь](/windows/desktop/Msi/command-line-options).

### <a name="registry-keys-created-during-installation"></a>Разделы реестра, созданные во время установки

Начиная с версии PowerShell 7.1, пакет MSI создает разделы реестра, которые хранят данные о расположении установки и версии PowerShell. Эти значения можно найти в разделе `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`. Значение `<GUID>` уникально для каждого типа сборки (выпуск или предварительная версия), основного номера версии и архитектуры.

|    Release    | Architecture |                                          Ключ реестра                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| Выпуск версии 7.1.x |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| Выпуск версии 7.1.x |     X64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| Предварительная версия 7.1.x |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| Предварительная версия 7.1.x |     X64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

Может использоваться администраторами и разработчиками для поиска пути к PowerShell. Значения `<GUID>` будут одинаковыми для всех выпусков предварительных и дополнительных версий. Значения `<GUID>` отличаются для каждого выпуска основной версии.

## <a name="installing-the-zip-package"></a><a id="zip" />Установка ZIP-пакета

Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell. Скачайте один из следующих ZIP-архивов на странице с [выпусками][выпуски].

- PowerShell-7.1.1-win-x64.zip
- PowerShell-7.1.1-win-x86.zip
- PowerShell-7.1.1-win-arm64.zip
- PowerShell-7.1.1-win-arm32.zip

В зависимости от способа загрузки файла может потребоваться разблокировать файл с помощью командлета `Unblock-File`. Распакуйте содержимое в выбранное расположение и запустите `pwsh.exe`. В отличие от установки пакетов MSI при установке ZIP-архива не выполняется проверка соответствия предварительным требованиям. Для правильного удаленного взаимодействия с помощью WSMan необходимо обеспечить соответствие [предварительным требованиям](#prerequisites).

Используйте этот метод для установки версии PowerShell на основе ARM на таких компьютерах, как Microsoft Surface Pro X. Чтобы получить оптимальные результаты, устанавливайте PowerShell в папку `$env:ProgramFiles\PowerShell\7`.

## <a name="deploying-on-windows-10-iot-enterprise"></a>Развертывание в Windows 10 IoT Корпоративная

Windows 10 IoT Корпоративная поставляется со средой Windows PowerShell, которую можно использовать для развертывания PowerShell 7.

1. Создайте `PSSession` для целевого устройства

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. Скопируйте ZIP-файл на устройство

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. Присоединитесь к устройству и извлеките архив

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. Настройте удаленное взаимодействие с PowerShell 7

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. Подключение к конечной точке PowerShell 7 на устройстве

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a>Развертывание в Windows 10 IoT Базовая

Windows PowerShell добавляется в Windows 10 IoT Базовая, если вы включаете функцию _IOT_POWERSHELL_, которую можно использовать для развертывания PowerShell 7. Действия, описанные выше для Windows 10 IoT Корпоративная, могут быть выполнены и для центра Интернета вещей.

Чтобы добавить последнюю версию PowerShell в образ для доставки, используйте команду [Import-PSCoreRelease][] для включения пакета в рабочую область и добавления _OPENSRC_POWERSHELL_ в образ.

> [!NOTE]
> В архитектуре ARM64 Windows PowerShell не добавляется при включении _IOT_POWERSHELL_. Поэтому установка на основе ZIP-файла не поддерживается. Для добавления в образ используйте команду `Import-PSCoreRelease`.

## <a name="deploying-on-nano-server"></a>Развертывание на Nano Server

В этих указаниях предполагается, что Nano Server — это операционная система для удаленного управления, в которой уже работает какая-либо версия PowerShell. Дополнительные сведения см. в разделе о [средстве создания образов Nano Server](/windows-server/get-started/deploy-nano-server).

Двоичные файлы PowerShell можно развернуть двумя разными способами:

1. Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.
1. В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.

В обоих случаях требуется ZIP-пакет выпуска Windows 10 семейства x64. Выполните команды в экземпляре PowerShell с ролью администратора.

### <a name="offline-deployment-of-powershell"></a>Автономное развертывание PowerShell

1. С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.
1. Отключите образ и загрузите его.
1. Подключитесь к встроенному экземпляру Windows PowerShell.
1. Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].

### <a name="online-deployment-of-powershell"></a>Автономное PowerShell в сети

Разверните PowerShell в Nano Server, выполнив действия ниже.

- Подключитесь к встроенному экземпляру Windows PowerShell.

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

- Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].

## <a name="install-as-a-net-global-tool"></a>Установка в качестве глобального средства .NET

Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`. Но в выполняющейся оболочке нет обновленной переменной `$env:PATH`. Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.

## <a name="install-powershell-via-winget"></a>Установка PowerShell через Winget

Программа командной строки `winget` позволяет разработчикам обнаруживать, устанавливать, обновлять, удалять и настраивать приложения на компьютерах Windows 10. Она является клиентским интерфейсом для службы Диспетчера пакетов Windows.

> [!NOTE]
> В настоящее время инструмент `winget` предоставляется в предварительной версии. Сейчас доступны не все запланированные функции.
> Не используйте этот метод в сценарии развертывания в рабочей среде. Список системных требований и инструкции по установке см. в документации по [winget].

Для установки PowerShell с помощью опубликованных пакетов `winget` можно использовать следующие команды:

1. Найдите последнюю версию PowerShell.

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.1
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.1-preview.5
   ```

1. Установите версию PowerShell, используя параметр `--exact`.

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><a id="msix" />Установка из Microsoft Store

Версия PowerShell 7.1 опубликована в Microsoft Store. Этот выпуск PowerShell можно найти на веб-сайте [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) или в приложении Store в ОС Windows.

Пакет Microsoft Store обеспечивает следующие преимущества:

- автоматические обновления, встроенные в основной механизм Windows 10;
- интеграция с другими механизмами распространения программного обеспечения, такими как Intune и SCCM.

Ограничения

Пакеты MSIX выполняются в песочнице приложения, которая виртуализует доступ к некоторым расположениям в файловой системе и реестре.

- Все изменения реестра в разделе HKEY_CURRENT_USER при записи копируются в закрытое хранилище, отдельно для каждого пользователя и приложения. Таким образом, эти значения недоступны для других приложений.
- Параметры конфигурации системного уровня, хранящиеся в `$PSHOME`, нельзя изменить. Это относится и к конфигурации WSMAN. Это означает, что вы не сможете подключать удаленные сеансы к установкам PowerShell на основе хранилища. Поддерживаются конфигурации уровня пользователя и удаленное взаимодействие по SSH.

Подробнее см. [Основные сведения о работе упакованных классических приложений в Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).

### <a name="using-the-msix-package"></a>Использование пакета MSIX

> [!NOTE]
> Предварительные сборки PowerShell включают пакет MSIX. Пакет MSIX не поддерживается официально. Этот пакет создан исключительно для тестовых целей и только на период действия предварительной версии.

Чтобы вручную установить пакет MSIX на клиенте Windows 10, скачайте пакет MSIX на странице GitHub с [выпусками][выпуски]. Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить. Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.

MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`

Для установки пакета необходимо использовать командлет `Add-AppxPackage`.

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a>Создание конечной точки удаленного взаимодействия

PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan. Дополнительные сведения см. в разделе:

- [Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]
- [Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]

## <a name="upgrading-an-existing-installation"></a>Обновление существующей установки

Для получения оптимального результата при обновлении используйте тот же метод установки, который вы использовали при первой установке PowerShell. При использовании разных методов установки PowerShell устанавливается в разные расположения. Если вы не знаете, как была выполнена установка PowerShell, вы можете сравнить расположение установки со сведениями о пакетах из этой статьи. Если установка выполнена с помощью пакета MSI, эти сведения будут отображаться в разделе **Программы и компоненты** Панели управления.

## <a name="installation-support"></a>Поддержка установки

Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе. В других источниках могут быть доступны другие методы установки. Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.

<!-- link references -->

[предварительная версия]: https://aka.ms/powershell-release?tag=preview
[Актуальная]: https://aka.ms/powershell-release?tag=stable
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
["еще один метод экземпляра"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
