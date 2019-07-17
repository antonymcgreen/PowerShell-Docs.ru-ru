---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727145"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="2f54d-103">Метод EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f54d-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="2f54d-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="2f54d-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f54d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f54d-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="2f54d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f54d-106">Parameters</span></span>

<span data-ttu-id="2f54d-107">*BreakAll* \[in\] Устанавливает точку останова в каждой строке в сценарии ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f54d-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="2f54d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f54d-108">Return value</span></span>

<span data-ttu-id="2f54d-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2f54d-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f54d-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="2f54d-110">Remarks</span></span>

<span data-ttu-id="2f54d-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="2f54d-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f54d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2f54d-112">Requirements</span></span>

<span data-ttu-id="2f54d-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2f54d-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2f54d-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f54d-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2f54d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f54d-115">See also</span></span>

[<span data-ttu-id="2f54d-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2f54d-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
