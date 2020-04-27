---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetMetaConfiguration
ms.openlocfilehash: bd280cb8ebd7b0522e4e01cbd24bd9bdcfddf4c2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953411"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="45621-103">Метод GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="45621-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="45621-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="45621-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="45621-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45621-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="45621-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="45621-106">Parameters</span></span>

<span data-ttu-id="45621-107">*MetaConfiguration* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="45621-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="45621-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="45621-108">Return value</span></span>

<span data-ttu-id="45621-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="45621-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="45621-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="45621-110">Remarks</span></span>

<span data-ttu-id="45621-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="45621-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="45621-112">Требования</span><span class="sxs-lookup"><span data-stu-id="45621-112">Requirements</span></span>

<span data-ttu-id="45621-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="45621-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="45621-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="45621-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="45621-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="45621-115">See also</span></span>

[<span data-ttu-id="45621-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="45621-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
