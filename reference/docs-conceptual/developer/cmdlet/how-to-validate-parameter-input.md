---
title: Проверка входных параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6c700c8-0889-49a1-a990-8c6e9aaf4735
caps.latest.revision: 6
ms.openlocfilehash: 5166213f8247fa23d5e0b3fdfd2367062d595169
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365483"
---
# <a name="how-to-validate-parameter-input"></a><span data-ttu-id="8b47d-102">Как проверить входные параметры</span><span class="sxs-lookup"><span data-stu-id="8b47d-102">How to Validate Parameter Input</span></span>

<span data-ttu-id="8b47d-103">Этот раздел содержит примеры, демонстрирующие проверку входных параметров с помощью различных атрибутов для реализации правил проверки.</span><span class="sxs-lookup"><span data-stu-id="8b47d-103">This section contains examples that show how to validate parameter input by using various attributes to implement validation rules.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8b47d-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="8b47d-104">In This Section</span></span>

<span data-ttu-id="8b47d-105">[Проверка набора аргументов](./how-to-validate-an-argument-set.md) Описывает, как проверить набор аргументов с помощью атрибута набора аргументов.</span><span class="sxs-lookup"><span data-stu-id="8b47d-105">[How to Validate an Argument Set](./how-to-validate-an-argument-set.md) Describes how to validate an argument set by using the ArgumentSet attribute.</span></span>

<span data-ttu-id="8b47d-106">[Проверка диапазона аргументов](./how-to-validate-an-argument-range.md) Описывает, как проверить диапазон аргументов с помощью атрибута Аргументранже.</span><span class="sxs-lookup"><span data-stu-id="8b47d-106">[How to Validate an Argument Range](./how-to-validate-an-argument-range.md) Describes how to validate an argument range by using the ArgumentRange attribute.</span></span>

<span data-ttu-id="8b47d-107">[Проверка шаблона аргумента](./how-to-validate-an-argument-pattern.md) Описывает, как проверить шаблон аргумента с помощью атрибута Аргументпаттерн.</span><span class="sxs-lookup"><span data-stu-id="8b47d-107">[How to Validate an Argument Pattern](./how-to-validate-an-argument-pattern.md) Describes how to validate an argument pattern by using the ArgumentPattern attribute.</span></span>

<span data-ttu-id="8b47d-108">[Проверка длины аргумента](./how-to-validate-the-argument-length.md) Описывает, как проверить длину аргумента с помощью атрибута Аргументленгс.</span><span class="sxs-lookup"><span data-stu-id="8b47d-108">[How to Validate the Argument Length](./how-to-validate-the-argument-length.md) Describes how to validate the length of an argument by using the ArgumentLength attribute.</span></span>

<span data-ttu-id="8b47d-109">[Проверка числа аргументов](./how-to-validate-an-argument-count.md) Описывает, как проверить число аргументов с помощью атрибута Аргументкаунт.</span><span class="sxs-lookup"><span data-stu-id="8b47d-109">[How to Validate an Argument Count](./how-to-validate-an-argument-count.md) Describes how to validate an argument count by using the ArgumentCount attribute.</span></span>

<span data-ttu-id="8b47d-110">Способ объявления параметра может повлиять на проверку.</span><span class="sxs-lookup"><span data-stu-id="8b47d-110">The way a parameter is declared can affect validation.</span></span> <span data-ttu-id="8b47d-111">Дополнительные сведения см. [в разделе как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8b47d-111">For more information, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

## <a name="reference"></a><span data-ttu-id="8b47d-112">Ссылка</span><span class="sxs-lookup"><span data-stu-id="8b47d-112">Reference</span></span>

## <a name="see-also"></a><span data-ttu-id="8b47d-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b47d-113">See Also</span></span>

[<span data-ttu-id="8b47d-114">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b47d-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
