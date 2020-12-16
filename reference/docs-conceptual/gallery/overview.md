---
ms.date: 12/01/2020
title: Коллекция PowerShell
description: Коллекция PowerShell — это центральный репозиторий для хранения модулей, скриптов PowerShell и ресурсов DSC.
ms.openlocfilehash: f1ce6a8e2d5d72ac14cf3e4854626ef612d27891
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470321"
---
# <a name="the-powershell-gallery"></a>Коллекция PowerShell

Коллекция PowerShell — это центральный репозиторий для хранения содержимого PowerShell. В ней можно найти полезные модули PowerShell с командами и ресурсы настройки требуемого состояния (DSC).
Здесь также представлены скрипты PowerShell, некоторые из которых могут содержать рабочие процессы PowerShell. Они описывают набор задач и реализуют конвейер для их выполнения. Некоторые из этих пакетов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.

## <a name="powershellget-overview"></a>Обзор PowerShellGet

Модуль PowerShellGet содержит командлеты для обнаружения, установки, обновления и публикации пакетов PowerShell, которые содержат такие артефакты, как модули, ресурсы DSC, возможности ролей и скрипты из [коллекции PowerShell](https://www.PowerShellGallery.com) и других частных репозиториев.

## <a name="getting-started-with-the-gallery"></a>Начало работы с коллекцией

Для установки пакетов из коллекции требуется последняя версия модуля PowerShellGet. Полные инструкции по установке см. в разделе [Установка PowerShellGet](installing-psget.md).

Дополнительные сведения об использовании команд PowerShellGet при работе с коллекцией см. в статье [Начало работы](getting-started.md). Вы также можете запустить командлет *Update-Help -Module PowerShellGet*, чтобы установить локальную справку по этим командам.

## <a name="supported-operating-systems"></a>Поддерживаемые операционные системы

Для модуля **PowerShellGet** требуется **PowerShell 3.0 или более поздней версии**.

Для **PowerShellGet** требуется .NET Framework 4.5 или более поздней версии. См. дополнительные сведения об [установке .NET Framework для разработчиков](/dotnet/framework/install/guide-for-developers).

Так как **PowerShell Core** является кроссплатформенным решением, которое работает в Windows, Linux и MacOS, это также означает поддержку **PowerShellGet** в этих системах. Полный список систем, поддерживаемых **PowerShell Core**, см. в руководстве по [установке PowerShell](/powershell/scripting/install/installing-powershell).

Много модулей, размещенных в коллекции, поддерживают различные ОС и имеют дополнительные требования.
Дополнительные сведения см. в документации по модулям.

## <a name="got-a-question-have-feedback"></a>Возник вопрос? Хотите поделиться мнением?

Дополнительные сведения о коллекции PowerShell и PowerShellGet см. на странице [Начало работы](getting-started.md).

Сведения о текущем состоянии служб коллекции PowerShell см. на странице [Состояние коллекции PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) на сайте GitHub.

Оставить отзыв или сообщить о проблеме можно в [репозитории GitHub](https://github.com/PowerShell/PowerShellGallery/issues).
