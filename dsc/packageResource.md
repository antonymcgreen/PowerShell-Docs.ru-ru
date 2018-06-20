---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Package в DSC
ms.openlocfilehash: 16f7f1b8fa7b84bcfdeb09fdc46db9c93113e70c
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34188536"
---
# <a name="dsc-package-resource"></a><span data-ttu-id="18fee-103">Ресурс Package в DSC</span><span class="sxs-lookup"><span data-stu-id="18fee-103">DSC Package Resource</span></span>

> <span data-ttu-id="18fee-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="18fee-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="18fee-105">Ресурс **Package** в DSC Windows PowerShell предоставляет механизм установки или удаления пакетов, таких как пакеты установщика Windows и setup.exe, на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="18fee-105">The **Package** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall packages, such as Windows Installer and setup.exe packages, on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="18fee-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18fee-106">Syntax</span></span>

```
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ ReturnCode = [UInt32[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="18fee-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="18fee-107">Properties</span></span>
|  <span data-ttu-id="18fee-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="18fee-108">Property</span></span>  |  <span data-ttu-id="18fee-109">Описание</span><span class="sxs-lookup"><span data-stu-id="18fee-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="18fee-110">Name</span><span class="sxs-lookup"><span data-stu-id="18fee-110">Name</span></span>| <span data-ttu-id="18fee-111">Указывает имя пакета, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="18fee-111">Indicates the name of the package for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="18fee-112">путь</span><span class="sxs-lookup"><span data-stu-id="18fee-112">Path</span></span>| <span data-ttu-id="18fee-113">Указывает путь к файлу пакета.</span><span class="sxs-lookup"><span data-stu-id="18fee-113">Indicates the path where the package resides.</span></span>|
| <span data-ttu-id="18fee-114">ProductID</span><span class="sxs-lookup"><span data-stu-id="18fee-114">ProductId</span></span>| <span data-ttu-id="18fee-115">Указывает уникальный идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="18fee-115">Indicates the product ID that uniquely identifies the package.</span></span>|
| <span data-ttu-id="18fee-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="18fee-116">Arguments</span></span>| <span data-ttu-id="18fee-117">Указывает строку аргументов, которая будет передана в пакет в указанном виде.</span><span class="sxs-lookup"><span data-stu-id="18fee-117">Lists a string of arguments that will be passed to the package exactly as provided.</span></span>|
| <span data-ttu-id="18fee-118">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="18fee-118">Credential</span></span>| <span data-ttu-id="18fee-119">Предоставляет доступ к пакету в удаленном источнике.</span><span class="sxs-lookup"><span data-stu-id="18fee-119">Provides access to the package on a remote source.</span></span> <span data-ttu-id="18fee-120">Это свойство не используется для установки пакета.</span><span class="sxs-lookup"><span data-stu-id="18fee-120">This property is not used to install the package.</span></span> <span data-ttu-id="18fee-121">Пакет всегда устанавливается в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="18fee-121">The package is always installed on the local system.</span></span>|
| <span data-ttu-id="18fee-122">Ensure</span><span class="sxs-lookup"><span data-stu-id="18fee-122">Ensure</span></span>| <span data-ttu-id="18fee-123">Указывает, установлен ли пакет.</span><span class="sxs-lookup"><span data-stu-id="18fee-123">Indicates if the package is installed.</span></span> <span data-ttu-id="18fee-124">Если это свойство имеет значение Absent, пакет не устанавливается (а если он уже установлен, то удаляется).</span><span class="sxs-lookup"><span data-stu-id="18fee-124">Set this property to "Absent" to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="18fee-125">Если это свойство имеет значение Present (по умолчанию), пакет устанавливается.</span><span class="sxs-lookup"><span data-stu-id="18fee-125">Set it to "Present" (the default value) to ensure the package is installed.</span></span>|
| <span data-ttu-id="18fee-126">LogPath</span><span class="sxs-lookup"><span data-stu-id="18fee-126">LogPath</span></span>| <span data-ttu-id="18fee-127">Указывает полный путь к папке, где нужно сохранить файл журнала для установки или удаления пакета.</span><span class="sxs-lookup"><span data-stu-id="18fee-127">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span>|
| <span data-ttu-id="18fee-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="18fee-128">DependsOn</span></span> | <span data-ttu-id="18fee-129">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="18fee-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="18fee-130">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: "DependsOn = "[ResourceType]ResourceName"".</span><span class="sxs-lookup"><span data-stu-id="18fee-130">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>|
| <span data-ttu-id="18fee-131">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="18fee-131">ReturnCode</span></span>| <span data-ttu-id="18fee-132">Указывает ожидаемый код возврата.</span><span class="sxs-lookup"><span data-stu-id="18fee-132">Indicates the expected return code.</span></span> <span data-ttu-id="18fee-133">Если фактический код возврата не соответствует указанному здесь значению, настройка вернет ошибку.</span><span class="sxs-lookup"><span data-stu-id="18fee-133">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span>|

## <a name="example"></a><span data-ttu-id="18fee-134">Пример</span><span class="sxs-lookup"><span data-stu-id="18fee-134">Example</span></span>

<span data-ttu-id="18fee-135">В этом примере выполняется установщик MSI, который находится по указанному пути и имеет указанный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="18fee-135">This example runs the .msi installer that is located at the specified path and has the specified product ID.</span></span>

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