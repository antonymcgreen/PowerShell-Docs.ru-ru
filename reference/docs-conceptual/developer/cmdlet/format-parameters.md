---
ms.date: 09/13/2016
ms.topic: reference
title: Параметры форматирования
description: Параметры форматирования
ms.openlocfilehash: 5f970683fedc71b208ff6becad761d94611a91a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652825"
---
# <a name="format-parameters"></a><span data-ttu-id="8d0ea-103">Параметры форматирования</span><span class="sxs-lookup"><span data-stu-id="8d0ea-103">Format Parameters</span></span>

<span data-ttu-id="8d0ea-104">В следующей таблице перечислены рекомендуемые имена и функциональные возможности для параметров, используемых для форматирования или создания данных.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-104">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="8d0ea-105">Параметр</span><span class="sxs-lookup"><span data-stu-id="8d0ea-105">Parameter</span></span>|<span data-ttu-id="8d0ea-106">функциональное назначение;</span><span class="sxs-lookup"><span data-stu-id="8d0ea-106">Functionality</span></span>|
|---|---|
|<span data-ttu-id="8d0ea-107">**Тех**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-107">**As**</span></span><br><span data-ttu-id="8d0ea-108">Тип данных: ключевое слово</span><span class="sxs-lookup"><span data-stu-id="8d0ea-108">Data type: Keyword</span></span>|<span data-ttu-id="8d0ea-109">Реализуйте этот параметр, чтобы указать формат выходных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-109">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="8d0ea-110">Например, возможными значениями могут быть Text или script.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-110">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="8d0ea-111">**Двоичный**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-111">**Binary**</span></span><br><span data-ttu-id="8d0ea-112">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="8d0ea-112">Data type: SwitchParameter</span></span>|<span data-ttu-id="8d0ea-113">Реализуйте этот параметр, чтобы указать, что командлет обрабатывает двоичные значения.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-113">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="8d0ea-114">**Кодирование**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-114">**Encoding**</span></span><br><span data-ttu-id="8d0ea-115">Тип данных: ключевое слово</span><span class="sxs-lookup"><span data-stu-id="8d0ea-115">Data type: Keyword</span></span>|<span data-ttu-id="8d0ea-116">Реализуйте этот параметр, чтобы указать поддерживаемый тип кодировки.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-116">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="8d0ea-117">Например, возможные значения: ASCII, UTF8, Юникод, UTF7, BigEndianUnicode, Byte и String.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-117">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="8d0ea-118">**Новой строки**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-118">**NewLine**</span></span><br><span data-ttu-id="8d0ea-119">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="8d0ea-119">Data type: SwitchParameter</span></span>|<span data-ttu-id="8d0ea-120">Реализуйте этот параметр, чтобы символы новой строки поддерживались при указании параметра.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-120">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="8d0ea-121">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-121">**ShortName**</span></span><br><span data-ttu-id="8d0ea-122">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="8d0ea-122">Data type: SwitchParameter</span></span>|<span data-ttu-id="8d0ea-123">Реализуйте этот параметр, чтобы при указании параметра поддерживались короткие имена.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-123">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="8d0ea-124">**Width**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-124">**Width**</span></span><br><span data-ttu-id="8d0ea-125">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="8d0ea-125">Data type: Int32</span></span>|<span data-ttu-id="8d0ea-126">Реализуйте этот параметр, чтобы пользователь мог указать ширину выходного устройства.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-126">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="8d0ea-127">**оборачивание;**</span><span class="sxs-lookup"><span data-stu-id="8d0ea-127">**Wrap**</span></span><br><span data-ttu-id="8d0ea-128">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="8d0ea-128">Data type: SwitchParameter</span></span>|<span data-ttu-id="8d0ea-129">Реализуйте этот параметр, чтобы при указании параметра поддерживался перенос текста.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-129">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="8d0ea-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d0ea-130">See Also</span></span>

[<span data-ttu-id="8d0ea-131">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="8d0ea-131">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="8d0ea-132">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0ea-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="8d0ea-133">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0ea-133">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
