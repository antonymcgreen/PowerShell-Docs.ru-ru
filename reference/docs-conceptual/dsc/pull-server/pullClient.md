---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента DSC
ms.openlocfilehash: 7c68f4c59170c672e7573de7e7e595a60a81c966
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561109"
---
# <a name="setting-up-a-dsc-pull-client"></a>Настройка опрашивающего клиента DSC

> Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Для каждого целевого узла нужно включить опрашивающий режим и указать URL-адрес или расположение файла для подключения к опрашивающему серверу, чтобы получать конфигурации и ресурсы, а также отправлять данные отчетов.

В следующих разделах показано, как настроить опрашивающие клиенты.

* [Настройка опрашивающего клиента с помощью имени конфигурации](pullClientConfigNames.md)
* [Настройка опрашивающего клиента с помощью идентификатора конфигурации](pullClientConfigID.md)

> [!NOTE]
> Эти разделы относятся к PowerShell 5.0. Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md).
