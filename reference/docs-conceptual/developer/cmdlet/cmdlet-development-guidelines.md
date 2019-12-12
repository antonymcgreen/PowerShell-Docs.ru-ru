---
title: Рекомендации по разработке командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.assetid: c30cc3c0-e958-4a8f-b81f-1e38de772f13
caps.latest.revision: 14
ms.openlocfilehash: 89c7682e87fa6f389349fc44275be0d2ffc83957
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369923"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="8ec9f-102">Рекомендации по разработке командлетов</span><span class="sxs-lookup"><span data-stu-id="8ec9f-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="8ec9f-103">В подразделах этого раздела приводятся рекомендации по разработке, которые можно использовать для создания командлетов правильного формата.</span><span class="sxs-lookup"><span data-stu-id="8ec9f-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="8ec9f-104">Используя общие функциональные возможности среды выполнения Windows PowerShell и, следуя этим рекомендациям, можно разрабатывать надежные командлеты с минимальными усилиями и обеспечить единообразную работу пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ec9f-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="8ec9f-105">Кроме того, вы уменьшите нагрузку на тест, так как для них не требуется повторное тестирование.</span><span class="sxs-lookup"><span data-stu-id="8ec9f-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8ec9f-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="8ec9f-106">In This Section</span></span>

- [<span data-ttu-id="8ec9f-107">Необходимые рекомендации по разработке</span><span class="sxs-lookup"><span data-stu-id="8ec9f-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="8ec9f-108">Настоятельно рекомендуется руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="8ec9f-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="8ec9f-109">Рекомендации по разработке рекомендаций</span><span class="sxs-lookup"><span data-stu-id="8ec9f-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="8ec9f-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ec9f-110">See Also</span></span>

[<span data-ttu-id="8ec9f-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ec9f-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="8ec9f-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ec9f-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
