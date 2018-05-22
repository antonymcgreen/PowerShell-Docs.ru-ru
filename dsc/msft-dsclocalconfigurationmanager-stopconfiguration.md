---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод StopConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: aaed29cb81e2079c4673b621b81c52e109aa7b48
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="stopconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="d587f-103">Метод StopConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="d587f-103">StopConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="d587f-104">Останавливает выполняемое изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d587f-104">Stops the configuration change that is in progress.</span></span>

<a name="syntax"></a><span data-ttu-id="d587f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d587f-105">Syntax</span></span>
------

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="d587f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d587f-106">Parameters</span></span>
----------

<span data-ttu-id="d587f-107">*force* \[in\] **true** для принудительной остановки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d587f-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="d587f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d587f-108">Return value</span></span>
------------

<span data-ttu-id="d587f-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d587f-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d587f-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="d587f-110">Remarks</span></span>

<span data-ttu-id="d587f-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="d587f-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d587f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d587f-112">Requirements</span></span>
------------
><span data-ttu-id="d587f-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="d587f-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="d587f-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d587f-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="d587f-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d587f-115">See also</span></span>


[<span data-ttu-id="d587f-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="d587f-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)