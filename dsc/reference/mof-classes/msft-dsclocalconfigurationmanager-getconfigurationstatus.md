---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationStatus класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: c66ccc4eefaef2d0c3a68fa8a96c5abb9bda6e4c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078781"
---
# <a name="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="2e754-103">Метод GetConfigurationStatus класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="2e754-103">GetConfigurationStatus method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="2e754-104">Получает журнал состояния конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e754-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e754-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e754-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="2e754-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e754-106">Parameters</span></span>

<span data-ttu-id="2e754-107">*All* \[in\] Значение **true**, если этот метод должен возвращать сведения обо всех запусках конфигурации на компьютере, включая применение конфигурации и проверку согласованности.</span><span class="sxs-lookup"><span data-stu-id="2e754-107">*All* \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="2e754-108">*configurationStatus* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCConfigurationStatus**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="2e754-108">*configurationStatus* \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="2e754-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2e754-109">Return value</span></span>

<span data-ttu-id="2e754-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2e754-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e754-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="2e754-111">Remarks</span></span>

<span data-ttu-id="2e754-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="2e754-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e754-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2e754-113">Requirements</span></span>

<span data-ttu-id="2e754-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2e754-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2e754-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e754-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2e754-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e754-116">See also</span></span>

[<span data-ttu-id="2e754-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2e754-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)