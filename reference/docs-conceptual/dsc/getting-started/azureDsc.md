---
ms.date: 03/15/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование DSC в Microsoft Azure
ms.openlocfilehash: 6d71b69eea78e775a3e5aaac64bccfa10092b8e6
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870835"
---
# <a name="using-dsc-on-microsoft-azure"></a>Использование DSC в Microsoft Azure

Настройка требуемого состояния (DSC) поддерживается в Microsoft Azure при помощи [обработчика расширений настройки требуемого состояния Azure](/azure/virtual-machines/extensions/dsc-overview) и [DSC в службе автоматизации Azure](/azure/automation/automation-dsc-overview).

## <a name="azure-desired-state-configuration-extension-handler"></a>Обработчик расширения настройки требуемого состояния Azure

Расширение Azure DSC позволяет управлять виртуальными машинами, размещенным в Microsoft Azure, при помощи DSC. Дополнительные сведения см. в следующих разделах:

- [Обработчик расширения настройки требуемого состояния Azure](/azure/virtual-machines/extensions/dsc-overview)
- [Windows VMSS и настройка требуемого состояния при помощи шаблонов Azure Resource Manager](/azure/virtual-machines/extensions/dsc-template)
- [Передача учетных данных в обработчик расширения настройки требуемого состояния Azure](/azure/virtual-machines/extensions/dsc-credentials)
- [Журнал расширения Azure Desired State Configuration](azureDscexthistory.md)

## <a name="azure-automation-dsc"></a>DSC службы автоматизации Azure

[Служба автоматизации Azure](https://azure.microsoft.com/services/automation/) позволяет управлять конфигурациями DSC, ресурсами и управляемыми узлами из Azure. Дополнительные сведения см. в следующих разделах:

- [DSC в службе автоматизации Azure](/azure/automation/automation-dsc-overview)
- [Начало работы с DSC в службе автоматизации Azure](/azure/automation/automation-dsc-getting-started)
- [Подключение компьютеров для управления при помощи DSC в службе автоматизации Azure](/azure/automation/automation-dsc-onboarding)