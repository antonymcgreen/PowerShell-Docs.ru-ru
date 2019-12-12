---
ms.date: 10/16/2017
keywords: dsc,powershell,конфигурация,установка
title: Применение конфигураций
ms.openlocfilehash: 2a40f2055dda78cc0cb6cb05a5e14dce48be9d00
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953651"
---
# <a name="enacting-configurations"></a>Применение конфигураций

>Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

Настройку требуемого состояния PowerShell (DSC) можно применять двумя способами: в режиме принудительной отправки и в режиме опроса.

## <a name="push-mode"></a>Режим принудительной отправки

![Режим принудительной отправки](../images/pushModel.png "Принципы работы")

Режим принудительной отправки означает, что пользователь активно применяет конфигурацию к целевому узлу, вызывая командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).

Созданную и скомпилированную конфигурацию можно применить в режиме принудительной отправки, вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) и указав в качестве значения параметра -Path для этого командлета путь к MOF-файлу конфигурации.
Например, если MOF-файл конфигурации находится в каталоге `C:\DSC\Configurations\localhost.mof`, его можно применить на локальном компьютере, выполнив следующую команду: `Start-DscConfiguration -Path 'C:\DSC\Configurations'`

> __Примечание__. По умолчанию DSC выполняет конфигурацию в фоновом режиме. Для интерактивного выполнения конфигурации вызовите командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) с параметром __-wait__.

## <a name="pull-mode"></a>Режим опроса

![Режим запросов](../images/pullModel.png "Принципы работы")

В режиме опроса на опрашивающих клиентах настраивается получение конфигураций требуемого состояния из удаленной опрашивающей службы.
Опрашивающая служба при этом настраивается для размещения службы DSC. Затем производится подготовка с использованием конфигураций и ресурсов, которые требуются опрашивающим клиентам.
На каждом опрашивающем сервере задается расписание событий периодической проверки соответствия для конфигурации узла.
При первой активации события локальный диспетчер конфигураций (LCM) на опрашивающем клиенте отправляет в опрашивающую службу запрос на получение конфигурации, указанной в LCM.
Если такая конфигурация в опрашивающей службе обнаруживается и проходит начальные проверки допустимости, она скачивается на опрашивающий клиент, где LCM ее выполняет.

LCM регулярно проверяет, соответствует ли клиент конфигурации, в интервалы, заданные свойством **ConfigurationModeFrequencyMins** LCM.
LCM регулярно проверяет наличие обновленных конфигураций в опрашивающей службе с интервалами, заданными свойством LCM **RefreshModeFrequency**.
Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).

Рекомендуемое решение для размещения опрашивающей службы — облачная служба DSC, [служба автоматизации Azure](https://azure.microsoft.com/services/automation/).
Это размещенное решение, которое предоставляет возможности администрирования и создания отчетов с графическим представлением, а также централизованного управления.

Дополнительные сведения о настройке опрашивающей службы в Windows Server см. в разделе [Настройка опрашивающего веб-сервера DSC](pullServer.md).
Но помните, что функциональность этой реализации ограничена, и для интеграции требуются некоторые самостоятельные действия.

В следующих разделах описана опрашивающая служба и клиенты:

- [Обзор DSC службы автоматизации Azure](https://docs.microsoft.com/azure/automation/automation-dsc-overview).
- [Настройка опрашивающего SMB-сервера](pullServerSMB.md)
- [Настройка опрашивающего клиента](pullClientConfigID.md)