---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationResultOutput
ms.openlocfilehash: 9c81082c28b2ffcc329264d29784782deaa9779d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464083"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="b4329-103">Метод GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="b4329-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="b4329-104">Получает выходные данные агента конфигурации, относящиеся к определенному заданию.</span><span class="sxs-lookup"><span data-stu-id="b4329-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4329-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4329-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="b4329-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4329-106">Parameters</span></span>

<span data-ttu-id="b4329-107">**jobId** \[in\] Идентификатор задания, для которого необходимо получить выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b4329-107">**jobId** \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="b4329-108">**resumeOutputBookmark** \[in\] Указывает, что выходные данные должны быть продолжением предыдущей закладки.</span><span class="sxs-lookup"><span data-stu-id="b4329-108">**resumeOutputBookmark** \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="b4329-109">**output** \[out\] Выходные данные для указанного задания.</span><span class="sxs-lookup"><span data-stu-id="b4329-109">**output** \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4329-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b4329-110">Return value</span></span>

<span data-ttu-id="b4329-111">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b4329-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4329-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4329-112">Remarks</span></span>

<span data-ttu-id="b4329-113">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="b4329-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4329-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b4329-114">Requirements</span></span>

<span data-ttu-id="b4329-115">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b4329-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b4329-116">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4329-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b4329-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4329-117">See also</span></span>

[<span data-ttu-id="b4329-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b4329-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
