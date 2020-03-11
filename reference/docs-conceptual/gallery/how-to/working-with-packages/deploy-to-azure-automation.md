---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Развертывание в службу автоматизации Azure
ms.openlocfilehash: 5d09a0777c59b642400d683c8cb6f881319fb881
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278755"
---
# <a name="deploy-to-azure-automation"></a>Развертывание в службу автоматизации Azure

Кнопкой "Развернуть в службе автоматизации Azure" на странице сведений о пакете можно развернуть пакет из коллекции PowerShell в службе автоматизации Azure.

![Кнопка "Развернуть в службе автоматизации Azure"](media/deploy-to-azure-automation/DeployToAzureAutomationButton.png)

При нажатии этой кнопки вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure.
Если пакет имеет зависимости, все они будут также развернуты в службе автоматизации Azure.

> [!WARNING]
> Если в вашей учетной записи службы автоматизации уже существует такой пакет с той же версией, его повторное развертывание из коллекции PowerShell приведет к перезаписи существующего пакета в учетной записи службы автоматизации.

При развертывании модуля он будет отображаться в разделе модулей службы автоматизации Azure.  При развертывании скрипта он будет отображаться в разделе модулей Runbook службы автоматизации Azure.

Кнопку "Развернуть в службе автоматизации Azure" можно отключить, добавив тег AzureAutomationNotSupported в метаданные пакета.

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure

Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии. Нажав кнопку "ОК", вы принимаете условия лицензии".

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](media/deploy-to-azure-automation/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>Дополнительные сведения

- [Запрос на принятие условий лицензии в PowerShellGet](../../concepts/module-license-acceptance.md)
- [Запрос на принятие условий лицензии в коллекции PowerShell](packages-that-require-license-acceptance.md)
- [Веб-сайт службы автоматизации Azure](https://azure.microsoft.com/services/automation/)
