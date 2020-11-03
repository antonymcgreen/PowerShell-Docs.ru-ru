---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113630
Help Version: 7.0.1.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: e14d322fb2f964f06c064c1f9878dc3033947520
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "93230865"
---
# <span data-ttu-id="be9d0-103">Модуль PSReadLine</span><span class="sxs-lookup"><span data-stu-id="be9d0-103">PSReadLine Module</span></span>

## <span data-ttu-id="be9d0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="be9d0-104">Description</span></span>

<span data-ttu-id="be9d0-105">Модуль PSReadLine содержит командлеты, позволяющие настроить среду редактирования командной строки в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be9d0-105">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="be9d0-106">В этих статьях описываются PSReadLine версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="be9d0-106">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="be9d0-107">Эта версия поставляется в PowerShell V6 и Windows 10 октября 2018 с обновлением (сборка 1809).</span><span class="sxs-lookup"><span data-stu-id="be9d0-107">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="be9d0-108">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="be9d0-108">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="be9d0-109">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="be9d0-109">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="be9d0-110">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="be9d0-110">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="be9d0-111">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="be9d0-111">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="be9d0-112">Командлеты PSReadLine</span><span class="sxs-lookup"><span data-stu-id="be9d0-112">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="be9d0-113">псконсолехостреадлине</span><span class="sxs-lookup"><span data-stu-id="be9d0-113">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="be9d0-114">Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="be9d0-114">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="be9d0-115">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="be9d0-115">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="be9d0-116">Возвращает ключевые привязки для модуля PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="be9d0-116">Gets the key bindings for the PSReadLine module.</span></span>

### [<span data-ttu-id="be9d0-117">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="be9d0-117">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="be9d0-118">Получает значения для параметров, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="be9d0-118">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="be9d0-119">псконсолехостреадлине</span><span class="sxs-lookup"><span data-stu-id="be9d0-119">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="be9d0-120">Эта функция является основной точкой входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="be9d0-120">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="be9d0-121">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="be9d0-121">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="be9d0-122">Удаляет привязку клавиш.</span><span class="sxs-lookup"><span data-stu-id="be9d0-122">Removes a key binding.</span></span>

### [<span data-ttu-id="be9d0-123">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="be9d0-123">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="be9d0-124">Привязывает ключи к функциям, определяемым пользователем или PSReadLine Key.</span><span class="sxs-lookup"><span data-stu-id="be9d0-124">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="be9d0-125">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="be9d0-125">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="be9d0-126">Настройка поведения редактирования командной строки в **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="be9d0-126">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

