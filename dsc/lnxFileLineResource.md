---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурса nxFileLine в DSC для Linux
ms.openlocfilehash: 6b927839c23478aa9916a5d23836b31fccc58484
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219639"
---
# <a name="dsc-for-linux-nxfileline-resource"></a><span data-ttu-id="a2afb-103">Ресурса nxFileLine в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="a2afb-103">DSC for Linux nxFileLine Resource</span></span>

<span data-ttu-id="a2afb-104">Ресурс **nxFileLine** в DSC PowerShell предоставляет механизм управления строками в файле конфигурации на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="a2afb-104">The **nxFileLine** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to to manage lines within a configuration file on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2afb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2afb-105">Syntax</span></span>

```
nxFileLine <string> #ResourceName
{
    FilePath = <string>
    ContainsLine = <string>
    [ DoesNotContainPattern = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="a2afb-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="a2afb-106">Properties</span></span>

|  <span data-ttu-id="a2afb-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="a2afb-107">Property</span></span> |  <span data-ttu-id="a2afb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a2afb-108">Description</span></span> |
|---|---|
| <span data-ttu-id="a2afb-109">FilePath</span><span class="sxs-lookup"><span data-stu-id="a2afb-109">FilePath</span></span>| <span data-ttu-id="a2afb-110">Полный путь к файлу для управления строками на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="a2afb-110">The full path to the file to manage lines in on the target node.</span></span>|
| <span data-ttu-id="a2afb-111">ContainsLine</span><span class="sxs-lookup"><span data-stu-id="a2afb-111">ContainsLine</span></span>| <span data-ttu-id="a2afb-112">Строка, которая должна существовать в файле.</span><span class="sxs-lookup"><span data-stu-id="a2afb-112">A line to ensure exists in the file.</span></span> <span data-ttu-id="a2afb-113">Если в файле эта строка отсутствует, она будет добавлена.</span><span class="sxs-lookup"><span data-stu-id="a2afb-113">This line will be appended to the file if it does not exist in the file.</span></span> <span data-ttu-id="a2afb-114">Свойство **ContainsLine** является обязательным, но, если оно не требуется, можно задать в качестве его значения пустую строку ("ContainsLine ="").</span><span class="sxs-lookup"><span data-stu-id="a2afb-114">**ContainsLine** is mandatory, but can be set to an empty string (\`ContainsLine = ‘’\`\`) if it is not needed.</span></span>|
| <span data-ttu-id="a2afb-115">DoesNotContainPattern</span><span class="sxs-lookup"><span data-stu-id="a2afb-115">DoesNotContainPattern</span></span>| <span data-ttu-id="a2afb-116">Шаблон регулярных выражений для строк, которые не должны присутствовать в файле.</span><span class="sxs-lookup"><span data-stu-id="a2afb-116">A regular expression pattern for lines that should not exist in the file.</span></span> <span data-ttu-id="a2afb-117">Присутствующие в файле строки, которые соответствуют этому регулярному выражению, будут удалены.</span><span class="sxs-lookup"><span data-stu-id="a2afb-117">For any lines that exist in the file that match this regular expression, the line will be removed from the file.</span></span>|
| <span data-ttu-id="a2afb-118">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a2afb-118">DependsOn</span></span> | <span data-ttu-id="a2afb-119">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="a2afb-119">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a2afb-120">Например, если **идентификатор** первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a2afb-120">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="a2afb-121">Пример</span><span class="sxs-lookup"><span data-stu-id="a2afb-121">Example</span></span>

<span data-ttu-id="a2afb-122">В этом примере показывается, как использовать ресурс **nxFileLine** для настройки файла `/etc/sudoers`, чтобы пользователь monuser не требовал использовать телетайп (TTY).</span><span class="sxs-lookup"><span data-stu-id="a2afb-122">This example demonstrates using the **nxFileLine** resource to configure the `/etc/sudoers` file, ensuring that the user: monuser is configured to not requiretty.</span></span>

```
Import-DSCResource -Module nx

nxFileLine DoNotRequireTTY
{
   FilePath = “/etc/sudoers”
   ContainsLine = 'Defaults:monuser !requiretty'
   DoesNotContainPattern = "Defaults:monuser[ ]+requiretty"
}
```