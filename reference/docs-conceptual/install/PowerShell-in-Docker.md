---
title: Использование PowerShell в Docker
description: Использование среды PowerShell, предварительно установленной в образе Docker.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: b16a31a04ca863ab55c7c9718b1a1a973e61ee46
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "80646377"
---
# <a name="using-powershell-in-docker"></a>Использование PowerShell в Docker

Корпорация Майкрософт публикует образы Docker с предварительной установкой PowerShell. В этой статье описывается, как приступить к работе с PowerShell в контейнере Docker.

## <a name="finding-available-images"></a>Поиск доступных образов

Для выпущенных образов требуется Docker 17.05 или более поздней версии. Также предполагается, что Docker можно запускать без `sudo` или прав локального администратора. Чтобы правильно установить [, следуйте официальным ][install]инструкциям`docker` Docker.

Контейнеры выпуска извлекают содержимое из официального распространяемого образа, например `centos:7`, затем устанавливают зависимости и, наконец, устанавливают пакет PowerShell.

Контейнеры находятся по адресу [hub.docker.com/r/microsoft/powershell][docker-release].

Чтобы получить дополнительные сведения об этих образах Docker, перейдите в репозиторий [PowerShell-Docker][PowerShell-Docker] на GitHub.

## <a name="using-powershell-in-a-container"></a>Использование PowerShell в контейнере

Ниже представлены команды Docker, необходимые для скачивания образа и запуска интерактивного сеанса PowerShell.

```console
docker run -it mcr.microsoft.com/powershell
```

### <a name="remove-the-image-when-no-longer-needed"></a>Удаление ненужного образа

Следующая команда используется для удаления образа Docker, который больше не нужен.

```console
docker rmi mcr.microsoft.com/powershell
```

## <a name="legal-and-licensing"></a>Правовая информация и лицензирование

PowerShell лицензируется на условиях [Лицензия MIT][].

### <a name="windows-docker-file-and-image-licenses"></a>Файл Windows Docker и лицензии на образы

Запрашивая и используя образ ОС контейнера для контейнеров Windows, вы признаете, что ознакомлены с Дополнительными условиями лицензионного соглашения, доступными в Docker Hub, и соглашаетесь с ними:

- [Window Server Core][Window Server Core]
- [Nano Server][Nano Server]

### <a name="telemetry"></a>Телеметрия

По умолчанию PowerShell собирает ограниченные данные телеметрии без личных сведений, которые могут помочь в разработке будущих версий PowerShell. Чтобы отказаться от отправки данных телеметрии, создайте переменную среды `POWERSHELL_TELEMETRY_OPTOUT` и присвойте ей значение `1` перед запуском PowerShell из места установки. На собираемые нами данные телеметрии распространяется [Заявление о конфиденциальности корпорации Майкрософт][privacy].

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[docker-release]: https://hub.docker.com/r/microsoft/powershell/
[appinsights]: https://azure.microsoft.com/services/application-insights/
[Лицензия MIT]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[PowerShell-Docker]: https://github.com/PowerShell/PowerShell-Docker
[Window Server Core]: https://hub.docker.com/r/microsoft/windowsservercore/
[Nano Server]: https://hub.docker.com/r/microsoft/nanoserver/
[privacy]: https://privacy.microsoft.com/privacystatement/
