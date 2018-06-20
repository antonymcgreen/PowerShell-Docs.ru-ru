---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод EnableDebugConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 9e2a978f9d16abaed959be022229db4da5fd65bd
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218201"
---
# <a name="enabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="0fdcb-103">Метод EnableDebugConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0fdcb-103">EnableDebugConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="0fdcb-104">Включает отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="0fdcb-104">Enables DSC resource debugging.</span></span>

<a name="syntax"></a><span data-ttu-id="0fdcb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fdcb-105">Syntax</span></span>
------

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

<a name="parameters"></a><span data-ttu-id="0fdcb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fdcb-106">Parameters</span></span>
----------

<span data-ttu-id="0fdcb-107">*BreakAll* \[in\] Устанавливает точку останова в каждой строке в сценарии ресурса.</span><span class="sxs-lookup"><span data-stu-id="0fdcb-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="0fdcb-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0fdcb-108">Return value</span></span>
------------

<span data-ttu-id="0fdcb-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0fdcb-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0fdcb-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="0fdcb-110">Remarks</span></span>

<span data-ttu-id="0fdcb-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="0fdcb-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0fdcb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0fdcb-112">Requirements</span></span>
------------
><span data-ttu-id="0fdcb-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0fdcb-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="0fdcb-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0fdcb-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="0fdcb-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fdcb-115">See also</span></span>


[<span data-ttu-id="0fdcb-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0fdcb-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)