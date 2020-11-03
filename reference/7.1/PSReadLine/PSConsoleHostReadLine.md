---
external help file: PSReadLine-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: псконсолехостреадлине
ms.openlocfilehash: 10e79223801a32a2409de253daabe1019ae1b64b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233185"
---
# <span data-ttu-id="961ec-103">псконсолехостреадлине</span><span class="sxs-lookup"><span data-stu-id="961ec-103">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="961ec-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="961ec-104">SYNOPSIS</span></span>
<span data-ttu-id="961ec-105">Эта функция является основной точкой входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="961ec-105">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="961ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="961ec-106">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="961ec-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="961ec-107">DESCRIPTION</span></span>

<span data-ttu-id="961ec-108">`PSConsoleHostReadLine` Главная точка входа для модуля PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="961ec-108">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="961ec-109">Узел консоли PowerShell автоматически загружает модуль PSReadLine и вызывает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="961ec-109">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="961ec-110">В нормальных операционных условиях эта функция не предназначена для использования из командной строки.</span><span class="sxs-lookup"><span data-stu-id="961ec-110">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="961ec-111">Точка расширения `PSConsoleHostReadLine` является особой для узла консоли.</span><span class="sxs-lookup"><span data-stu-id="961ec-111">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="961ec-112">Узел вызывает любой псевдоним, функцию или скрипт с этим именем.</span><span class="sxs-lookup"><span data-stu-id="961ec-112">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="961ec-113">PSReadLine определяет эту функцию, чтобы она вызывалась из узла консоли.</span><span class="sxs-lookup"><span data-stu-id="961ec-113">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="961ec-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="961ec-114">EXAMPLES</span></span>

### <span data-ttu-id="961ec-115">Пример 1</span><span class="sxs-lookup"><span data-stu-id="961ec-115">Example 1</span></span>

<span data-ttu-id="961ec-116">Эта функция не предназначена для использования из командной строки.</span><span class="sxs-lookup"><span data-stu-id="961ec-116">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="961ec-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="961ec-117">PARAMETERS</span></span>

## <span data-ttu-id="961ec-118">Входные данные</span><span class="sxs-lookup"><span data-stu-id="961ec-118">INPUTS</span></span>

### <span data-ttu-id="961ec-119">Нет</span><span class="sxs-lookup"><span data-stu-id="961ec-119">None</span></span>

## <span data-ttu-id="961ec-120">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="961ec-120">OUTPUTS</span></span>

### <span data-ttu-id="961ec-121">Нет</span><span class="sxs-lookup"><span data-stu-id="961ec-121">None</span></span>

## <span data-ttu-id="961ec-122">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="961ec-122">NOTES</span></span>

## <span data-ttu-id="961ec-123">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="961ec-123">RELATED LINKS</span></span>

[<span data-ttu-id="961ec-124">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="961ec-124">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

