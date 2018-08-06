---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Registry в DSC
ms.openlocfilehash: 8d74473d167b70182c3a16c1d39d2a9e797afb1b
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39267727"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="71d72-103">Ресурс Registry в DSC</span><span class="sxs-lookup"><span data-stu-id="71d72-103">DSC Registry Resource</span></span>

<span data-ttu-id="71d72-104">_Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0_</span><span class="sxs-lookup"><span data-stu-id="71d72-104">_Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0_</span></span>

<span data-ttu-id="71d72-105">Ресурс **Registry** в DSC Windows PowerShell предоставляет механизм управления разделами и значениями реестра на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="71d72-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="71d72-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71d72-106">Syntax</span></span>

```
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Ensure = [string] { Present | Absent }  ]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ DependsOn = [string[]] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
}
```

## <a name="properties"></a><span data-ttu-id="71d72-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="71d72-107">Properties</span></span>

| <span data-ttu-id="71d72-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="71d72-108">Property</span></span> | <span data-ttu-id="71d72-109">Описание</span><span class="sxs-lookup"><span data-stu-id="71d72-109">Description</span></span> |
| --- | --- |
| <span data-ttu-id="71d72-110">Клавиши</span><span class="sxs-lookup"><span data-stu-id="71d72-110">Key</span></span>| <span data-ttu-id="71d72-111">Указывает путь к разделу реестра, для которого требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="71d72-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="71d72-112">Этот путь должен включать куст.</span><span class="sxs-lookup"><span data-stu-id="71d72-112">This path must include the hive.</span></span>|
| <span data-ttu-id="71d72-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="71d72-113">ValueName</span></span>| <span data-ttu-id="71d72-114">Указывает имя значения реестра.</span><span class="sxs-lookup"><span data-stu-id="71d72-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="71d72-115">Чтобы добавить или удалить раздел реестра, укажите это свойство как пустую строку, не указывая ValueType или ValueData.</span><span class="sxs-lookup"><span data-stu-id="71d72-115">To add or remove a registry key, specify this property as an empty string without specifying ValueType or ValueData.</span></span> <span data-ttu-id="71d72-116">Чтобы изменить или удалить значение по умолчанию раздела реестра, укажите это свойство как пустую строку, указав ValueType или ValueData.</span><span class="sxs-lookup"><span data-stu-id="71d72-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying ValueType or ValueData.</span></span>|
| <span data-ttu-id="71d72-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="71d72-117">Ensure</span></span>| <span data-ttu-id="71d72-118">Указывает, существует ли ключ и значение.</span><span class="sxs-lookup"><span data-stu-id="71d72-118">Indicates if the key and value exist.</span></span> <span data-ttu-id="71d72-119">Для этого укажите для этого свойства значение Present.</span><span class="sxs-lookup"><span data-stu-id="71d72-119">To ensure that they do, set this property to "Present".</span></span> <span data-ttu-id="71d72-120">Чтобы они не существовали, укажите для этого свойства значение Absent.</span><span class="sxs-lookup"><span data-stu-id="71d72-120">To ensure that they do not exist, set the property to "Absent".</span></span> <span data-ttu-id="71d72-121">Значение по умолчанию — Present.</span><span class="sxs-lookup"><span data-stu-id="71d72-121">The default value is "Present".</span></span>|
| <span data-ttu-id="71d72-122">Force</span><span class="sxs-lookup"><span data-stu-id="71d72-122">Force</span></span>| <span data-ttu-id="71d72-123">Если указанный раздел реестра присутствует, **Force** перезаписывает его новым значением.</span><span class="sxs-lookup"><span data-stu-id="71d72-123">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="71d72-124">При удалении раздела реестра с подразделами необходимо выбрать **$true**</span><span class="sxs-lookup"><span data-stu-id="71d72-124">If deleting a registry key with subkeys, this needs to be **$true**</span></span> |
| <span data-ttu-id="71d72-125">Hex</span><span class="sxs-lookup"><span data-stu-id="71d72-125">Hex</span></span>| <span data-ttu-id="71d72-126">Указывает, будут ли данные выражены в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="71d72-126">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="71d72-127">Если свойство задано, данные значения DWORD/QWORD будут представлены в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="71d72-127">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="71d72-128">Недопустимо для других типов.</span><span class="sxs-lookup"><span data-stu-id="71d72-128">Not valid for other types.</span></span> <span data-ttu-id="71d72-129">Значение по умолчанию — **$false**.</span><span class="sxs-lookup"><span data-stu-id="71d72-129">The default value is **$false**.</span></span>|
| <span data-ttu-id="71d72-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="71d72-130">DependsOn</span></span>| <span data-ttu-id="71d72-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="71d72-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="71d72-132">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="71d72-132">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="71d72-133">ValueData</span><span class="sxs-lookup"><span data-stu-id="71d72-133">ValueData</span></span>| <span data-ttu-id="71d72-134">Данные для значения реестра.</span><span class="sxs-lookup"><span data-stu-id="71d72-134">The data for the registry value.</span></span>|
| <span data-ttu-id="71d72-135">ValueType</span><span class="sxs-lookup"><span data-stu-id="71d72-135">ValueType</span></span>| <span data-ttu-id="71d72-136">Указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="71d72-136">Indicates the type of the value.</span></span> <span data-ttu-id="71d72-137">Поддерживаемые типы параметров: строковый (REG_SZ), двоичный (REG-BINARY), Dword — 32-битный (REG_DWORD), Qword — 64-битный (REG_QWORD), многостроковый (REG_MULTI_SZ), расширяемый строковый (REG_EXPAND_SZ).</span><span class="sxs-lookup"><span data-stu-id="71d72-137">The supported types are: String (REG_SZ), Binary (REG-BINARY), Dword 32-bit (REG_DWORD), Qword 64-bit (REG_QWORD), Multi-string (REG_MULTI_SZ), Expandable string (REG_EXPAND_SZ)</span></span> |

## <a name="example"></a><span data-ttu-id="71d72-138">Пример</span><span class="sxs-lookup"><span data-stu-id="71d72-138">Example</span></span>

<span data-ttu-id="71d72-139">В этом примере гарантируется, что ключ с именем ExampleKey присутствует в кусте **HKEY\_LOCAL\_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="71d72-139">This example ensures that a key named "ExampleKey" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> <span data-ttu-id="71d72-140">Для изменения настройки реестра в кусте `HKEY\CURRENT\USER` требуется запустить конфигурацию с использованием не системных, а пользовательских учетных данных.</span><span class="sxs-lookup"><span data-stu-id="71d72-140">Changing a registry setting in the `HKEY\CURRENT\USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="71d72-141">Вы можете использовать свойство **PsDscRunAsCredential**, чтобы указать учетные данные пользователя для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="71d72-141">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="71d72-142">Пример см. в руководстве по [запуску DSC с использованием учетных данных пользователя](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="71d72-142">For an example, see [Running DSC with user credentials](runAsUser.md).</span></span>