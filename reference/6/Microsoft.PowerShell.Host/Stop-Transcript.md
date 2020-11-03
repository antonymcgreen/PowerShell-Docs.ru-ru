---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 5f02f59e778c55b2292bb4533cf2f8aaab2dbb7d
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93208985"
---
# <span data-ttu-id="345b1-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="345b1-103">Stop-Transcript</span></span>

## <span data-ttu-id="345b1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="345b1-104">SYNOPSIS</span></span>
<span data-ttu-id="345b1-105">Останавливает запись.</span><span class="sxs-lookup"><span data-stu-id="345b1-105">Stops a transcript.</span></span>

## <span data-ttu-id="345b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="345b1-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="345b1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="345b1-107">DESCRIPTION</span></span>

<span data-ttu-id="345b1-108">`Stop-Transcript`Командлет останавливает запись, которая была запущена `Start-Transcript` командлетом.</span><span class="sxs-lookup"><span data-stu-id="345b1-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="345b1-109">Кроме того, можно завершить сеанс, чтобы прекратить запись разговора.</span><span class="sxs-lookup"><span data-stu-id="345b1-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="345b1-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="345b1-110">EXAMPLES</span></span>

### <span data-ttu-id="345b1-111">Пример 1. завершение всех записей</span><span class="sxs-lookup"><span data-stu-id="345b1-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="345b1-112">Эта команда останавливает все записи.</span><span class="sxs-lookup"><span data-stu-id="345b1-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="345b1-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="345b1-113">PARAMETERS</span></span>

### <span data-ttu-id="345b1-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="345b1-114">CommonParameters</span></span>

<span data-ttu-id="345b1-115">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="345b1-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="345b1-116">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="345b1-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="345b1-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="345b1-117">INPUTS</span></span>

### <span data-ttu-id="345b1-118">Нет</span><span class="sxs-lookup"><span data-stu-id="345b1-118">None</span></span>

<span data-ttu-id="345b1-119">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="345b1-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="345b1-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="345b1-120">OUTPUTS</span></span>

### <span data-ttu-id="345b1-121">System.String</span><span class="sxs-lookup"><span data-stu-id="345b1-121">System.String</span></span>

<span data-ttu-id="345b1-122">Этот командлет возвращает строку, содержащую сообщение о состоянии и путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="345b1-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="345b1-123">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="345b1-123">NOTES</span></span>

* <span data-ttu-id="345b1-124">Если запись разговора не была запущена, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="345b1-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="345b1-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="345b1-125">RELATED LINKS</span></span>

[<span data-ttu-id="345b1-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="345b1-126">Start-Transcript</span></span>](Start-Transcript.md)
