---
ms.date: 09/13/2016
ms.topic: reference
title: Как объявить наборы параметров
description: Как объявить наборы параметров
ms.openlocfilehash: bd4d504a9fe6c7f7626901c49bc08851244f0995
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667068"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="1f92d-103">Как объявить наборы параметров</span><span class="sxs-lookup"><span data-stu-id="1f92d-103">How to Declare Parameter Sets</span></span>

<span data-ttu-id="1f92d-104">В этом примере показано, как определить два набора параметров при объявлении параметров для командлета.</span><span class="sxs-lookup"><span data-stu-id="1f92d-104">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="1f92d-105">Каждый набор параметров имеет как уникальный параметр, так и общий параметр, который используется обоими наборами параметров.</span><span class="sxs-lookup"><span data-stu-id="1f92d-105">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="1f92d-106">Дополнительные сведения о наборах параметров, в том числе о том, как указать набор параметров по умолчанию, см. в разделе [наборы параметров командлета](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1f92d-106">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f92d-107">Везде, где это возможно, определите уникальный параметр набора параметров в качестве обязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="1f92d-107">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="1f92d-108">Однако если вы хотите, чтобы командлет выполнялся без указания каких бы то ни было параметров, параметр UNIQUE может быть необязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="1f92d-108">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="1f92d-109">Например, уникальный параметр `Get-Command` командлета является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1f92d-109">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="1f92d-110">Определение двух наборов параметров</span><span class="sxs-lookup"><span data-stu-id="1f92d-110">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="1f92d-111">Добавьте `ParameterSet` ключевое слово в атрибут Parameter для уникального параметра первого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="1f92d-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. <span data-ttu-id="1f92d-112">Добавьте `ParameterSet` ключевое слово в атрибут Parameter для уникального параметра второго набора параметров.</span><span class="sxs-lookup"><span data-stu-id="1f92d-112">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. <span data-ttu-id="1f92d-113">Для параметра, который принадлежит обоим наборам параметров, добавьте атрибут Parameter для каждого набора параметров, а затем добавьте `ParameterSet` ключевое слово в каждый набор.</span><span class="sxs-lookup"><span data-stu-id="1f92d-113">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="1f92d-114">В каждом атрибуте параметра можно указать способ определения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="1f92d-114">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="1f92d-115">Параметр может быть необязательным в одном наборе и обязателен в другом.</span><span class="sxs-lookup"><span data-stu-id="1f92d-115">A parameter can be optional in one set and mandatory in another.</span></span>

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a><span data-ttu-id="1f92d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f92d-116">See Also</span></span>

[<span data-ttu-id="1f92d-117">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="1f92d-117">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="1f92d-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f92d-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
