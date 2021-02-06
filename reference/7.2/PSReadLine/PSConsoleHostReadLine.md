---
external help file: PSReadLine-help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: псконсолехостреадлине
ms.openlocfilehash: e02f06137395e187cfe86eb1aeb4b30dbb3f09f1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599997"
---
# <span data-ttu-id="3ed7d-102">псконсолехостреадлине</span><span class="sxs-lookup"><span data-stu-id="3ed7d-102">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="3ed7d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3ed7d-103">SYNOPSIS</span></span>
<span data-ttu-id="3ed7d-104">Эта функция является основной точкой входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-104">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="3ed7d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ed7d-105">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="3ed7d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ed7d-106">DESCRIPTION</span></span>

<span data-ttu-id="3ed7d-107">`PSConsoleHostReadLine` Главная точка входа для модуля PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-107">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="3ed7d-108">Узел консоли PowerShell автоматически загружает модуль PSReadLine и вызывает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-108">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="3ed7d-109">В нормальных операционных условиях эта функция не предназначена для использования из командной строки.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-109">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="3ed7d-110">Точка расширения `PSConsoleHostReadLine` является особой для узла консоли.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-110">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="3ed7d-111">Узел вызывает любой псевдоним, функцию или скрипт с этим именем.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-111">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="3ed7d-112">PSReadLine определяет эту функцию, чтобы она вызывалась из узла консоли.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-112">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="3ed7d-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="3ed7d-113">EXAMPLES</span></span>

### <span data-ttu-id="3ed7d-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="3ed7d-114">Example 1</span></span>

<span data-ttu-id="3ed7d-115">Эта функция не предназначена для использования из командной строки.</span><span class="sxs-lookup"><span data-stu-id="3ed7d-115">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="3ed7d-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ed7d-116">PARAMETERS</span></span>

## <span data-ttu-id="3ed7d-117">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3ed7d-117">INPUTS</span></span>

### <span data-ttu-id="3ed7d-118">None</span><span class="sxs-lookup"><span data-stu-id="3ed7d-118">None</span></span>

## <span data-ttu-id="3ed7d-119">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3ed7d-119">OUTPUTS</span></span>

### <span data-ttu-id="3ed7d-120">None</span><span class="sxs-lookup"><span data-stu-id="3ed7d-120">None</span></span>

## <span data-ttu-id="3ed7d-121">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3ed7d-121">NOTES</span></span>

## <span data-ttu-id="3ed7d-122">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3ed7d-122">RELATED LINKS</span></span>

[<span data-ttu-id="3ed7d-123">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="3ed7d-123">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

