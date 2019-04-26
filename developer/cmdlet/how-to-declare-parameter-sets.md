---
title: Как объявить наборы параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067898"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="15da2-102">Как объявить наборы параметров</span><span class="sxs-lookup"><span data-stu-id="15da2-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="15da2-103">В этом примере показано, как определить два набора параметров, при объявлении параметров для командлета.</span><span class="sxs-lookup"><span data-stu-id="15da2-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="15da2-104">Каждый набор параметров имеет уникальный параметр и общий параметр, который используется в обоих наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="15da2-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="15da2-105">Дополнительные сведения о наборах параметров, включая способы указания набор параметров по умолчанию, см. в разделе [командлет задает параметр](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="15da2-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15da2-106">По возможности определите параметр unique командлета набор параметров, что обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="15da2-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="15da2-107">Тем не менее если требуется, чтобы командлет для запуска без указания параметров, уникальный параметр может быть необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="15da2-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="15da2-108">Например, параметр unique командлета `Get-Command` командлет является необязательным.</span><span class="sxs-lookup"><span data-stu-id="15da2-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="15da2-109">Как определить два набора параметров</span><span class="sxs-lookup"><span data-stu-id="15da2-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="15da2-110">Добавление `ParameterSet` слово атрибут параметра для параметра уникальный первого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="15da2-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

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

2. <span data-ttu-id="15da2-111">Добавление `ParameterSet` ключевое слово, чтобы атрибут параметра для параметр unique командлета второй набор параметров.</span><span class="sxs-lookup"><span data-stu-id="15da2-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

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

3. <span data-ttu-id="15da2-112">Для параметра, который принадлежит обоих наборов параметров, добавьте атрибут параметра для каждого набора параметров, а затем добавьте `ParameterSet` ключевое слово для каждого набора.</span><span class="sxs-lookup"><span data-stu-id="15da2-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="15da2-113">В каждом атрибуте параметра можно указать, как определен этот параметр.</span><span class="sxs-lookup"><span data-stu-id="15da2-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="15da2-114">Параметр может быть необязательным в одном наборе и обязательным в другой.</span><span class="sxs-lookup"><span data-stu-id="15da2-114">A parameter can be optional in one set and mandatory in another.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="15da2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="15da2-115">See Also</span></span>

[<span data-ttu-id="15da2-116">Наборы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="15da2-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="15da2-117">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15da2-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
