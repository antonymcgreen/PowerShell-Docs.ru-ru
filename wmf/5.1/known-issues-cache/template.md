---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.topic: conceptual
title: пример шаблона с описанием известной проблемы или ограничения
ms.openlocfilehash: 8c1004e16f78913174af2e519e451f6fd9f30ff7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055553"
---
 ><span data-ttu-id="7c756-103">Примечание. Предоставьте предложенное описательное название и краткое описание.</span><span class="sxs-lookup"><span data-stu-id="7c756-103">Note: provide a proposed descriptive title and a brief description</span></span>

## <a name="example-erroneous-executionpolicy-errors"></a><span data-ttu-id="7c756-104">Пример: ложные ошибки ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7c756-104">Example: Erroneous ExecutionPolicy errors</span></span>
<span data-ttu-id="7c756-105">В Windows 7 использование модулей PowerShell и ресурсов DSC может привести к возникновению ошибок, связанных с ExecutionPolicy.</span><span class="sxs-lookup"><span data-stu-id="7c756-105">On Windows 7, the use of PowerShell modules and DSC resources may result in errors reported about ExecutionPolicy.</span></span>

### <a name="resolution"></a><span data-ttu-id="7c756-106">Разрешение</span><span class="sxs-lookup"><span data-stu-id="7c756-106">Resolution</span></span>

<span data-ttu-id="7c756-107">Чтобы устранить проблему, задайте для **ExecutionPolicy** значение **RemoteSigned**, выполнив следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):</span><span class="sxs-lookup"><span data-stu-id="7c756-107">To resolve, set the **ExecutionPolicy** to **RemoteSigned** by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```
