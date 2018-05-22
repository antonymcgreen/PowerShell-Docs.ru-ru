---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationResultOutput класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 73d10a8b44e5056e3fce1598518630a84aff6ceb
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="89d02-103">Метод GetConfigurationResultOutput класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="89d02-103">GetConfigurationResultOutput method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="89d02-104">Получает выходные данные агента конфигурации, относящиеся к определенному заданию.</span><span class="sxs-lookup"><span data-stu-id="89d02-104">Gets the Configuration Agent output associated with a specific job.</span></span>

<a name="syntax"></a><span data-ttu-id="89d02-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89d02-105">Syntax</span></span>
------

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

<a name="parameters"></a><span data-ttu-id="89d02-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="89d02-106">Parameters</span></span>
----------

<span data-ttu-id="89d02-107">*jobId* \[in\] Идентификатор задания, для которого необходимо получить выходные данные.</span><span class="sxs-lookup"><span data-stu-id="89d02-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="89d02-108">*resumeOutputBookmark* \[in\] Указывает, что выходные данные должны быть продолжением от предыдущей закладки.</span><span class="sxs-lookup"><span data-stu-id="89d02-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="89d02-109">*output* \[out\] Выходные данные для указанного задания.</span><span class="sxs-lookup"><span data-stu-id="89d02-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="89d02-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89d02-110">Return value</span></span>
------------

<span data-ttu-id="89d02-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="89d02-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="89d02-112">Замечания</span><span class="sxs-lookup"><span data-stu-id="89d02-112">Remarks</span></span>

<span data-ttu-id="89d02-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="89d02-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="89d02-114">Требования</span><span class="sxs-lookup"><span data-stu-id="89d02-114">Requirements</span></span>
------------
><span data-ttu-id="89d02-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="89d02-115">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="89d02-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="89d02-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="89d02-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="89d02-117">See also</span></span>


[<span data-ttu-id="89d02-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="89d02-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)