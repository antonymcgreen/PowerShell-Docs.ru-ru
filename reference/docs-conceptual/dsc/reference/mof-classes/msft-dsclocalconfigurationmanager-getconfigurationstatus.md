---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationStatus
ms.openlocfilehash: c2c478151428052d656832fb4079f12d666a910d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464062"
---
# <a name="getconfigurationstatus-method"></a><span data-ttu-id="92a31-103">Метод GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="92a31-103">GetConfigurationStatus method</span></span>

<span data-ttu-id="92a31-104">Получает журнал состояния конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92a31-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="92a31-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92a31-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="92a31-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="92a31-106">Parameters</span></span>

<span data-ttu-id="92a31-107">**All** \[in\] **true**, если этот метод должен возвращать сведения обо всех запусках конфигурации на компьютере, включая применение конфигурации и проверку согласованности.</span><span class="sxs-lookup"><span data-stu-id="92a31-107">**All** \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="92a31-108">**configurationStatus** \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCConfigurationStatus**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="92a31-108">**configurationStatus** \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="92a31-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="92a31-109">Return value</span></span>

<span data-ttu-id="92a31-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="92a31-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="92a31-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="92a31-111">Remarks</span></span>

<span data-ttu-id="92a31-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="92a31-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="92a31-113">Требования</span><span class="sxs-lookup"><span data-stu-id="92a31-113">Requirements</span></span>

<span data-ttu-id="92a31-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="92a31-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="92a31-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="92a31-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="92a31-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="92a31-116">See also</span></span>

[<span data-ttu-id="92a31-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="92a31-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
