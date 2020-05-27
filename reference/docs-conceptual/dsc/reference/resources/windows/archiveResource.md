---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Archive в DSC
ms.openlocfilehash: 679de8b965304c149b10321e73e42b224f49ecc5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560378"
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="1d92b-103">Ресурс Archive в DSC</span><span class="sxs-lookup"><span data-stu-id="1d92b-103">DSC Archive Resource</span></span>

> <span data-ttu-id="1d92b-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1d92b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="1d92b-105">Ресурс Archive в DSC Windows PowerShell предоставляет механизм распаковки файлов архивов (ZIP) в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="1d92b-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d92b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d92b-106">Syntax</span></span>

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="1d92b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1d92b-107">Properties</span></span>

|<span data-ttu-id="1d92b-108">Свойство</span><span class="sxs-lookup"><span data-stu-id="1d92b-108">Property</span></span> |<span data-ttu-id="1d92b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1d92b-109">Description</span></span> |
|---|---|
|<span data-ttu-id="1d92b-110">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d92b-110">Destination</span></span> |<span data-ttu-id="1d92b-111">Указывает, куда будет извлечено содержимое архива.</span><span class="sxs-lookup"><span data-stu-id="1d92b-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span> |
|<span data-ttu-id="1d92b-112">путь</span><span class="sxs-lookup"><span data-stu-id="1d92b-112">Path</span></span> |<span data-ttu-id="1d92b-113">Указывает исходный путь для файла архива.</span><span class="sxs-lookup"><span data-stu-id="1d92b-113">Specifies the source path of the archive file.</span></span> |
|<span data-ttu-id="1d92b-114">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1d92b-114">Checksum</span></span> |<span data-ttu-id="1d92b-115">Определяет тип проверки пары файлов на идентичность.</span><span class="sxs-lookup"><span data-stu-id="1d92b-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="1d92b-116">Если свойство **Checksum** не задано, для сравнения используется только имя файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="1d92b-116">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="1d92b-117">Допустимые значения: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-117">Valid values include: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span></span> <span data-ttu-id="1d92b-118">Если свойство **Checksum** указано без свойства **Validate**, возникает ошибка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d92b-118">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> |
|<span data-ttu-id="1d92b-119">Force</span><span class="sxs-lookup"><span data-stu-id="1d92b-119">Force</span></span> |<span data-ttu-id="1d92b-120">Определенные операции с файлами (например, перезапись файла или удаление непустого каталога) вызывают ошибку.</span><span class="sxs-lookup"><span data-stu-id="1d92b-120">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="1d92b-121">Свойство **Force** позволяет переопределять такие ошибки.</span><span class="sxs-lookup"><span data-stu-id="1d92b-121">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="1d92b-122">Значение по умолчанию равно **False**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-122">The default value is **False**.</span></span> |
|<span data-ttu-id="1d92b-123">Проверить</span><span class="sxs-lookup"><span data-stu-id="1d92b-123">Validate</span></span>| <span data-ttu-id="1d92b-124">Проверяет соответствие архива и подписи, используя свойство **Checksum**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-124">Uses the **Checksum** property to determine if the archive matches the signature.</span></span> <span data-ttu-id="1d92b-125">Если свойство **Checksum** указано без свойства **Validate**, возникает ошибка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d92b-125">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> <span data-ttu-id="1d92b-126">Если свойство **Validate** указано без свойства **Checksum**, по умолчанию для **Checksum** используется значение _SHA-256_.</span><span class="sxs-lookup"><span data-stu-id="1d92b-126">If you specify **Validate** without **Checksum**, a _SHA-256_ **Checksum** is used by default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1d92b-127">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="1d92b-127">Common properties</span></span>

|<span data-ttu-id="1d92b-128">Свойство</span><span class="sxs-lookup"><span data-stu-id="1d92b-128">Property</span></span> |<span data-ttu-id="1d92b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="1d92b-129">Description</span></span> |
|---|---|
|<span data-ttu-id="1d92b-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1d92b-130">DependsOn</span></span> |<span data-ttu-id="1d92b-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="1d92b-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1d92b-132">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="1d92b-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1d92b-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="1d92b-133">Ensure</span></span> |<span data-ttu-id="1d92b-134">Указывает необходимость проверки того, существует ли содержимое архива в **папке назначения**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-134">Determines whether to check if the content of the archive exists at the **Destination**.</span></span> <span data-ttu-id="1d92b-135">Чтобы убедиться, что содержимое существует, укажите для этого свойства значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-135">Set this property to **Present** to ensure the contents exist.</span></span> <span data-ttu-id="1d92b-136">Чтобы убедиться, что содержимого не существует, укажите для этого свойства значение **Absent**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-136">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="1d92b-137">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="1d92b-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="1d92b-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1d92b-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="1d92b-139">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="1d92b-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="1d92b-140">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1d92b-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="1d92b-141">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="1d92b-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="1d92b-142">Пример</span><span class="sxs-lookup"><span data-stu-id="1d92b-142">Example</span></span>

<span data-ttu-id="1d92b-143">В следующем примере показано, как использовать ресурс Archive, чтобы убедиться, что содержимое архивного файла с именем `Test.zip` существует и извлекается в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="1d92b-143">The following example shows how to use the Archive resource to ensure that the contents of an archive file called `Test.zip` exist and are extracted at a given destination.</span></span>

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```
