---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: da71d4ef896befaadd7ed64f9a013dc19508a54c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604562"
---
# <span data-ttu-id="3ca42-102">Модуль PSReadLine</span><span class="sxs-lookup"><span data-stu-id="3ca42-102">PSReadLine Module</span></span>

## <span data-ttu-id="3ca42-103">Описание</span><span class="sxs-lookup"><span data-stu-id="3ca42-103">Description</span></span>

<span data-ttu-id="3ca42-104">Модуль PSReadLine содержит командлеты, позволяющие настроить среду редактирования командной строки в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ca42-104">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="3ca42-105">В этих статьях описываются PSReadLine версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="3ca42-105">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="3ca42-106">Эта версия поставляется в PowerShell V6 и Windows 10 октября 2018 с обновлением (сборка 1809).</span><span class="sxs-lookup"><span data-stu-id="3ca42-106">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="3ca42-107">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="3ca42-107">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="3ca42-108">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="3ca42-108">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="3ca42-109">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="3ca42-109">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="3ca42-110">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="3ca42-110">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="3ca42-111">Командлеты PSReadLine</span><span class="sxs-lookup"><span data-stu-id="3ca42-111">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="3ca42-112">псконсолехостреадлине</span><span class="sxs-lookup"><span data-stu-id="3ca42-112">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="3ca42-113">Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="3ca42-113">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="3ca42-114">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="3ca42-114">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="3ca42-115">Возвращает связанные ключевые функции для модуля PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="3ca42-115">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="3ca42-116">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="3ca42-116">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="3ca42-117">Получает значения для параметров, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="3ca42-117">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="3ca42-118">псконсолехостреадлине</span><span class="sxs-lookup"><span data-stu-id="3ca42-118">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="3ca42-119">Эта функция является основной точкой входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="3ca42-119">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="3ca42-120">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="3ca42-120">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="3ca42-121">Удаляет привязку клавиш.</span><span class="sxs-lookup"><span data-stu-id="3ca42-121">Removes a key binding.</span></span>

### [<span data-ttu-id="3ca42-122">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="3ca42-122">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="3ca42-123">Привязывает ключи к функциям, определяемым пользователем или PSReadLine Key.</span><span class="sxs-lookup"><span data-stu-id="3ca42-123">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="3ca42-124">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="3ca42-124">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="3ca42-125">Настройка поведения редактирования командной строки в **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="3ca42-125">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

