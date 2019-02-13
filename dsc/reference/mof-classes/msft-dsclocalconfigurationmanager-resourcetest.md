---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Метод ResourceTest класса MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: e7645b0c6b93b96cb01f72c1c92d468f7642ea13
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680957"
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="5e89d-103">Метод ResourceTest класса MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="5e89d-103">ResourceTest method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="5e89d-104">Напрямую вызывает метод **Test** ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="5e89d-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e89d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e89d-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="5e89d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e89d-106">Parameters</span></span>

<span data-ttu-id="5e89d-107">*ResourceType* \[in\] Имя вызываемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="5e89d-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="5e89d-108">*ModuleName* \[in\] Имя модуля, содержащего вызываемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="5e89d-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="5e89d-109">*resourceProperty* \[in\] Указывает имя свойства ресурса и его значение в хэш-таблице как ключ и значение соответственно.</span><span class="sxs-lookup"><span data-stu-id="5e89d-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="5e89d-110">Используйте командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) для обнаружения свойств ресурсов и их типов.</span><span class="sxs-lookup"><span data-stu-id="5e89d-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="5e89d-111">*InDesiredState* \[out\] В выходных данных это свойство имеет значение **true**, если целевой узел находится в нужном состоянии.</span><span class="sxs-lookup"><span data-stu-id="5e89d-111">*InDesiredState* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="5e89d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5e89d-112">Return value</span></span>

<span data-ttu-id="5e89d-113">Возвращает нуль в случае успешного выполнения; в противном случае возвращает код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5e89d-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e89d-114">Замечания</span><span class="sxs-lookup"><span data-stu-id="5e89d-114">Remarks</span></span>

<span data-ttu-id="5e89d-115">Это статический метод.</span><span class="sxs-lookup"><span data-stu-id="5e89d-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e89d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="5e89d-116">Requirements</span></span>

<span data-ttu-id="5e89d-117">**MOF-файл:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5e89d-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="5e89d-118">**Пространство имен**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5e89d-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="5e89d-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e89d-119">See also</span></span>

[<span data-ttu-id="5e89d-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="5e89d-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)