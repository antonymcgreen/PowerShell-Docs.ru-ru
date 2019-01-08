---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Создание сценариев PowerShell
ms.openlocfilehash: 07925ce8dcafd33970a703c9b241bf6f76f88d10
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402896"
---
# <a name="powershell"></a><span data-ttu-id="c8d9f-103">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8d9f-103">PowerShell</span></span>

<span data-ttu-id="c8d9f-104">PowerShell — это оболочка командной строки с поддержкой задач и язык скриптов на основе .NET.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-104">PowerShell is a task-based command-line shell and scripting language built on .NET.</span></span>
<span data-ttu-id="c8d9f-105">PowerShell позволяет системным администраторам и опытным пользователям быстро автоматизировать задачи для управления процессами и операционными системами (Linux, macOS и Windows).</span><span class="sxs-lookup"><span data-stu-id="c8d9f-105">PowerShell helps system administrators and power-users rapidly automate tasks that manage operating systems (Linux, macOS, and Windows) and processes.</span></span>

<span data-ttu-id="c8d9f-106">Команды PowerShell позволяют управлять компьютерами из командной строки.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-106">PowerShell commands let you manage computers from the command line.</span></span> <span data-ttu-id="c8d9f-107">При использовании поставщиков PowerShell доступ к хранилищам данных, таким как реестр и хранилище сертификатов, становится таким же простым, как и доступ к файловой системе.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-107">PowerShell providers let you access data stores, such as the registry and certificate store, as easily as you access the file system.</span></span> <span data-ttu-id="c8d9f-108">PowerShell включает многофункциональное средство синтаксического анализа выражений и полностью разработанный язык скриптов.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-108">PowerShell includes a rich expression parser and a fully developed scripting language.</span></span>

## <a name="powershell-is-open-source"></a><span data-ttu-id="c8d9f-109">Исходный код PowerShell является открытым</span><span class="sxs-lookup"><span data-stu-id="c8d9f-109">PowerShell is open-source</span></span>

<span data-ttu-id="c8d9f-110">Базовый исходный код PowerShell теперь доступен в GitHub, и участники сообщества могут вносить в него свои дополнения.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-110">PowerShell base source code is now available in GitHub and open to community contributions.</span></span>
<span data-ttu-id="c8d9f-111">См. [Код PowerShell в GitHub](https://github.com/powershell/powershell).</span><span class="sxs-lookup"><span data-stu-id="c8d9f-111">See [PowerShell source on GitHub](https://github.com/powershell/powershell).</span></span>

<span data-ttu-id="c8d9f-112">Вы можете начать с нужных вам элементов в руководстве по [получению PowerShell](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8d9f-112">You can start with the bits you need at [Get PowerShell](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>
<span data-ttu-id="c8d9f-113">Или же с краткого обзора в разделе [Приступая к работе](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8d9f-113">Or, perhaps, with a quick tour at [Getting Started](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell).</span></span>

## <a name="powershell-design-goals"></a><span data-ttu-id="c8d9f-114">Задачи при проектировании сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8d9f-114">PowerShell design goals</span></span>

<span data-ttu-id="c8d9f-115">PowerShell помогает улучшить среду командной строки и сценариев за счет устранения застарелых проблем и добавления новых функций.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-115">PowerShell is designed to improve the command-line and scripting environment by eliminating long-standing problems and adding new features.</span></span>

### <a name="discoverability"></a><span data-ttu-id="c8d9f-116">Возможность обнаружения</span><span class="sxs-lookup"><span data-stu-id="c8d9f-116">Discoverability</span></span>

<span data-ttu-id="c8d9f-117">В PowerShell можно легко получить представление о предоставляемых возможностях.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-117">PowerShell makes it easy to discover its features.</span></span> <span data-ttu-id="c8d9f-118">Например, чтобы получить список командлетов для просмотра и изменения служб Windows, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="c8d9f-118">For example, to find a list of cmdlets that view and change Windows services, type:</span></span>

```powershell
Get-Command *-Service
```

<span data-ttu-id="c8d9f-119">Узнав, какой командлет выполняет задачу, можно получить дополнительные сведения о нем с помощью командлета `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-119">After discovering which cmdlet accomplishes a task, you can learn more about the cmdlet by using the `Get-Help` cmdlet.</span></span> <span data-ttu-id="c8d9f-120">Например, для отображения справки по командлету `Get-Service` введите:</span><span class="sxs-lookup"><span data-stu-id="c8d9f-120">For example, to display help about the `Get-Service` cmdlet, type:</span></span>

```powershell
Get-Help Get-Service
```

<span data-ttu-id="c8d9f-121">Большинство командлетов возвращают объекты, которые могут быть обработаны и преобразованы как текст для просмотра.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-121">Most cmdlets return objects that can be manipulated and then rendered as text for display.</span></span> <span data-ttu-id="c8d9f-122">Чтобы проанализировать выходные данные этого командлета, передайте их в командлет `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-122">To fully understand the output of a cmdlet, pipe the output to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="c8d9f-123">Например, следующая команда отображает сведения об элементах выходных данных объекта с помощью командлета `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-123">For example, the following command displays information about the members of the object output by the `Get-Service` cmdlet.</span></span>

```powershell
Get-Service | Get-Member
```

### <a name="consistency"></a><span data-ttu-id="c8d9f-124">Consistency</span><span class="sxs-lookup"><span data-stu-id="c8d9f-124">Consistency</span></span>

<span data-ttu-id="c8d9f-125">Управление системами может быть непростой задачей.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-125">Managing systems can be a complex task.</span></span> <span data-ttu-id="c8d9f-126">Средства с согласованным интерфейсом помогают справляться с такими трудностями.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-126">Tools that have a consistent interface help to control the inherent complexity.</span></span> <span data-ttu-id="c8d9f-127">К сожалению, программы командной строки и COM-объекты с поддержкой скриптов не обеспечивают согласованность.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-127">Unfortunately, command-line tools and scriptable COM objects aren't known for their consistency.</span></span>

<span data-ttu-id="c8d9f-128">Согласованность возможностей PowerShell является одним его из важнейших преимуществ.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-128">The consistency of PowerShell is one of its primary assets.</span></span> <span data-ttu-id="c8d9f-129">Например, если вы научитесь использовать командлет `Sort-Object`, эти знания можно применить для сортировки выходных данных любого командлета.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-129">For example, if you learn how to use the `Sort-Object` cmdlet, you can use that knowledge to sort the output of any cmdlet.</span></span> <span data-ttu-id="c8d9f-130">Вам не нужно изучать разные процедуры сортировки для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-130">You don't have to learn the different sorting routines of each cmdlet.</span></span>

<span data-ttu-id="c8d9f-131">Кроме того, разработчикам командлетов не нужно создавать функции сортировки для своих командлетов.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-131">Additionally, cmdlet developers don't have to design sorting features for their cmdlets.</span></span> <span data-ttu-id="c8d9f-132">PowerShell предоставляет платформу с базовыми функциями, которая принудительно обеспечивает согласованность.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-132">PowerShell provides a framework with the basic features that forces consistency.</span></span> <span data-ttu-id="c8d9f-133">Эта платформа исключает некоторые функции для разработчика,</span><span class="sxs-lookup"><span data-stu-id="c8d9f-133">The framework eliminates some choices that are left to the developer.</span></span> <span data-ttu-id="c8d9f-134">но при этом она значительно упрощает разработку командлетов.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-134">But, in return, it makes the development of cmdlets much simpler.</span></span>

### <a name="interactive-and-scripting-environments"></a><span data-ttu-id="c8d9f-135">Интерактивные среды и среды скриптов</span><span class="sxs-lookup"><span data-stu-id="c8d9f-135">Interactive and scripting environments</span></span>

<span data-ttu-id="c8d9f-136">В командной строке Windows предоставляется интерактивная оболочка с доступом к программам командной строки и основным скриптам.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-136">The Windows Command Prompt provides an interactive shell with access to command-line tools and basic scripting.</span></span> <span data-ttu-id="c8d9f-137">Сервер скриптов Windows (WHS) предоставляет программы командной строки и COM-объекты автоматизации с поддержкой скриптов, но не интерактивную оболочку.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-137">Windows Script Host (WSH) has scriptable command-line tools and COM automation objects, but doesn't provide an interactive shell.</span></span>

<span data-ttu-id="c8d9f-138">PowerShell объединяет интерактивную оболочку и среду скриптов.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-138">PowerShell combines an interactive shell and a scripting environment.</span></span> <span data-ttu-id="c8d9f-139">PowerShell может обращаться к программам командной строки, COM-объектам и библиотекам класса .NET.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-139">PowerShell can access command-line tools, COM objects, and .NET class libraries.</span></span> <span data-ttu-id="c8d9f-140">Такое сочетание функций расширяет возможности интерактивного пользователя, разработчика скриптов и системного администратора.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-140">This combination of features extends the capabilities of the interactive user, the script writer, and the system administrator.</span></span>

### <a name="object-orientation"></a><span data-ttu-id="c8d9f-141">Ориентация на объекты</span><span class="sxs-lookup"><span data-stu-id="c8d9f-141">Object orientation</span></span>

<span data-ttu-id="c8d9f-142">Основой PowerShell является объект, а не текст.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-142">PowerShell is based on object not text.</span></span> <span data-ttu-id="c8d9f-143">Выходные данные команды — это объект.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-143">The output of a command is an object.</span></span> <span data-ttu-id="c8d9f-144">С помощью конвейера выходной объект можно отправить в другую команду в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-144">You can send the output object, through the pipeline, to another command as its input.</span></span>

<span data-ttu-id="c8d9f-145">Этот конвейер предлагает привычный интерфейс для людей, у которых есть опыт работы с другими оболочками.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-145">This pipeline provides a familiar interface for people experienced with other shells.</span></span> <span data-ttu-id="c8d9f-146">PowerShell расширяет эту концепцию, отправляя объекты, а не текст.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-146">PowerShell extends this concept by sending objects rather than text.</span></span>

### <a name="easy-transition-to-scripting"></a><span data-ttu-id="c8d9f-147">Легкий переход к скриптам</span><span class="sxs-lookup"><span data-stu-id="c8d9f-147">Easy transition to scripting</span></span>

<span data-ttu-id="c8d9f-148">Возможность обнаружения команд PowerShell упрощает переход от интерактивного ввода команд к созданию и выполнению скриптов.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-148">PowerShell's command discoverability makes it easy to transition from typing commands interactively to creating and running scripts.</span></span> <span data-ttu-id="c8d9f-149">Журнал и записи PowerShell упрощают копирование команд в файл для использования в качестве скрипта.</span><span class="sxs-lookup"><span data-stu-id="c8d9f-149">PowerShell transcripts and history make it easy to copy commands to a file for use as a script.</span></span>
