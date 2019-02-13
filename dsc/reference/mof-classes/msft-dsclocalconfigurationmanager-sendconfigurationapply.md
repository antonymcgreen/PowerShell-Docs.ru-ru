---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfigurationApply класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: da3a08307122ab38ee4a6fd5d4a9b97579a988f7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680538"
---
# <a name="sendconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="d0fbc-103">Метод SendConfigurationApply класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="d0fbc-103">SendConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="d0fbc-104">Отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d0fbc-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0fbc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0fbc-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="d0fbc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0fbc-106">Parameters</span></span>

<span data-ttu-id="d0fbc-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d0fbc-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="d0fbc-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d0fbc-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="d0fbc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d0fbc-109">Return value</span></span>

<span data-ttu-id="d0fbc-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d0fbc-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0fbc-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="d0fbc-111">Remarks</span></span>

<span data-ttu-id="d0fbc-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="d0fbc-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0fbc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d0fbc-113">Requirements</span></span>

<span data-ttu-id="d0fbc-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="d0fbc-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="d0fbc-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d0fbc-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="d0fbc-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0fbc-116">See also</span></span>

[<span data-ttu-id="d0fbc-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="d0fbc-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)