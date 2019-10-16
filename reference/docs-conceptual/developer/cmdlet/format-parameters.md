---
title: Параметры формата | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369753"
---
# <a name="format-parameters"></a><span data-ttu-id="d2d57-102">Параметры форматирования</span><span class="sxs-lookup"><span data-stu-id="d2d57-102">Format Parameters</span></span>

<span data-ttu-id="d2d57-103">В следующей таблице перечислены рекомендуемые имена и функциональные возможности для параметров, используемых для форматирования или создания данных.</span><span class="sxs-lookup"><span data-stu-id="d2d57-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="d2d57-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="d2d57-104">Parameter</span></span>|<span data-ttu-id="d2d57-105">Функция</span><span class="sxs-lookup"><span data-stu-id="d2d57-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="d2d57-106">**Тех**</span><span class="sxs-lookup"><span data-stu-id="d2d57-106">**As**</span></span><br><span data-ttu-id="d2d57-107">Тип данных: ключевое слово</span><span class="sxs-lookup"><span data-stu-id="d2d57-107">Data type: Keyword</span></span>|<span data-ttu-id="d2d57-108">Реализуйте этот параметр, чтобы указать формат выходных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="d2d57-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="d2d57-109">Например, возможными значениями могут быть Text или script.</span><span class="sxs-lookup"><span data-stu-id="d2d57-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="d2d57-110">**Двоичный**</span><span class="sxs-lookup"><span data-stu-id="d2d57-110">**Binary**</span></span><br><span data-ttu-id="d2d57-111">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="d2d57-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="d2d57-112">Реализуйте этот параметр, чтобы указать, что командлет обрабатывает двоичные значения.</span><span class="sxs-lookup"><span data-stu-id="d2d57-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="d2d57-113">**Шифрования**</span><span class="sxs-lookup"><span data-stu-id="d2d57-113">**Encoding**</span></span><br><span data-ttu-id="d2d57-114">Тип данных: ключевое слово</span><span class="sxs-lookup"><span data-stu-id="d2d57-114">Data type: Keyword</span></span>|<span data-ttu-id="d2d57-115">Реализуйте этот параметр, чтобы указать поддерживаемый тип кодировки.</span><span class="sxs-lookup"><span data-stu-id="d2d57-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="d2d57-116">Например, возможные значения: ASCII, UTF8, Юникод, UTF7, BigEndianUnicode, Byte и String.</span><span class="sxs-lookup"><span data-stu-id="d2d57-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="d2d57-117">**Новой строки**</span><span class="sxs-lookup"><span data-stu-id="d2d57-117">**NewLine**</span></span><br><span data-ttu-id="d2d57-118">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="d2d57-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="d2d57-119">Реализуйте этот параметр, чтобы символы новой строки поддерживались при указании параметра.</span><span class="sxs-lookup"><span data-stu-id="d2d57-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="d2d57-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="d2d57-120">**ShortName**</span></span><br><span data-ttu-id="d2d57-121">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="d2d57-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="d2d57-122">Реализуйте этот параметр, чтобы при указании параметра поддерживались короткие имена.</span><span class="sxs-lookup"><span data-stu-id="d2d57-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="d2d57-123">**Ширина**</span><span class="sxs-lookup"><span data-stu-id="d2d57-123">**Width**</span></span><br><span data-ttu-id="d2d57-124">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="d2d57-124">Data type: Int32</span></span>|<span data-ttu-id="d2d57-125">Реализуйте этот параметр, чтобы пользователь мог указать ширину выходного устройства.</span><span class="sxs-lookup"><span data-stu-id="d2d57-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="d2d57-126">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d2d57-126">**Wrap**</span></span><br><span data-ttu-id="d2d57-127">Тип данных: переключатель</span><span class="sxs-lookup"><span data-stu-id="d2d57-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="d2d57-128">Реализуйте этот параметр, чтобы при указании параметра поддерживался перенос текста.</span><span class="sxs-lookup"><span data-stu-id="d2d57-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="d2d57-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="d2d57-129">See Also</span></span>

[<span data-ttu-id="d2d57-130">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="d2d57-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="d2d57-131">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2d57-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="d2d57-132">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2d57-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
