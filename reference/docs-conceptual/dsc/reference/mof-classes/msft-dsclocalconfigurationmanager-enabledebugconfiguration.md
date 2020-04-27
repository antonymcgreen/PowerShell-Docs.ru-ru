---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953441"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="630f9-103">Метод EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="630f9-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="630f9-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="630f9-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="630f9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="630f9-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="630f9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="630f9-106">Parameters</span></span>

<span data-ttu-id="630f9-107">*BreakAll* \[in\] Устанавливает точку останова в каждой строке в скрипте ресурса.</span><span class="sxs-lookup"><span data-stu-id="630f9-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="630f9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="630f9-108">Return value</span></span>

<span data-ttu-id="630f9-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="630f9-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="630f9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="630f9-110">Remarks</span></span>

<span data-ttu-id="630f9-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="630f9-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="630f9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="630f9-112">Requirements</span></span>

<span data-ttu-id="630f9-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="630f9-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="630f9-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="630f9-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="630f9-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="630f9-115">See also</span></span>

[<span data-ttu-id="630f9-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="630f9-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
