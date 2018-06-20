---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 2d6b4e3045bc8cff90576c345d1ccb97b2487426
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225595"
---
# <a name="new-guid"></a><span data-ttu-id="8c731-102">New-Guid</span><span class="sxs-lookup"><span data-stu-id="8c731-102">New-Guid</span></span>
<span data-ttu-id="8c731-103">Часто в сценарии (или при создании ресурсов DSC) требуется уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="8c731-103">Often script (or perhaps writing a DSC resource), you have the need for a unique identifier.</span></span> <span data-ttu-id="8c731-104">Здесь можно использовать GUID, для создания которых достаточно вызвать класс Guid платформы .NET Framework, однако наличие командлета делает этот процесс более очевидным и удобным для конечных пользователей, которые еще не знакомы с данным классом .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8c731-104">GUIDs work well, and it is easy to call the .NET Framework Guid class to generate one, but having a cmdlet makes this more discoverable for end users who are not already familiar with the .NET Framework class:</span></span>

<span data-ttu-id="8c731-105">PS C:\\&gt; New-Guid</span><span class="sxs-lookup"><span data-stu-id="8c731-105">PS C:\\&gt; New-Guid</span></span>

<span data-ttu-id="8c731-106">GUID</span><span class="sxs-lookup"><span data-stu-id="8c731-106">Guid</span></span>

----

<span data-ttu-id="8c731-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span><span class="sxs-lookup"><span data-stu-id="8c731-107">e19d6ea5-3cc2-4db9-8095-0cdaed5a703d</span></span>
