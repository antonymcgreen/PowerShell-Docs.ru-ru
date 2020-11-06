---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
Locale: en-US
Module Guid: 0e7b895d-2fec-43f7-8cae-11e8d16f6e40
Module Name: ThreadJob
ms.date: 07/09/2019
title: Модуль Среаджоб
ms.openlocfilehash: 4a6abe107ac041f0ce5fa3e5d776bb0ac352685c
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230098"
---
# <span data-ttu-id="f3352-102">Модуль Среаджоб</span><span class="sxs-lookup"><span data-stu-id="f3352-102">ThreadJob Module</span></span>

## <span data-ttu-id="f3352-103">Описание</span><span class="sxs-lookup"><span data-stu-id="f3352-103">Description</span></span>
<span data-ttu-id="f3352-104">Этот модуль расширяет существующий Баккграунджоб PowerShell для включения нового задания **среаджоб** на основе потока.</span><span class="sxs-lookup"><span data-stu-id="f3352-104">This module extends the existing PowerShell BackgroundJob to include a new thread based **ThreadJob** job.</span></span> <span data-ttu-id="f3352-105">Это более упрощенное решение для выполнения параллельных сценариев PowerShell, которые работают в существующей инфраструктуре заданий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3352-105">This is a lighter weight solution for running concurrent PowerShell scripts that works within the existing PowerShell job infrastructure.</span></span>

## <span data-ttu-id="f3352-106">Командлеты Среаджоб</span><span class="sxs-lookup"><span data-stu-id="f3352-106">ThreadJob Cmdlets</span></span>

### [<span data-ttu-id="f3352-107">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="f3352-107">Start-ThreadJob</span></span>](Start-ThreadJob.md)
<span data-ttu-id="f3352-108">Создает фоновые задания, аналогичные `Start-Job` командлету.</span><span class="sxs-lookup"><span data-stu-id="f3352-108">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>