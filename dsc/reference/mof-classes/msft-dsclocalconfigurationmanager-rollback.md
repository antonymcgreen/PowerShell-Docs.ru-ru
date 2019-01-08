---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод RollBack класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 4956900ecd2c9cb7f2e2b5bcab94616f9f5d5565
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047732"
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b4228-103">Метод RollBack класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="b4228-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b4228-104">Выполняет откат конфигурации к предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="b4228-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4228-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4228-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="b4228-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4228-106">Parameters</span></span>

<span data-ttu-id="b4228-107">*configurationNumber* \[in\] Указывает запрошенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b4228-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4228-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b4228-108">Return value</span></span>

<span data-ttu-id="b4228-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b4228-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4228-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="b4228-110">Remarks</span></span>

<span data-ttu-id="b4228-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="b4228-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4228-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b4228-112">Requirements</span></span>

<span data-ttu-id="b4228-113">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b4228-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b4228-114">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4228-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b4228-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4228-115">See also</span></span>

[<span data-ttu-id="b4228-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b4228-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)