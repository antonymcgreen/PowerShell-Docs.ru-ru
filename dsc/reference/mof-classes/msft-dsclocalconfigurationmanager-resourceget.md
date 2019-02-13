---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceGet класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 1b74adf2327af2e0f9416f1d00eac4e3b75e9013
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55682214"
---
# <a name="resourceget-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b0ad8-103">Метод ResourceGet класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="b0ad8-103">ResourceGet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b0ad8-104">Напрямую вызывает метод **Get** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0ad8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0ad8-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="b0ad8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0ad8-106">Parameters</span></span>

<span data-ttu-id="b0ad8-107">*ResourceType* \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="b0ad8-108">*ModuleName* \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="b0ad8-109">*resourceProperty* \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="b0ad8-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="b0ad8-111">*configurations* \[out\] Выходные данные содержат встроенный экземпляр конфигураций.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-111">*configurations* \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="b0ad8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b0ad8-112">Return value</span></span>

<span data-ttu-id="b0ad8-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0ad8-114">Замечания</span><span class="sxs-lookup"><span data-stu-id="b0ad8-114">Remarks</span></span>

<span data-ttu-id="b0ad8-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="b0ad8-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b0ad8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b0ad8-116">Requirements</span></span>

<span data-ttu-id="b0ad8-117">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b0ad8-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b0ad8-118">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0ad8-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b0ad8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0ad8-119">See also</span></span>

[<span data-ttu-id="b0ad8-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b0ad8-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)