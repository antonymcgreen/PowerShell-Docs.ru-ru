---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Package в DSC
ms.openlocfilehash: efac07b4b051564cadd5aa1542a6afda6cd453ad
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953151"
---
# <a name="dsc-package-resource"></a><span data-ttu-id="835c1-103">Ресурс Package в DSC</span><span class="sxs-lookup"><span data-stu-id="835c1-103">DSC Package Resource</span></span>

> <span data-ttu-id="835c1-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="835c1-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="835c1-105">Ресурс **Package** в DSC Windows PowerShell предоставляет механизм установки или удаления пакетов, таких как пакеты установщика Windows и setup.exe, на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="835c1-105">The **Package** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall packages, such as Windows Installer and setup.exe packages, on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="835c1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="835c1-106">Syntax</span></span>

```Syntax
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ ReturnCode = [UInt32[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="835c1-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="835c1-107">Properties</span></span>

|<span data-ttu-id="835c1-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="835c1-108">Property</span></span> |<span data-ttu-id="835c1-109">Description</span><span class="sxs-lookup"><span data-stu-id="835c1-109">Description</span></span> |
|---|---|
|<span data-ttu-id="835c1-110">Имя</span><span class="sxs-lookup"><span data-stu-id="835c1-110">Name</span></span> |<span data-ttu-id="835c1-111">Указывает имя пакета, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="835c1-111">Indicates the name of the package for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="835c1-112">путь</span><span class="sxs-lookup"><span data-stu-id="835c1-112">Path</span></span> |<span data-ttu-id="835c1-113">Указывает путь к файлу пакета.</span><span class="sxs-lookup"><span data-stu-id="835c1-113">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="835c1-114">ProductId</span><span class="sxs-lookup"><span data-stu-id="835c1-114">ProductId</span></span> |<span data-ttu-id="835c1-115">Указывает уникальный идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="835c1-115">Indicates the product ID that uniquely identifies the package.</span></span> |
|<span data-ttu-id="835c1-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="835c1-116">Arguments</span></span> |<span data-ttu-id="835c1-117">Указывает строку аргументов, которая будет передана в пакет в указанном виде.</span><span class="sxs-lookup"><span data-stu-id="835c1-117">Lists a string of arguments that will be passed to the package exactly as provided.</span></span> |
|<span data-ttu-id="835c1-118">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="835c1-118">Credential</span></span> |<span data-ttu-id="835c1-119">Предоставляет доступ к пакету в удаленном источнике.</span><span class="sxs-lookup"><span data-stu-id="835c1-119">Provides access to the package on a remote source.</span></span> <span data-ttu-id="835c1-120">Это свойство не используется для установки пакета.</span><span class="sxs-lookup"><span data-stu-id="835c1-120">This property is not used to install the package.</span></span> <span data-ttu-id="835c1-121">Пакет всегда устанавливается в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="835c1-121">The package is always installed on the local system.</span></span> |
|<span data-ttu-id="835c1-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="835c1-122">LogPath</span></span> |<span data-ttu-id="835c1-123">Указывает полный путь к папке, где нужно сохранить файл журнала для установки или удаления пакета.</span><span class="sxs-lookup"><span data-stu-id="835c1-123">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |
|<span data-ttu-id="835c1-124">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="835c1-124">ReturnCode</span></span> |<span data-ttu-id="835c1-125">Указывает ожидаемый код возврата.</span><span class="sxs-lookup"><span data-stu-id="835c1-125">Indicates the expected return code.</span></span> <span data-ttu-id="835c1-126">Если фактический код возврата не соответствует указанному здесь значению, настройка вернет ошибку.</span><span class="sxs-lookup"><span data-stu-id="835c1-126">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="835c1-127">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="835c1-127">Common properties</span></span>

|<span data-ttu-id="835c1-128">Свойство</span><span class="sxs-lookup"><span data-stu-id="835c1-128">Property</span></span> |<span data-ttu-id="835c1-129">Description</span><span class="sxs-lookup"><span data-stu-id="835c1-129">Description</span></span> |
|---|---|
|<span data-ttu-id="835c1-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="835c1-130">DependsOn</span></span> |<span data-ttu-id="835c1-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="835c1-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="835c1-132">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="835c1-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="835c1-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="835c1-133">Ensure</span></span> |<span data-ttu-id="835c1-134">Указывает, установлен ли пакет.</span><span class="sxs-lookup"><span data-stu-id="835c1-134">Indicates if the package is installed.</span></span> <span data-ttu-id="835c1-135">Если это свойство имеет значение **Absent**, пакет не устанавливается (а если он уже установлен, то удаляется).</span><span class="sxs-lookup"><span data-stu-id="835c1-135">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="835c1-136">Если это свойство имеет значение **Present**, пакет устанавливается.</span><span class="sxs-lookup"><span data-stu-id="835c1-136">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="835c1-137">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="835c1-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="835c1-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="835c1-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="835c1-139">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="835c1-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="835c1-140">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="835c1-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="835c1-141">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="835c1-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="835c1-142">Пример</span><span class="sxs-lookup"><span data-stu-id="835c1-142">Example</span></span>

<span data-ttu-id="835c1-143">В этом примере выполняется установщик MSI, который находится по указанному пути и имеет указанный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="835c1-143">This example runs the .msi installer that is located at the specified path and has the specified product ID.</span></span>

```powershell
Configuration PackageTest
{
    Package PackageExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Path        = "$Env:SystemDrive\TestFolder\TestProject.msi"
        Name        = "TestPackage"
        ProductId   = "ACDDCDAF-80C6-41E6-A1B9-8ABD8A05027E"
    }
}
```