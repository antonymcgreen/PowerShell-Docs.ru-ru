---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetConfigurationStatus класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: c66ccc4eefaef2d0c3a68fa8a96c5abb9bda6e4c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55681424"
---
# <a name="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="6a9aa-103">Метод GetConfigurationStatus класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="6a9aa-103">GetConfigurationStatus method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="6a9aa-104">Получает журнал состояния конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a9aa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a9aa-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="6a9aa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a9aa-106">Parameters</span></span>

<span data-ttu-id="6a9aa-107">*All* \[in\] Значение **true**, если этот метод должен возвращать сведения обо всех запусках конфигурации на компьютере, включая применение конфигурации и проверку согласованности.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-107">*All* \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="6a9aa-108">*configurationStatus* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCConfigurationStatus**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-108">*configurationStatus* \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="6a9aa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6a9aa-109">Return value</span></span>

<span data-ttu-id="6a9aa-110">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a9aa-111">Замечания</span><span class="sxs-lookup"><span data-stu-id="6a9aa-111">Remarks</span></span>

<span data-ttu-id="6a9aa-112">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="6a9aa-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a9aa-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6a9aa-113">Requirements</span></span>

<span data-ttu-id="6a9aa-114">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="6a9aa-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="6a9aa-115">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="6a9aa-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="6a9aa-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a9aa-116">See also</span></span>

[<span data-ttu-id="6a9aa-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="6a9aa-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)