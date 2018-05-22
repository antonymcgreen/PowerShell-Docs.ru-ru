---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: d2f9b7025d611912e119800408e25fcb66bc0228
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="82036-103">Метод RollBack класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="82036-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="82036-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="82036-104">Rolls back the configuration to a previous version.</span></span>

<a name="syntax"></a><span data-ttu-id="82036-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82036-105">Syntax</span></span>
------

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

<a name="parameters"></a><span data-ttu-id="82036-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="82036-106">Parameters</span></span>
----------

<span data-ttu-id="82036-107">*configurationNumber* \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="82036-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="82036-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="82036-108">Return value</span></span>
------------

<span data-ttu-id="82036-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="82036-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="82036-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="82036-110">Remarks</span></span>

<span data-ttu-id="82036-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="82036-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="82036-112">Требования</span><span class="sxs-lookup"><span data-stu-id="82036-112">Requirements</span></span>
------------
><span data-ttu-id="82036-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="82036-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="82036-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="82036-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="82036-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="82036-115">See also</span></span>


[<span data-ttu-id="82036-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="82036-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)