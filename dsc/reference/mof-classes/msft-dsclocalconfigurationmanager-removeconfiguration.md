---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RemoveConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 03555cc73da1272bdebebc3d93b26aaf8fabc18e
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047683"
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="a594b-103">Метод RemoveConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="a594b-103">RemoveConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="a594b-104">Удаляет файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a594b-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="a594b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a594b-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="a594b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a594b-106">Parameters</span></span>

<span data-ttu-id="a594b-107">*Stage* \[in\] Указывает, какой документ конфигурации необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="a594b-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="a594b-108">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a594b-108">The following values are valid:</span></span>

|<span data-ttu-id="a594b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="a594b-109">Value</span></span> |<span data-ttu-id="a594b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a594b-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="a594b-111">**1**</span><span class="sxs-lookup"><span data-stu-id="a594b-111">**1**</span></span> | <span data-ttu-id="a594b-112">Документ **текущей** конфигурации (current.mof).</span><span class="sxs-lookup"><span data-stu-id="a594b-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="a594b-113">**2**</span><span class="sxs-lookup"><span data-stu-id="a594b-113">**2**</span></span> | <span data-ttu-id="a594b-114">Документ **ожидающей** конфигурации (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="a594b-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="a594b-115">**4**</span><span class="sxs-lookup"><span data-stu-id="a594b-115">**4**</span></span> | <span data-ttu-id="a594b-116">Документ **предыдущей** конфигурации (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="a594b-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="a594b-117">*Force* \[in\] **true** для принудительного удаления конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a594b-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="a594b-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a594b-118">Return value</span></span>

<span data-ttu-id="a594b-119">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a594b-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a594b-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="a594b-120">Remarks</span></span>

<span data-ttu-id="a594b-121">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="a594b-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a594b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a594b-122">Requirements</span></span>

<span data-ttu-id="a594b-123">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a594b-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a594b-124">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a594b-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a594b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a594b-125">See also</span></span>

[<span data-ttu-id="a594b-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a594b-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)