---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Класс MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 09b30edd48384c0e8412e0e6ee926a719249c5b8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953271"
---
# <a name="msft_dsclocalconfigurationmanager-class"></a><span data-ttu-id="fa02c-103">Класс MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="fa02c-103">MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="fa02c-104">Локальный диспетчер конфигураций (LCM) управляет состоянием файлов конфигурации и использует агент конфигурации для применения настроек.</span><span class="sxs-lookup"><span data-stu-id="fa02c-104">The Local Configuration Manager (LCM) that controls the states of configuration files and uses Configuration Agent to apply the configurations.</span></span>

<span data-ttu-id="fa02c-105">Следующий пример синтаксиса — упрощенный MOF-код, который включает все наследуемые свойства.</span><span class="sxs-lookup"><span data-stu-id="fa02c-105">The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa02c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa02c-106">Syntax</span></span>

```
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a><span data-ttu-id="fa02c-107">Члены группы</span><span class="sxs-lookup"><span data-stu-id="fa02c-107">Members</span></span>

<span data-ttu-id="fa02c-108">Класс **MSFT_DSCLocalConfigurationManager** включает следующие члены:</span><span class="sxs-lookup"><span data-stu-id="fa02c-108">The **MSFT_DSCLocalConfigurationManager** class has the following members:</span></span>

- <span data-ttu-id="fa02c-109">[Методы][]</span><span class="sxs-lookup"><span data-stu-id="fa02c-109">[Methods][]</span></span>

### <a name="methods"></a><span data-ttu-id="fa02c-110">Методы</span><span class="sxs-lookup"><span data-stu-id="fa02c-110">Methods</span></span>

<span data-ttu-id="fa02c-111">Класс **MSFT_DSCLocalConfigurationManager** включает следующие методы:</span><span class="sxs-lookup"><span data-stu-id="fa02c-111">The **MSFT_DSCLocalConfigurationManager** class has these methods.</span></span>

|<span data-ttu-id="fa02c-112">Метод</span><span class="sxs-lookup"><span data-stu-id="fa02c-112">Method</span></span> |<span data-ttu-id="fa02c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fa02c-113">Description</span></span> |
|:--- |:---|
| [<span data-ttu-id="fa02c-114">ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-114">ApplyConfiguration</span></span>](msft-dsclocalconfigurationmanager-applyconfiguration.md)| <span data-ttu-id="fa02c-115">Использует агент конфигурации для применения конфигурации, которая находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="fa02c-115">Uses the Configuration Agent to apply the configuration that is pending.</span></span>|
| [<span data-ttu-id="fa02c-116">DisableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-116">DisableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| <span data-ttu-id="fa02c-117">Отключает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="fa02c-117">Disables DSC resource debugging.</span></span>|
| [<span data-ttu-id="fa02c-118">EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-118">EnableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| <span data-ttu-id="fa02c-119">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="fa02c-119">Enables DSC resource debugging.</span></span>|
| [<span data-ttu-id="fa02c-120">GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-120">GetConfiguration</span></span>](msft-dsclocalconfigurationmanager-getconfiguration.md)| <span data-ttu-id="fa02c-121">Отправляет документ конфигурации на управляемый узел и использует метод **Get** агента конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-121">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="fa02c-122">GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="fa02c-122">GetConfigurationResultOutput</span></span>](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| <span data-ttu-id="fa02c-123">Получает выходные данные агента конфигурации, относящиеся к определенному заданию.</span><span class="sxs-lookup"><span data-stu-id="fa02c-123">Gets the Configuration Agent output relating to a specific job.</span></span>|
| [<span data-ttu-id="fa02c-124">GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="fa02c-124">GetConfigurationStatus</span></span>](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| <span data-ttu-id="fa02c-125">Получает журнал состояния конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-125">Get the configuration status history.</span></span>|
| [<span data-ttu-id="fa02c-126">GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-126">GetMetaConfiguration</span></span>](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| <span data-ttu-id="fa02c-127">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-127">Gets the LCM settings that are used to control Configuration Agent.</span></span>|
| [<span data-ttu-id="fa02c-128">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="fa02c-128">PerformRequiredConfigurationChecks</span></span>](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| <span data-ttu-id="fa02c-129">Запускает проверку согласованности.</span><span class="sxs-lookup"><span data-stu-id="fa02c-129">Starts the consistency check.</span></span>|
| [<span data-ttu-id="fa02c-130">RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-130">RemoveConfiguration</span></span>](msft-dsclocalconfigurationmanager-removeconfiguration.md)| <span data-ttu-id="fa02c-131">Удаляет файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-131">Removes the configuration files.</span></span>|
| [<span data-ttu-id="fa02c-132">ResourceGet</span><span class="sxs-lookup"><span data-stu-id="fa02c-132">ResourceGet</span></span>](msft-dsclocalconfigurationmanager-resourceget.md)| <span data-ttu-id="fa02c-133">Напрямую вызывает метод **Get** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="fa02c-133">Directly calls the **Get** method of a DSC resource.</span></span>|
| [<span data-ttu-id="fa02c-134">ResourceSet</span><span class="sxs-lookup"><span data-stu-id="fa02c-134">ResourceSet</span></span>](msft-dsclocalconfigurationmanager-resourceset.md)| <span data-ttu-id="fa02c-135">Напрямую вызывает метод **Set** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="fa02c-135">Directly calls the **Set** method of a DSC resource.</span></span>|
| [<span data-ttu-id="fa02c-136">ResourceTest</span><span class="sxs-lookup"><span data-stu-id="fa02c-136">ResourceTest</span></span>](msft-dsclocalconfigurationmanager-resourcetest.md)| <span data-ttu-id="fa02c-137">Напрямую вызывает метод **Test** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="fa02c-137">Directly calls the **Test** method of a DSC resource.</span></span>|
| [<span data-ttu-id="fa02c-138">RollBack</span><span class="sxs-lookup"><span data-stu-id="fa02c-138">RollBack</span></span>](msft-dsclocalconfigurationmanager-rollback.md)| <span data-ttu-id="fa02c-139">Выполняет откат к предыдущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-139">Rolls back to a previous configuration.</span></span>|
| [<span data-ttu-id="fa02c-140">SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-140">SendConfiguration</span></span>](msft-dsclocalconfigurationmanager-sendconfiguration.md)| <span data-ttu-id="fa02c-141">Отправляет документ конфигурации на управляемый узел и сохраняет его как ожидающее изменение.</span><span class="sxs-lookup"><span data-stu-id="fa02c-141">Sends the configuration document to the managed node and saves it as a pending change.</span></span>|
| [<span data-ttu-id="fa02c-142">SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="fa02c-142">SendConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| <span data-ttu-id="fa02c-143">Отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-143">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="fa02c-144">SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="fa02c-144">SendConfigurationApplyAsync</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| <span data-ttu-id="fa02c-145">Отправляет документ конфигурации на управляемый узел и запускает агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-145">Send the configuration document to the managed node and start using the Configuration Agent to apply the configuration.</span></span> <span data-ttu-id="fa02c-146">Для получения выходных данных используется метод GetConfigurationResultOutput.</span><span class="sxs-lookup"><span data-stu-id="fa02c-146">Use GetConfigurationResultOutput to retrieve result output.</span></span>|
| [<span data-ttu-id="fa02c-147">SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="fa02c-147">SendMetaConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| <span data-ttu-id="fa02c-148">Задает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa02c-148">Sets the LCM settings that are used to control the Configuration Agent.</span></span>|
| [<span data-ttu-id="fa02c-149">StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-149">StopConfiguration</span></span>](msft-dsclocalconfigurationmanager-stopconfiguration.md)| <span data-ttu-id="fa02c-150">Останавливает выполняемую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="fa02c-150">Stops the configuration that is in progress.</span></span>|
| [<span data-ttu-id="fa02c-151">TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-151">TestConfiguration</span></span>](msft-dsclocalconfigurationmanager-testconfiguration.md)| <span data-ttu-id="fa02c-152">Отправляет документ конфигурации на управляемый узел и проверяет соответствие текущей конфигурации документу.</span><span class="sxs-lookup"><span data-stu-id="fa02c-152">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>|

## <a name="requirements"></a><span data-ttu-id="fa02c-153">Требования</span><span class="sxs-lookup"><span data-stu-id="fa02c-153">Requirements</span></span>

<span data-ttu-id="fa02c-154">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="fa02c-154">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="fa02c-155">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa02c-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>
