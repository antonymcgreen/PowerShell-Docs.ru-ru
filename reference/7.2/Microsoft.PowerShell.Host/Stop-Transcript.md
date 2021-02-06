---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605284"
---
# <span data-ttu-id="a2855-102">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="a2855-102">Stop-Transcript</span></span>

## <span data-ttu-id="a2855-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a2855-103">SYNOPSIS</span></span>
<span data-ttu-id="a2855-104">Останавливает запись.</span><span class="sxs-lookup"><span data-stu-id="a2855-104">Stops a transcript.</span></span>

## <span data-ttu-id="a2855-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2855-105">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="a2855-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2855-106">DESCRIPTION</span></span>

<span data-ttu-id="a2855-107">`Stop-Transcript`Командлет останавливает запись, которая была запущена `Start-Transcript` командлетом.</span><span class="sxs-lookup"><span data-stu-id="a2855-107">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="a2855-108">Кроме того, можно завершить сеанс, чтобы прекратить запись разговора.</span><span class="sxs-lookup"><span data-stu-id="a2855-108">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="a2855-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="a2855-109">EXAMPLES</span></span>

### <span data-ttu-id="a2855-110">Пример 1. завершение всех записей</span><span class="sxs-lookup"><span data-stu-id="a2855-110">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="a2855-111">Эта команда останавливает все записи.</span><span class="sxs-lookup"><span data-stu-id="a2855-111">This command stops all transcripts.</span></span>

## <span data-ttu-id="a2855-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2855-112">PARAMETERS</span></span>

### <span data-ttu-id="a2855-113">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a2855-113">CommonParameters</span></span>

<span data-ttu-id="a2855-114">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2855-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2855-115">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2855-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2855-116">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a2855-116">INPUTS</span></span>

### <span data-ttu-id="a2855-117">None</span><span class="sxs-lookup"><span data-stu-id="a2855-117">None</span></span>

<span data-ttu-id="a2855-118">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="a2855-118">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a2855-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a2855-119">OUTPUTS</span></span>

### <span data-ttu-id="a2855-120">System.String</span><span class="sxs-lookup"><span data-stu-id="a2855-120">System.String</span></span>

<span data-ttu-id="a2855-121">Этот командлет возвращает строку, содержащую сообщение о состоянии и путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="a2855-121">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="a2855-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a2855-122">NOTES</span></span>

* <span data-ttu-id="a2855-123">Если запись разговора не была запущена, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a2855-123">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="a2855-124">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a2855-124">RELATED LINKS</span></span>

[<span data-ttu-id="a2855-125">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="a2855-125">Start-Transcript</span></span>](Start-Transcript.md)

