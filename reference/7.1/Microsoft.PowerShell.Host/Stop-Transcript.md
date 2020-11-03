---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 86903ca648ff3ee58ec939143b7881741827f453
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209344"
---
# <span data-ttu-id="073e8-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="073e8-103">Stop-Transcript</span></span>

## <span data-ttu-id="073e8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="073e8-104">SYNOPSIS</span></span>
<span data-ttu-id="073e8-105">Останавливает запись.</span><span class="sxs-lookup"><span data-stu-id="073e8-105">Stops a transcript.</span></span>

## <span data-ttu-id="073e8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="073e8-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="073e8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="073e8-107">DESCRIPTION</span></span>

<span data-ttu-id="073e8-108">`Stop-Transcript`Командлет останавливает запись, которая была запущена `Start-Transcript` командлетом.</span><span class="sxs-lookup"><span data-stu-id="073e8-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="073e8-109">Кроме того, можно завершить сеанс, чтобы прекратить запись разговора.</span><span class="sxs-lookup"><span data-stu-id="073e8-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="073e8-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="073e8-110">EXAMPLES</span></span>

### <span data-ttu-id="073e8-111">Пример 1. завершение всех записей</span><span class="sxs-lookup"><span data-stu-id="073e8-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="073e8-112">Эта команда останавливает все записи.</span><span class="sxs-lookup"><span data-stu-id="073e8-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="073e8-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="073e8-113">PARAMETERS</span></span>

### <span data-ttu-id="073e8-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="073e8-114">CommonParameters</span></span>

<span data-ttu-id="073e8-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="073e8-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="073e8-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="073e8-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="073e8-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="073e8-117">INPUTS</span></span>

### <span data-ttu-id="073e8-118">Нет</span><span class="sxs-lookup"><span data-stu-id="073e8-118">None</span></span>

<span data-ttu-id="073e8-119">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="073e8-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="073e8-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="073e8-120">OUTPUTS</span></span>

### <span data-ttu-id="073e8-121">System.String</span><span class="sxs-lookup"><span data-stu-id="073e8-121">System.String</span></span>

<span data-ttu-id="073e8-122">Этот командлет возвращает строку, содержащую сообщение о состоянии и путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="073e8-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="073e8-123">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="073e8-123">NOTES</span></span>

* <span data-ttu-id="073e8-124">Если запись разговора не была запущена, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="073e8-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="073e8-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="073e8-125">RELATED LINKS</span></span>

[<span data-ttu-id="073e8-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="073e8-126">Start-Transcript</span></span>](Start-Transcript.md)

