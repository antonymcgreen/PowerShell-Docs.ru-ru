---
ms.date: 06/12/2017
contributor: Farehar
keywords: gallery,powershell,psgallery
title: Запрос на принятие условий лицензии
ms.openlocfilehash: eaed248895d14bd455d2d8d3c2222d8848eeccae
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003903"
---
# <a name="require-license-acceptance"></a>Запрос на принятие условий лицензии

На странице сведений об элементах модулей, для использования которых требуется принять условия лицензии, отображается соответствующий текст. Лицензию для модуля можно просмотреть, щелкнув ссылку View License.txt.

![Запрос на принятие условий лицензии](../../Images/RequireLicenseAcceptance.png)

При установке, сохранении и обновлении модуля с помощью PowerShellGet или при развертывании в службе автоматизации Azure пользователям будет предложено принять условия лицензионного соглашения.

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure

Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии. Нажав кнопку "ОК", вы принимаете условия лицензии".

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>Дополнительные подробности

[Запрос на принятие условий лицензии в PowerShellGet](../../concepts/module-license-acceptance.md)
[Веб-сайт службы автоматизации Azure](/azure/automation)
