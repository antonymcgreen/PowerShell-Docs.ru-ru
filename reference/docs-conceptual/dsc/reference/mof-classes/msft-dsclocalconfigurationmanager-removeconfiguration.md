---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RemoveConfiguration
ms.openlocfilehash: aacbed96beb960d7e0d449423a4de9a27f0a287e
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953401"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="e2985-103">Метод RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2985-103">RemoveConfiguration method</span></span>

<span data-ttu-id="e2985-104">Удаляет файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e2985-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2985-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2985-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="e2985-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2985-106">Parameters</span></span>

<span data-ttu-id="e2985-107">*Stage* \[in\] Указывает, какой документ конфигурации необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e2985-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="e2985-108">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e2985-108">The following values are valid:</span></span>

|<span data-ttu-id="e2985-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e2985-109">Value</span></span> |<span data-ttu-id="e2985-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e2985-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="e2985-111">**1**</span><span class="sxs-lookup"><span data-stu-id="e2985-111">**1**</span></span> | <span data-ttu-id="e2985-112">Документ **текущей** конфигурации (current.mof).</span><span class="sxs-lookup"><span data-stu-id="e2985-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="e2985-113">**2**</span><span class="sxs-lookup"><span data-stu-id="e2985-113">**2**</span></span> | <span data-ttu-id="e2985-114">Документ **ожидающей** конфигурации (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="e2985-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="e2985-115">**4**</span><span class="sxs-lookup"><span data-stu-id="e2985-115">**4**</span></span> | <span data-ttu-id="e2985-116">Документ **предыдущей** конфигурации (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="e2985-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="e2985-117">*Force* \[in\] **true** для принудительного удаления конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e2985-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="e2985-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2985-118">Return value</span></span>

<span data-ttu-id="e2985-119">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e2985-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2985-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e2985-120">Remarks</span></span>

<span data-ttu-id="e2985-121">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="e2985-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2985-122">Требования</span><span class="sxs-lookup"><span data-stu-id="e2985-122">Requirements</span></span>

<span data-ttu-id="e2985-123">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e2985-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e2985-124">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2985-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e2985-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2985-125">See also</span></span>

[<span data-ttu-id="e2985-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e2985-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
