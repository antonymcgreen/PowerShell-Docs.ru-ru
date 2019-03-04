---
title: Форматирование параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251189"
---
# <a name="format-parameters"></a><span data-ttu-id="cf7ae-102">Параметры форматирования</span><span class="sxs-lookup"><span data-stu-id="cf7ae-102">Format Parameters</span></span>

<span data-ttu-id="cf7ae-103">Ниже перечислены рекомендуемые имена и функции для параметров, которые используются для форматирования или для формирования данных.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="cf7ae-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="cf7ae-104">Parameter</span></span>|<span data-ttu-id="cf7ae-105">Функции</span><span class="sxs-lookup"><span data-stu-id="cf7ae-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="cf7ae-106">**как**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-106">**As**</span></span><br><span data-ttu-id="cf7ae-107">Тип данных: Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="cf7ae-107">Data type: Keyword</span></span>|<span data-ttu-id="cf7ae-108">Реализуйте этот параметр, чтобы задать формат выходных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="cf7ae-109">Например возможные значения может быть текст или скрипт.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="cf7ae-110">**Двоичный**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-110">**Binary**</span></span><br><span data-ttu-id="cf7ae-111">Тип данных: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cf7ae-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="cf7ae-112">Реализуйте этот параметр, чтобы указать, что командлет обрабатывает двоичные значения.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="cf7ae-113">**Кодировка**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-113">**Encoding**</span></span><br><span data-ttu-id="cf7ae-114">Тип данных: Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="cf7ae-114">Data type: Keyword</span></span>|<span data-ttu-id="cf7ae-115">Реализуйте этот параметр, чтобы указать тип кодировки, который поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="cf7ae-116">Например возможные значения может быть ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, байтов и строки.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="cf7ae-117">**NewLine**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-117">**NewLine**</span></span><br><span data-ttu-id="cf7ae-118">Тип данных: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cf7ae-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="cf7ae-119">Реализуйте этот параметр, таким образом, чтобы символы новой строки поддерживаются в том случае, если указан параметр.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="cf7ae-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-120">**ShortName**</span></span><br><span data-ttu-id="cf7ae-121">Тип данных: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cf7ae-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="cf7ae-122">Таким образом, чтобы короткие имена поддерживаются в том случае, если этот параметр указан, Реализуйте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="cf7ae-123">**Ширина**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-123">**Width**</span></span><br><span data-ttu-id="cf7ae-124">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="cf7ae-124">Data type: Int32</span></span>|<span data-ttu-id="cf7ae-125">Реализуйте этот параметр, чтобы пользователь может указать ширину выходных данных устройства.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="cf7ae-126">**Wrap**</span><span class="sxs-lookup"><span data-stu-id="cf7ae-126">**Wrap**</span></span><br><span data-ttu-id="cf7ae-127">Тип данных: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cf7ae-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="cf7ae-128">Реализуйте этот параметр, чтобы обтекания текстом поддерживается в том случае, если этот параметр указан.</span><span class="sxs-lookup"><span data-stu-id="cf7ae-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="cf7ae-129">См. также</span><span class="sxs-lookup"><span data-stu-id="cf7ae-129">See Also</span></span>

[<span data-ttu-id="cf7ae-130">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="cf7ae-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="cf7ae-131">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf7ae-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="cf7ae-132">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf7ae-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
