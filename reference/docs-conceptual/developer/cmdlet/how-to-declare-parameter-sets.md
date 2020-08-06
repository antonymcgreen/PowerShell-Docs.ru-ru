---
title: Объявление наборов параметров | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e6d06a9a78356693fe7a338dc5c9207044b23441
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784169"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="603d9-102">Как объявить наборы параметров</span><span class="sxs-lookup"><span data-stu-id="603d9-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="603d9-103">В этом примере показано, как определить два набора параметров при объявлении параметров для командлета.</span><span class="sxs-lookup"><span data-stu-id="603d9-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="603d9-104">Каждый набор параметров имеет как уникальный параметр, так и общий параметр, который используется обоими наборами параметров.</span><span class="sxs-lookup"><span data-stu-id="603d9-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="603d9-105">Дополнительные сведения о наборах параметров, в том числе о том, как указать набор параметров по умолчанию, см. в разделе [наборы параметров командлета](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="603d9-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="603d9-106">Везде, где это возможно, определите уникальный параметр набора параметров в качестве обязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="603d9-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="603d9-107">Однако если вы хотите, чтобы командлет выполнялся без указания каких бы то ни было параметров, параметр UNIQUE может быть необязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="603d9-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="603d9-108">Например, уникальный параметр `Get-Command` командлета является необязательным.</span><span class="sxs-lookup"><span data-stu-id="603d9-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="603d9-109">Определение двух наборов параметров</span><span class="sxs-lookup"><span data-stu-id="603d9-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="603d9-110">Добавьте `ParameterSet` ключевое слово в атрибут Parameter для уникального параметра первого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="603d9-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

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

2. <span data-ttu-id="603d9-111">Добавьте `ParameterSet` ключевое слово в атрибут Parameter для уникального параметра второго набора параметров.</span><span class="sxs-lookup"><span data-stu-id="603d9-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

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

3. <span data-ttu-id="603d9-112">Для параметра, который принадлежит обоим наборам параметров, добавьте атрибут Parameter для каждого набора параметров, а затем добавьте `ParameterSet` ключевое слово в каждый набор.</span><span class="sxs-lookup"><span data-stu-id="603d9-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="603d9-113">В каждом атрибуте параметра можно указать способ определения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="603d9-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="603d9-114">Параметр может быть необязательным в одном наборе и обязателен в другом.</span><span class="sxs-lookup"><span data-stu-id="603d9-114">A parameter can be optional in one set and mandatory in another.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="603d9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="603d9-115">See Also</span></span>

[<span data-ttu-id="603d9-116">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="603d9-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="603d9-117">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="603d9-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
