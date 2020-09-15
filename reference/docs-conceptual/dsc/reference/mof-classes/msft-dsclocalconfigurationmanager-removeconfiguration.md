---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод RemoveConfiguration
ms.openlocfilehash: ef15c873d8dfaf28e5cdeb611b72a70921c099be
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464355"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="162ea-103">Метод RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="162ea-103">RemoveConfiguration method</span></span>

<span data-ttu-id="162ea-104">Удаляет файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="162ea-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="162ea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="162ea-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="162ea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="162ea-106">Parameters</span></span>

<span data-ttu-id="162ea-107">**Stage** \[in\] Указывает, какой документ конфигурации необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="162ea-107">**Stage** \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="162ea-108">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="162ea-108">The following values are valid:</span></span>

|<span data-ttu-id="162ea-109">Значение</span><span class="sxs-lookup"><span data-stu-id="162ea-109">Value</span></span> |<span data-ttu-id="162ea-110">Описание</span><span class="sxs-lookup"><span data-stu-id="162ea-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="162ea-111">**1**</span><span class="sxs-lookup"><span data-stu-id="162ea-111">**1**</span></span> | <span data-ttu-id="162ea-112">Документ **текущей** конфигурации (current.mof).</span><span class="sxs-lookup"><span data-stu-id="162ea-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="162ea-113">**2**</span><span class="sxs-lookup"><span data-stu-id="162ea-113">**2**</span></span> | <span data-ttu-id="162ea-114">Документ **ожидающей** конфигурации (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="162ea-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="162ea-115">**4**</span><span class="sxs-lookup"><span data-stu-id="162ea-115">**4**</span></span> | <span data-ttu-id="162ea-116">Документ **предыдущей** конфигурации (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="162ea-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="162ea-117">*Force* \[in\] **true** для принудительного удаления конфигурации.</span><span class="sxs-lookup"><span data-stu-id="162ea-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="162ea-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="162ea-118">Return value</span></span>

<span data-ttu-id="162ea-119">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="162ea-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="162ea-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="162ea-120">Remarks</span></span>

<span data-ttu-id="162ea-121">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="162ea-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="162ea-122">Требования</span><span class="sxs-lookup"><span data-stu-id="162ea-122">Requirements</span></span>

<span data-ttu-id="162ea-123">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="162ea-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="162ea-124">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="162ea-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="162ea-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="162ea-125">See also</span></span>

[<span data-ttu-id="162ea-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="162ea-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
