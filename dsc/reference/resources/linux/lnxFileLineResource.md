---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурса nxFileLine в DSC для Linux
ms.openlocfilehash: 6a91db25638b09659adfabcec78f91bcb2e69dd9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077966"
---
# <a name="dsc-for-linux-nxfileline-resource"></a><span data-ttu-id="8bd05-103">Ресурса nxFileLine в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="8bd05-103">DSC for Linux nxFileLine Resource</span></span>

<span data-ttu-id="8bd05-104">Ресурс **nxFileLine** в DSC PowerShell предоставляет механизм управления строками в файле конфигурации на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="8bd05-104">The **nxFileLine** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage lines within a configuration file on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bd05-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bd05-105">Syntax</span></span>

```
nxFileLine <string> #ResourceName
{
    FilePath = <string>
    ContainsLine = <string>
    [ DoesNotContainPattern = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="8bd05-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="8bd05-106">Properties</span></span>

|  <span data-ttu-id="8bd05-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="8bd05-107">Property</span></span> |  <span data-ttu-id="8bd05-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8bd05-108">Description</span></span> |
|---|---|
| <span data-ttu-id="8bd05-109">FilePath</span><span class="sxs-lookup"><span data-stu-id="8bd05-109">FilePath</span></span>| <span data-ttu-id="8bd05-110">Полный путь к файлу для управления строками на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="8bd05-110">The full path to the file to manage lines in on the target node.</span></span>|
| <span data-ttu-id="8bd05-111">ContainsLine</span><span class="sxs-lookup"><span data-stu-id="8bd05-111">ContainsLine</span></span>| <span data-ttu-id="8bd05-112">Строка, которая должна существовать в файле.</span><span class="sxs-lookup"><span data-stu-id="8bd05-112">A line to ensure exists in the file.</span></span> <span data-ttu-id="8bd05-113">Если в файле эта строка отсутствует, она будет добавлена.</span><span class="sxs-lookup"><span data-stu-id="8bd05-113">This line will be appended to the file if it does not exist in the file.</span></span> <span data-ttu-id="8bd05-114">Свойство **ContainsLine** является обязательным, но, если оно не требуется, можно задать в качестве его значения пустую строку (`ContainsLine = ""`).</span><span class="sxs-lookup"><span data-stu-id="8bd05-114">**ContainsLine** is mandatory, but can be set to an empty string (`ContainsLine = ""`) if it is not needed.</span></span>|
| <span data-ttu-id="8bd05-115">DoesNotContainPattern</span><span class="sxs-lookup"><span data-stu-id="8bd05-115">DoesNotContainPattern</span></span>| <span data-ttu-id="8bd05-116">Шаблон регулярных выражений для строк, которые не должны присутствовать в файле.</span><span class="sxs-lookup"><span data-stu-id="8bd05-116">A regular expression pattern for lines that should not exist in the file.</span></span> <span data-ttu-id="8bd05-117">Присутствующие в файле строки, которые соответствуют этому регулярному выражению, будут удалены.</span><span class="sxs-lookup"><span data-stu-id="8bd05-117">For any lines that exist in the file that match this regular expression, the line will be removed from the file.</span></span>|
| <span data-ttu-id="8bd05-118">DependsOn</span><span class="sxs-lookup"><span data-stu-id="8bd05-118">DependsOn</span></span> | <span data-ttu-id="8bd05-119">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="8bd05-119">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="8bd05-120">Например, если **идентификатор** первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="8bd05-120">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="8bd05-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8bd05-121">Example</span></span>

<span data-ttu-id="8bd05-122">В этом примере показывается, как использовать ресурс **nxFileLine** для настройки файла `/etc/sudoers`, чтобы пользователь monuser не требовал использовать телетайп (TTY).</span><span class="sxs-lookup"><span data-stu-id="8bd05-122">This example demonstrates using the **nxFileLine** resource to configure the `/etc/sudoers` file, ensuring that the user: monuser is configured to not requiretty.</span></span>

```powershell
Import-DscResource -Module nx

nxFileLine DoNotRequireTTY
{
   FilePath = “/etc/sudoers”
   ContainsLine = 'Defaults:monuser !requiretty'
   DoesNotContainPattern = "Defaults:monuser[ ]+requiretty"
}
```