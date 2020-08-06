---
title: Рекомендации по разработке командлетов | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.openlocfilehash: 5dd83b12a9052ff5f146c4c4e077a9358907cbd0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784492"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="7498e-102">Рекомендации по разработке командлетов</span><span class="sxs-lookup"><span data-stu-id="7498e-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="7498e-103">В подразделах этого раздела приводятся рекомендации по разработке, которые можно использовать для создания командлетов правильного формата.</span><span class="sxs-lookup"><span data-stu-id="7498e-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="7498e-104">Используя общие функциональные возможности среды выполнения Windows PowerShell и, следуя этим рекомендациям, можно разрабатывать надежные командлеты с минимальными усилиями и обеспечить единообразную работу пользователя.</span><span class="sxs-lookup"><span data-stu-id="7498e-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="7498e-105">Кроме того, вы уменьшите нагрузку на тест, так как для них не требуется повторное тестирование.</span><span class="sxs-lookup"><span data-stu-id="7498e-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7498e-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7498e-106">In This Section</span></span>

- [<span data-ttu-id="7498e-107">Обязательные требования к разработке</span><span class="sxs-lookup"><span data-stu-id="7498e-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="7498e-108">Настоятельные рекомендации по разработке</span><span class="sxs-lookup"><span data-stu-id="7498e-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="7498e-109">Советы по разработке</span><span class="sxs-lookup"><span data-stu-id="7498e-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="7498e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7498e-110">See Also</span></span>

[<span data-ttu-id="7498e-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7498e-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="7498e-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7498e-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
