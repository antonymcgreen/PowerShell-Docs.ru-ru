---
title: Объявление наборов параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365613"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="8bd78-102">Как объявить наборы параметров</span><span class="sxs-lookup"><span data-stu-id="8bd78-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="8bd78-103">В этом примере показано, как определить два набора параметров при объявлении параметров для командлета.</span><span class="sxs-lookup"><span data-stu-id="8bd78-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="8bd78-104">Каждый набор параметров имеет как уникальный параметр, так и общий параметр, который используется обоими наборами параметров.</span><span class="sxs-lookup"><span data-stu-id="8bd78-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="8bd78-105">Дополнительные сведения о наборах параметров, в том числе о том, как указать набор параметров по умолчанию, см. в разделе [наборы параметров командлета](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="8bd78-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bd78-106">Везде, где это возможно, определите уникальный параметр набора параметров в качестве обязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="8bd78-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="8bd78-107">Однако если вы хотите, чтобы командлет выполнялся без указания каких бы то ни было параметров, параметр UNIQUE может быть необязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="8bd78-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="8bd78-108">Например, параметр Unique командлета `Get-Command` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8bd78-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="8bd78-109">Определение двух наборов параметров</span><span class="sxs-lookup"><span data-stu-id="8bd78-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="8bd78-110">Добавьте ключевое слово `ParameterSet` в атрибут Parameter для уникального параметра первого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="8bd78-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

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

2. <span data-ttu-id="8bd78-111">Добавьте ключевое слово `ParameterSet` в атрибут Parameter для уникального параметра второго набора параметров.</span><span class="sxs-lookup"><span data-stu-id="8bd78-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

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

3. <span data-ttu-id="8bd78-112">Для параметра, который принадлежит обоим наборам параметров, добавьте атрибут Parameter для каждого набора параметров, а затем добавьте к каждому набору ключевое слово `ParameterSet`.</span><span class="sxs-lookup"><span data-stu-id="8bd78-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="8bd78-113">В каждом атрибуте параметра можно указать способ определения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8bd78-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="8bd78-114">Параметр может быть необязательным в одном наборе и обязателен в другом.</span><span class="sxs-lookup"><span data-stu-id="8bd78-114">A parameter can be optional in one set and mandatory in another.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8bd78-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="8bd78-115">See Also</span></span>

[<span data-ttu-id="8bd78-116">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="8bd78-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="8bd78-117">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bd78-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
