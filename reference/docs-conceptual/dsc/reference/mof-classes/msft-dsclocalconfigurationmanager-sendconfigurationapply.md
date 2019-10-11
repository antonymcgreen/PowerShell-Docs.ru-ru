---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод SendConfigurationApply
ms.openlocfilehash: 11b9d435bbaac1600d25ff074b6c55b236a8378b
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954891"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="9e02b-103">Метод SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="9e02b-103">SendConfigurationApply method</span></span>

<span data-ttu-id="9e02b-104">Отправляет документ конфигурации на управляемый узел и использует агент конфигурации для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e02b-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e02b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e02b-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="9e02b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e02b-106">Parameters</span></span>

<span data-ttu-id="9e02b-107">*ConfigurationData* \[in\] Данные среды для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e02b-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="9e02b-108">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e02b-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="9e02b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e02b-109">Return value</span></span>

<span data-ttu-id="9e02b-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="9e02b-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e02b-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="9e02b-111">Remarks</span></span>

<span data-ttu-id="9e02b-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="9e02b-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e02b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9e02b-113">Requirements</span></span>

<span data-ttu-id="9e02b-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="9e02b-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="9e02b-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e02b-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="9e02b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e02b-116">See also</span></span>

[<span data-ttu-id="9e02b-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="9e02b-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
