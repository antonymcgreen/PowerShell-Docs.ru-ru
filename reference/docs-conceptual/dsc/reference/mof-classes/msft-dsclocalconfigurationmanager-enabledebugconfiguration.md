---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration
ms.openlocfilehash: be75b1012f49db79eb75a68c6912ffd5772bf16f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464100"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="7cada-103">Метод EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cada-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="7cada-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="7cada-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="7cada-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7cada-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="7cada-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7cada-106">Parameters</span></span>

<span data-ttu-id="7cada-107">**BreakAll** \[in\] Устанавливает точку останова в каждой строке в скрипте ресурса.</span><span class="sxs-lookup"><span data-stu-id="7cada-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="7cada-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7cada-108">Return value</span></span>

<span data-ttu-id="7cada-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7cada-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7cada-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cada-110">Remarks</span></span>

<span data-ttu-id="7cada-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="7cada-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7cada-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7cada-112">Requirements</span></span>

<span data-ttu-id="7cada-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7cada-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="7cada-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cada-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="7cada-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7cada-115">See also</span></span>

[<span data-ttu-id="7cada-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7cada-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
