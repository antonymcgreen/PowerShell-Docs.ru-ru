---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: ebf2b65f152c622ccf42e12545b0048a0b96d963
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="2a8f7-103">Метод GetMetaConfiguration класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="2a8f7-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="2a8f7-104">Получает параметры локального диспетчера конфигураций, которые используются для управления агентом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2a8f7-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

<a name="syntax"></a><span data-ttu-id="2a8f7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a8f7-105">Syntax</span></span>
------

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

<a name="parameters"></a><span data-ttu-id="2a8f7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a8f7-106">Parameters</span></span>
----------

<span data-ttu-id="2a8f7-107">*MetaConfiguration* \[out\] Выходные данные содержат встроенный экземпляр класса **MSFT_DSCMetaConfiguration**, который определяет параметры.</span><span class="sxs-lookup"><span data-stu-id="2a8f7-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="2a8f7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a8f7-108">Return value</span></span>
------------

<span data-ttu-id="2a8f7-109">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2a8f7-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a8f7-110">Замечания</span><span class="sxs-lookup"><span data-stu-id="2a8f7-110">Remarks</span></span>

<span data-ttu-id="2a8f7-111">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="2a8f7-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a8f7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2a8f7-112">Requirements</span></span>
------------
><span data-ttu-id="2a8f7-113">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2a8f7-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="2a8f7-114">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a8f7-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="2a8f7-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a8f7-115">See also</span></span>


[<span data-ttu-id="2a8f7-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2a8f7-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)