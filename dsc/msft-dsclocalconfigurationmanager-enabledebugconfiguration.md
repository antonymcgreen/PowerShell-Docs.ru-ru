---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b2eaebfa901cb5d93fd0183287073e6b31f975d1
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892405"
---
# <a name="enabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b1506-103">Метод EnableDebugConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="b1506-103">EnableDebugConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b1506-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="b1506-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1506-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1506-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="b1506-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1506-106">Parameters</span></span>

<span data-ttu-id="b1506-107">*BreakAll* \[in\] Устанавливает точку останова в каждой строке в сценарии ресурса.</span><span class="sxs-lookup"><span data-stu-id="b1506-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="b1506-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b1506-108">Return value</span></span>

<span data-ttu-id="b1506-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b1506-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1506-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="b1506-110">Remarks</span></span>

<span data-ttu-id="b1506-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="b1506-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1506-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b1506-112">Requirements</span></span>

<span data-ttu-id="b1506-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b1506-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b1506-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1506-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b1506-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1506-115">See also</span></span>

[<span data-ttu-id="b1506-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b1506-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)