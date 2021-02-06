---
description: Объясняет, как использовать функцию запуска с PowerShell для выполнения сценария с диска файловой системы.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: 7070fa2bc8bb30e83f59e3d1193faa3a8495f109
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604302"
---
# <a name="about-run-with-powershell"></a><span data-ttu-id="ac9b6-103">Сведения о запуске с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac9b6-103">About Run With PowerShell</span></span>

## <a name="short-description"></a><span data-ttu-id="ac9b6-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ac9b6-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ac9b6-105">Описание использования функции "Запуск с помощью PowerShell" для выполнения сценария с диска файловой системы.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-105">Explains how to use the "Run with PowerShell" feature to run a script from a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="ac9b6-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ac9b6-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="ac9b6-107">Начиная с Windows PowerShell 3,0, можно использовать функцию "Запуск с помощью PowerShell" для запуска сценариев из проводника в Windows 8, Windows Server 2012 и Windows Explorer в более ранних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-107">Beginning in Windows PowerShell 3.0, you can use the "Run with PowerShell" feature to run scripts from File Explorer in Windows 8 and Windows Server 2012 and from Windows Explorer in earlier versions of Windows.</span></span>

<span data-ttu-id="ac9b6-108">Функция "запустить с помощью PowerShell" предназначена для выполнения скриптов, которые не имеют обязательных параметров и не возвращают выходные данные в командную строку.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-108">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="ac9b6-109">При использовании функции "Запуск с помощью PowerShell" окно консоли PowerShell появляется только вкратце, если вообще.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-109">When you use the "Run with PowerShell" feature, the PowerShell console window appears only briefly, if at all.</span></span> <span data-ttu-id="ac9b6-110">Вы не можете взаимодействовать с ним.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-110">You cannot interact with it.</span></span>

<span data-ttu-id="ac9b6-111">Чтобы использовать функцию "Запуск с помощью PowerShell", сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ac9b6-111">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="ac9b6-112">В проводнике (или в проводнике Windows) щелкните правой кнопкой мыши имя файла скрипта и выберите команду "запустить с помощью PowerShell".</span><span class="sxs-lookup"><span data-stu-id="ac9b6-112">In File Explorer (or Windows Explorer), right-click the script file name and then select "Run with PowerShell".</span></span>

<span data-ttu-id="ac9b6-113">Функция "запустить с помощью PowerShell" запускает сеанс PowerShell с политикой выполнения "обход", запускает сценарий и закрывает сеанс.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-113">The "Run with PowerShell" feature starts a PowerShell session that has an execution policy of Bypass, runs the script, and closes the session.</span></span>

<span data-ttu-id="ac9b6-114">Она выполняет команду, имеющую следующий формат:</span><span class="sxs-lookup"><span data-stu-id="ac9b6-114">It runs a command that has the following format:</span></span>

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

<span data-ttu-id="ac9b6-115">"Запустить с помощью PowerShell" задает политику выполнения обхода только для сеанса (текущего экземпляра процесса PowerShell), в котором выполняется скрипт.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-115">"Run with PowerShell" sets the Bypass execution policy only for the session (the current instance of the PowerShell process) in which the script runs.</span></span>
<span data-ttu-id="ac9b6-116">Эта функция не изменяет политику выполнения для компьютера или пользователя.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-116">This feature does not change the execution policy for the computer or the user.</span></span>

<span data-ttu-id="ac9b6-117">На функцию "Запуск с помощью PowerShell" влияет только политика выполнения AllSigned.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-117">The "Run with PowerShell" feature is affected only by the AllSigned execution policy.</span></span> <span data-ttu-id="ac9b6-118">Если политика выполнения AllSigned действует для компьютера или пользователя, "запустить с помощью PowerShell" запускает только подписанные сценарии.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-118">If the AllSigned execution policy is effective for the computer or the user, "Run with PowerShell" runs only signed scripts.</span></span> <span data-ttu-id="ac9b6-119">На запуск с PowerShell не влияют никакие другие политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-119">"Run with PowerShell" is not affected by any other execution policy.</span></span> <span data-ttu-id="ac9b6-120">Подробнее см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="ac9b6-120">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="ac9b6-121">Устранение неполадок Примечание. команда выполнить с PowerShell может запросить подтверждение изменения политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="ac9b6-121">Troubleshooting Note: Run with PowerShell command might prompt you to confirm the execution policy change.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac9b6-122">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ac9b6-122">SEE ALSO</span></span>

[<span data-ttu-id="ac9b6-123">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="ac9b6-123">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="ac9b6-124">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="ac9b6-124">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="ac9b6-125">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="ac9b6-125">about_Scripts</span></span>](about_Scripts.md)

