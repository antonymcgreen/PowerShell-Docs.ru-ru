---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RemoveConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 03555cc73da1272bdebebc3d93b26aaf8fabc18e
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892690"
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="f1627-103">Метод RemoveConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="f1627-103">RemoveConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="f1627-104">Удаляет файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f1627-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1627-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1627-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="f1627-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1627-106">Parameters</span></span>

<span data-ttu-id="f1627-107">*Stage* \[in\] Указывает, какой документ конфигурации необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="f1627-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="f1627-108">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f1627-108">The following values are valid:</span></span>

|<span data-ttu-id="f1627-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f1627-109">Value</span></span> |<span data-ttu-id="f1627-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f1627-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="f1627-111">**1**</span><span class="sxs-lookup"><span data-stu-id="f1627-111">**1**</span></span> | <span data-ttu-id="f1627-112">Документ **текущей** конфигурации (current.mof).</span><span class="sxs-lookup"><span data-stu-id="f1627-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="f1627-113">**2**</span><span class="sxs-lookup"><span data-stu-id="f1627-113">**2**</span></span> | <span data-ttu-id="f1627-114">Документ **ожидающей** конфигурации (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="f1627-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="f1627-115">**4**</span><span class="sxs-lookup"><span data-stu-id="f1627-115">**4**</span></span> | <span data-ttu-id="f1627-116">Документ **предыдущей** конфигурации (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="f1627-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="f1627-117">*Force* \[in\] **true** для принудительного удаления конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f1627-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="f1627-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1627-118">Return value</span></span>

<span data-ttu-id="f1627-119">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f1627-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1627-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="f1627-120">Remarks</span></span>

<span data-ttu-id="f1627-121">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="f1627-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1627-122">Требования</span><span class="sxs-lookup"><span data-stu-id="f1627-122">Requirements</span></span>

<span data-ttu-id="f1627-123">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f1627-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f1627-124">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1627-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f1627-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1627-125">See also</span></span>

[<span data-ttu-id="f1627-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f1627-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)