---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: e14237ef68b95d68e2f14071aa1fa6ba0717f39f
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892847"
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="1ed81-103">Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="1ed81-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="1ed81-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1ed81-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ed81-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ed81-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="1ed81-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ed81-106">Parameters</span></span>

<span data-ttu-id="1ed81-107">*MetaConfiguration* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="1ed81-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="1ed81-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1ed81-108">Return value</span></span>

<span data-ttu-id="1ed81-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1ed81-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ed81-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="1ed81-110">Remarks</span></span>

<span data-ttu-id="1ed81-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="1ed81-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ed81-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1ed81-112">Requirements</span></span>

<span data-ttu-id="1ed81-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1ed81-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1ed81-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1ed81-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1ed81-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ed81-115">See also</span></span>

[<span data-ttu-id="1ed81-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1ed81-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)