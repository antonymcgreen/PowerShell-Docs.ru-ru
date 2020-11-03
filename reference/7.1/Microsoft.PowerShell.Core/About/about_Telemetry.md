---
description: Описание данных телеметрии, собранных в PowerShell, и способов отказа от них.
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: ef921d0feefe277c2832c0a459ae150c9a6b4acb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231834"
---
# <a name="about-telemetry"></a>Сведения о телеметрии

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описание данных телеметрии, собранных в PowerShell, и способов отказа от них.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

PowerShell отправляет базовые данные телеметрии в корпорацию Майкрософт.
Они позволяют нам лучше понимать среды, где используется PowerShell, а также приоритизировать новые функции и исправления.
Записываются следующие точки телеметрии:

- Число запусков PowerShell по типу (консоль API VS)
- Число уникальных использований PowerShell
- Число следующих типов выполнения:
  - Приложение (собственные команды)
  - екстерналскрипт
  - Сценарий
  - Компонент
  - Командлет
- Число включенных экспериментальных функций Майкрософт или экспериментальных функций, поставляемых с PowerShell
- Число размещенных сеансов
- Число загруженных модулей, принадлежащих корпорации Майкрософт

Эти данные включают имя ОС, версию ОС, версию PowerShell и канал распространения.

Чтобы отказаться от этой телеметрии, задайте для переменной среды POWERSHELL_TELEMETRY_OPTOUT значение true, да или 1.

