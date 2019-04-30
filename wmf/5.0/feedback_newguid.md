---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 90fd26f9f27d2398da839b309c17b921bb3b8521
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085332"
---
# <a name="new-guid"></a><span data-ttu-id="ee5ae-102">New-Guid</span><span class="sxs-lookup"><span data-stu-id="ee5ae-102">New-Guid</span></span>
<span data-ttu-id="ee5ae-103">Часто в сценарии (или при создании ресурсов DSC) требуется уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="ee5ae-103">Often script (or perhaps writing a DSC resource), you have the need for a unique identifier.</span></span> <span data-ttu-id="ee5ae-104">Здесь можно использовать GUID, для создания которых достаточно вызвать класс Guid платформы .NET Framework, однако наличие командлета делает этот процесс более очевидным и удобным для конечных пользователей, которые еще не знакомы с данным классом .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ee5ae-104">GUIDs work well, and it is easy to call the .NET Framework Guid class to generate one, but having a cmdlet makes this more discoverable for end users who are not already familiar with the .NET Framework class:</span></span>

<span data-ttu-id="ee5ae-105">PS C:\\&gt; New-Guid</span><span class="sxs-lookup"><span data-stu-id="ee5ae-105">PS C:\\&gt; New-Guid</span></span>

<span data-ttu-id="ee5ae-106">GUID</span><span class="sxs-lookup"><span data-stu-id="ee5ae-106">Guid</span></span>

----

<span data-ttu-id="ee5ae-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span><span class="sxs-lookup"><span data-stu-id="ee5ae-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span></span>
