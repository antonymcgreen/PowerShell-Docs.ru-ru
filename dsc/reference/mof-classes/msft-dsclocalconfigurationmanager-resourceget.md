---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceGet класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 1b74adf2327af2e0f9416f1d00eac4e3b75e9013
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078578"
---
# <a name="resourceget-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="102c5-103">Метод ResourceGet класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="102c5-103">ResourceGet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="102c5-104">Напрямую вызывает метод **Get** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="102c5-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="102c5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="102c5-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="102c5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="102c5-106">Parameters</span></span>

<span data-ttu-id="102c5-107">*ResourceType* \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="102c5-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="102c5-108">*ModuleName* \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="102c5-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="102c5-109">*resourceProperty* \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="102c5-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="102c5-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="102c5-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="102c5-111">*configurations* \[out\] Выходные данные содержат встроенный экземпляр конфигураций.</span><span class="sxs-lookup"><span data-stu-id="102c5-111">*configurations* \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="102c5-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="102c5-112">Return value</span></span>

<span data-ttu-id="102c5-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="102c5-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="102c5-114">Замечания</span><span class="sxs-lookup"><span data-stu-id="102c5-114">Remarks</span></span>

<span data-ttu-id="102c5-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="102c5-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="102c5-116">Требования</span><span class="sxs-lookup"><span data-stu-id="102c5-116">Requirements</span></span>

<span data-ttu-id="102c5-117">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="102c5-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="102c5-118">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="102c5-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="102c5-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="102c5-119">See also</span></span>

[<span data-ttu-id="102c5-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="102c5-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)