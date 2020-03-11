---
ms.date: 06/12/2017
contributor: Farehar
keywords: gallery,powershell,psgallery
title: Запрос на принятие условий лицензии
ms.openlocfilehash: 4b293ea693062cf9717fa4ca913c3eb9abaf7014
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278668"
---
# <a name="require-license-acceptance"></a>Запрос на принятие условий лицензии

На странице сведений об элементах модулей, для использования которых требуется принять условия лицензии, отображается соответствующий текст. Лицензию для модуля можно просмотреть, щелкнув ссылку View License.txt.

![Запрос на принятие условий лицензии](media/packages-that-require-license-acceptance/RequireLicenseAcceptance.png)

При установке, сохранении и обновлении модуля с помощью PowerShellGet или при развертывании в службе автоматизации Azure пользователям будет предложено принять условия лицензионного соглашения.

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure

Если для использования модуля, который развертывается в службе автоматизации Azure, нужно принять условия лицензионного соглашения, в пользовательском интерфейсе портала отобразится текст "Этот модуль требует принять условия лицензии. Нажав кнопку "ОК", вы принимаете условия лицензии".

![Запрос на принятие условий лицензии при развертывании в службе автоматизации Azure](media/packages-that-require-license-acceptance/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>Дополнительные сведения

[Запрос на принятие условий лицензии в PowerShellGet](../../concepts/module-license-acceptance.md)
[Веб-сайт службы автоматизации Azure](/azure/automation)
