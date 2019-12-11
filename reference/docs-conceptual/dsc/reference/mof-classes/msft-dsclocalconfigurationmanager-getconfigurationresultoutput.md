---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationResultOutput
ms.openlocfilehash: 480e710ce1a208253f0e664474c3e9bab296066a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953421"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="f43b7-103">Метод GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="f43b7-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="f43b7-104">Получает выходные данные агента конфигурации, относящиеся к определенному заданию.</span><span class="sxs-lookup"><span data-stu-id="f43b7-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="f43b7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f43b7-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="f43b7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f43b7-106">Parameters</span></span>

<span data-ttu-id="f43b7-107">*jobId* \[in\] Идентификатор задания, для которого необходимо получить выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f43b7-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="f43b7-108">*resumeOutputBookmark* \[in\] Указывает, что выходные данные должны быть продолжением от предыдущей закладки.</span><span class="sxs-lookup"><span data-stu-id="f43b7-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="f43b7-109">*output* \[out\] Выходные данные для указанного задания.</span><span class="sxs-lookup"><span data-stu-id="f43b7-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="f43b7-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f43b7-110">Return value</span></span>

<span data-ttu-id="f43b7-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f43b7-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f43b7-112">Замечания</span><span class="sxs-lookup"><span data-stu-id="f43b7-112">Remarks</span></span>

<span data-ttu-id="f43b7-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="f43b7-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f43b7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f43b7-114">Requirements</span></span>

<span data-ttu-id="f43b7-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f43b7-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f43b7-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f43b7-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f43b7-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f43b7-117">See also</span></span>

[<span data-ttu-id="f43b7-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f43b7-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
