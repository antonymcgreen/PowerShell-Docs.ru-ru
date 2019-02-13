---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: e14237ef68b95d68e2f14071aa1fa6ba0717f39f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680964"
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="72a6e-103">Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="72a6e-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="72a6e-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="72a6e-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="72a6e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72a6e-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="72a6e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="72a6e-106">Parameters</span></span>

<span data-ttu-id="72a6e-107">*MetaConfiguration* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="72a6e-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="72a6e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="72a6e-108">Return value</span></span>

<span data-ttu-id="72a6e-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="72a6e-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="72a6e-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="72a6e-110">Remarks</span></span>

<span data-ttu-id="72a6e-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="72a6e-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="72a6e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="72a6e-112">Requirements</span></span>

<span data-ttu-id="72a6e-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="72a6e-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="72a6e-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="72a6e-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="72a6e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="72a6e-115">See also</span></span>

[<span data-ttu-id="72a6e-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="72a6e-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)