---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.topic: conceptual
title: пример шаблона с описанием известной проблемы или ограничения
ms.openlocfilehash: 453d4e40b906ebcab7314f04e138ded271338846
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34221941"
---
><span data-ttu-id="5d84d-103">Примечание. Предоставьте предложенное описательное название и краткое описание.</span><span class="sxs-lookup"><span data-stu-id="5d84d-103">Note: provide a proposed descriptive title and a brief description</span></span>

## <a name="example-erroneous-executionpolicy-errors"></a><span data-ttu-id="5d84d-104">Пример. Ложные ошибки ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="5d84d-104">Example: Erroneous ExecutionPolicy errors</span></span> ##
<span data-ttu-id="5d84d-105">В Windows 7 использование модулей PowerShell и ресурсов DSC может привести к возникновению ошибок, связанных с ExecutionPolicy.</span><span class="sxs-lookup"><span data-stu-id="5d84d-105">On Windows 7, the use of PowerShell modules and DSC resources may result in errors reported about ExecutionPolicy.</span></span>

### <a name="resolution"></a><span data-ttu-id="5d84d-106">Разрешение</span><span class="sxs-lookup"><span data-stu-id="5d84d-106">Resolution</span></span>

<span data-ttu-id="5d84d-107">Чтобы устранить проблему, задайте для **ExecutionPolicy** значение **RemoteSigned**, выполнив следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):</span><span class="sxs-lookup"><span data-stu-id="5d84d-107">To resolve, set the **ExecutionPolicy** to **RemoteSigned** by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```
