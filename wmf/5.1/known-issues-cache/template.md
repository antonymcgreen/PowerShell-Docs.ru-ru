---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.topic: conceptual
title: пример шаблона с описанием известной проблемы или ограничения
ms.openlocfilehash: 8c1004e16f78913174af2e519e451f6fd9f30ff7
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794503"
---
 ><span data-ttu-id="718b6-103">Примечание. Предоставьте предложенное описательное название и краткое описание.</span><span class="sxs-lookup"><span data-stu-id="718b6-103">Note: provide a proposed descriptive title and a brief description</span></span>

## <a name="example-erroneous-executionpolicy-errors"></a><span data-ttu-id="718b6-104">Пример: ложные ошибки ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="718b6-104">Example: Erroneous ExecutionPolicy errors</span></span>
<span data-ttu-id="718b6-105">В Windows 7 использование модулей PowerShell и ресурсов DSC может привести к возникновению ошибок, связанных с ExecutionPolicy.</span><span class="sxs-lookup"><span data-stu-id="718b6-105">On Windows 7, the use of PowerShell modules and DSC resources may result in errors reported about ExecutionPolicy.</span></span>

### <a name="resolution"></a><span data-ttu-id="718b6-106">Разрешение</span><span class="sxs-lookup"><span data-stu-id="718b6-106">Resolution</span></span>

<span data-ttu-id="718b6-107">Чтобы устранить проблему, задайте для **ExecutionPolicy** значение **RemoteSigned**, выполнив следующую команду в сеансе PowerShell с повышенными правами ("Запуск от имени администратора"):</span><span class="sxs-lookup"><span data-stu-id="718b6-107">To resolve, set the **ExecutionPolicy** to **RemoteSigned** by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```
