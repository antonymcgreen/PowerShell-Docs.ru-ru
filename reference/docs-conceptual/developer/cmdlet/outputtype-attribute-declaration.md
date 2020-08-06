---
title: Объявление атрибута OutputType | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786549"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="9c4b8-102">Объявление атрибута для типа выходных данных</span><span class="sxs-lookup"><span data-stu-id="9c4b8-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="9c4b8-103">`OutputType`Атрибут определяет типы .NET Framework, возвращаемые командлетом, функцией или скриптом.</span><span class="sxs-lookup"><span data-stu-id="9c4b8-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c4b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c4b8-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="9c4b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c4b8-105">Parameters</span></span>

<span data-ttu-id="9c4b8-106">`string[]`Обязательный тип (или `Type[]` ).</span><span class="sxs-lookup"><span data-stu-id="9c4b8-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="9c4b8-107">Указывает типы, возвращаемые функцией командлета или скриптом.</span><span class="sxs-lookup"><span data-stu-id="9c4b8-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="9c4b8-108">Параметерсетнаме (String []) необязательный.</span><span class="sxs-lookup"><span data-stu-id="9c4b8-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="9c4b8-109">Задает наборы параметров, которые возвращают типы, указанные в `type` параметре.</span><span class="sxs-lookup"><span data-stu-id="9c4b8-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="9c4b8-110">Провидеркмдлет необязательный.</span><span class="sxs-lookup"><span data-stu-id="9c4b8-110">providerCmdlet Optional.</span></span> <span data-ttu-id="9c4b8-111">Указывает командлет поставщика, возвращающий типы, указанные в `type` параметре.</span><span class="sxs-lookup"><span data-stu-id="9c4b8-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c4b8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9c4b8-112">See Also</span></span>

[<span data-ttu-id="9c4b8-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c4b8-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
