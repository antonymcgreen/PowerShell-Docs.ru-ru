---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: e14237ef68b95d68e2f14071aa1fa6ba0717f39f
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047806"
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="22b51-103">Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="22b51-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="22b51-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22b51-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="22b51-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22b51-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="22b51-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="22b51-106">Parameters</span></span>

<span data-ttu-id="22b51-107">*MetaConfiguration* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="22b51-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="22b51-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="22b51-108">Return value</span></span>

<span data-ttu-id="22b51-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="22b51-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="22b51-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="22b51-110">Remarks</span></span>

<span data-ttu-id="22b51-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="22b51-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="22b51-112">Требования</span><span class="sxs-lookup"><span data-stu-id="22b51-112">Requirements</span></span>

<span data-ttu-id="22b51-113">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="22b51-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="22b51-114">-Namespace Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="22b51-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="22b51-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="22b51-115">See also</span></span>

[<span data-ttu-id="22b51-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="22b51-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)