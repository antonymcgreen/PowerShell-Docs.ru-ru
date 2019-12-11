---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953441"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="35bd4-103">Метод EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="35bd4-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="35bd4-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="35bd4-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="35bd4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35bd4-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="35bd4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="35bd4-106">Parameters</span></span>

<span data-ttu-id="35bd4-107">*BreakAll* \[in\] Устанавливает точку останова в каждой строке в сценарии ресурса.</span><span class="sxs-lookup"><span data-stu-id="35bd4-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="35bd4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="35bd4-108">Return value</span></span>

<span data-ttu-id="35bd4-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="35bd4-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="35bd4-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="35bd4-110">Remarks</span></span>

<span data-ttu-id="35bd4-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="35bd4-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="35bd4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="35bd4-112">Requirements</span></span>

<span data-ttu-id="35bd4-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="35bd4-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="35bd4-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="35bd4-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="35bd4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="35bd4-115">See also</span></span>

[<span data-ttu-id="35bd4-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="35bd4-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
