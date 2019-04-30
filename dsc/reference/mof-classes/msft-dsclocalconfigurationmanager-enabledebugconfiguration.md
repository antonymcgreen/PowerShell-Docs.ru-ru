---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b2eaebfa901cb5d93fd0183287073e6b31f975d1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078770"
---
# <a name="enabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="66418-103">Метод EnableDebugConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="66418-103">EnableDebugConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="66418-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="66418-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="66418-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66418-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="66418-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="66418-106">Parameters</span></span>

<span data-ttu-id="66418-107">*BreakAll* \[in\] Устанавливает точку останова в каждой строке в сценарии ресурса.</span><span class="sxs-lookup"><span data-stu-id="66418-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="66418-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66418-108">Return value</span></span>

<span data-ttu-id="66418-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="66418-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="66418-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="66418-110">Remarks</span></span>

<span data-ttu-id="66418-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="66418-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="66418-112">Требования</span><span class="sxs-lookup"><span data-stu-id="66418-112">Requirements</span></span>

<span data-ttu-id="66418-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="66418-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="66418-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="66418-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="66418-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="66418-115">See also</span></span>

[<span data-ttu-id="66418-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="66418-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)