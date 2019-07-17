---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetMetaConfiguration
ms.openlocfilehash: bd280cb8ebd7b0522e4e01cbd24bd9bdcfddf4c2
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734445"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="91d0a-103">Метод GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="91d0a-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="91d0a-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="91d0a-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="91d0a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91d0a-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="91d0a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="91d0a-106">Parameters</span></span>

<span data-ttu-id="91d0a-107">*MetaConfiguration* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="91d0a-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="91d0a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="91d0a-108">Return value</span></span>

<span data-ttu-id="91d0a-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="91d0a-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="91d0a-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="91d0a-110">Remarks</span></span>

<span data-ttu-id="91d0a-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="91d0a-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="91d0a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="91d0a-112">Requirements</span></span>

<span data-ttu-id="91d0a-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="91d0a-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="91d0a-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="91d0a-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="91d0a-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="91d0a-115">See also</span></span>

[<span data-ttu-id="91d0a-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="91d0a-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
