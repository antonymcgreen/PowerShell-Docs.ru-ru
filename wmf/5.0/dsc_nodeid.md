---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 7a1725e3858c59a6d31699add22b042359c48463
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680794"
---
# <a name="separation-of-node-and-configuration-ids"></a><span data-ttu-id="fef50-102">Разделение идентификаторов узла и конфигурации</span><span class="sxs-lookup"><span data-stu-id="fef50-102">Separation of Node and Configuration IDs</span></span>

## <a name="overview"></a><span data-ttu-id="fef50-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="fef50-103">Overview</span></span>

<span data-ttu-id="fef50-104">Чтобы повысить гибкость и удобство работы с DSC в режиме Pull, мы добавили в этот выпуск несколько функций.</span><span class="sxs-lookup"><span data-stu-id="fef50-104">In order to provide a more flexible and streamlined experience when using DSC in Pull mode, we have added a number of features in this release.</span></span> <span data-ttu-id="fef50-105">Они упрощают настройку и развертывание конфигураций на нескольких узлах и позволяют сохранить возможность отслеживания состояния и отчетов для каждого узла в отдельности.</span><span class="sxs-lookup"><span data-stu-id="fef50-105">These features are intended to allow you to have the flexibility to easily setup and deploy configurations across multiple nodes, while still tracking status and reporting information for each node individually.</span></span>
<span data-ttu-id="fef50-106">Эти функции представлены ниже:</span><span class="sxs-lookup"><span data-stu-id="fef50-106">These features are as follows:</span></span>

* <span data-ttu-id="fef50-107">Имя конфигурации, определяющее конфигурацию для компьютера.</span><span class="sxs-lookup"><span data-stu-id="fef50-107">A configuration name which identifies the configuration for a computer.</span></span> <span data-ttu-id="fef50-108">Это имя может совместно использоваться несколькими целевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="fef50-108">This name can be shared by multiple target nodes</span></span>
* <span data-ttu-id="fef50-109">Идентификатор агента, который однозначно идентифицирует отдельный узел.</span><span class="sxs-lookup"><span data-stu-id="fef50-109">An agent ID which uniquely identifies a single node</span></span>
* <span data-ttu-id="fef50-110">Этап регистрации, который имеет место только при первом подключении целевого узла к опрашивающему серверу.</span><span class="sxs-lookup"><span data-stu-id="fef50-110">A registration step which only occurs the first time a target node connects to a pull server</span></span>

<span data-ttu-id="fef50-111">**Примечание.** Эти функции были добавлены и не заменяют собой существующие функциональные возможности и механизмы извлечения.</span><span class="sxs-lookup"><span data-stu-id="fef50-111">**Note:** These features and functionality have been added and do not replace the existing pull features and concepts.</span></span> <span data-ttu-id="fef50-112">Как новые, так и старые функции можно использовать с опрашивающим сервером, входящим в состав этого выпуска.</span><span class="sxs-lookup"><span data-stu-id="fef50-112">You can use these new features or the older ones with the new pull server shipping in this release.</span></span>

<span data-ttu-id="fef50-113">Дополнительные сведения см. в разделе [Настройка опрашивающего клиента с использованием имен конфигураций](https://msdn.microsoft.com/powershell/dsc/pullclientconfignames).</span><span class="sxs-lookup"><span data-stu-id="fef50-113">For more information, see [Setting up a pull client using configuration names](https://msdn.microsoft.com/powershell/dsc/pullclientconfignames)</span></span>
