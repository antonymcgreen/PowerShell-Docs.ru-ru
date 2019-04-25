---
title: Создание рабочего процесса с помощью Windows PowerShell действий | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080440"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a><span data-ttu-id="e5bfd-102">Создание рабочего процесса с помощью действий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfd-102">Creating a Workflow with Windows PowerShell Activities</span></span>

<span data-ttu-id="e5bfd-103">Можно создать рабочий процесс Windows PowerShell, выбрав действий из панели элементов Visual Studio и перетащив их в окно конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-103">You can create a Windows PowerShell workflow by selecting activities from the Visual Studio Toolbox and dragging them to the Workflow Designer window.</span></span> <span data-ttu-id="e5bfd-104">Сведения о добавлении действия Windows PowerShell для панели элементов Visual Studio, см. в разделе [добавления действий Windows PowerShell для панели элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="e5bfd-104">For information about adding Windows PowerShell activities to the Visual Studio Toolbox, see [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).</span></span>

<span data-ttu-id="e5bfd-105">Следующие процедуры описывают создание рабочего процесса, который проверяет состояние домена для группы компьютеров, определяемое пользователем, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-105">The following procedures describe how to create a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="e5bfd-106">Настройка проекта</span><span class="sxs-lookup"><span data-stu-id="e5bfd-106">Setting up the Project</span></span>

1. <span data-ttu-id="e5bfd-107">Выполните процедуру, описанную в [добавления действий Windows PowerShell для панели элементов Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) для создания проекта рабочего процесса и добавления действий из [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities) и [ Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) сборок на панель элементов.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-107">Follow the procedure in [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) to create a workflow project and add the activities from the [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities) and [Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) assemblies to the toolbox.</span></span>

2. <span data-ttu-id="e5bfd-108">Добавьте System.Management.Automation, Microsoft.PowerShell.Activities, System.Management, Microsoft.PowerShell.Management.Activities и Microsoft.PowerShell.Commands.Management относительно проекта, как базовые сборки.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-108">Add System.Management.Automation, Microsoft.PowerShell.Activities, System.Management, Microsoft.PowerShell.Management.Activities, and Microsoft.PowerShell.Commands.Management as to the project as reference assemblies.</span></span>

### <a name="adding-activities-to-the-workflow"></a><span data-ttu-id="e5bfd-109">Добавление действий в рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="e5bfd-109">Adding Activities to the Workflow</span></span>

1. <span data-ttu-id="e5bfd-110">Добавить **последовательности** действия в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-110">Add a **Sequence** activity to the workflow.</span></span>

2. <span data-ttu-id="e5bfd-111">Создайте аргумент с именем `ComputerName` с типом аргумента `String[]`.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-111">Create an argument named `ComputerName` with an argument type of `String[]`.</span></span> <span data-ttu-id="e5bfd-112">Этот аргумент представляет имена компьютеров для проверки и join.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-112">This argument represents the names of the computers to check and join.</span></span>

3. <span data-ttu-id="e5bfd-113">Создайте аргумент с именем `DomainCred` типа [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span><span class="sxs-lookup"><span data-stu-id="e5bfd-113">Create an argument named `DomainCred` of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="e5bfd-114">Этот аргумент представляет учетные данные учетной записи домена, имеющее полномочия на присоединение компьютера к домену.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-114">This argument represents the domain credentials of a domain account that is authorized to join a computer to the domain.</span></span>

4. <span data-ttu-id="e5bfd-115">Создайте аргумент с именем `MachineCred` типа [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span><span class="sxs-lookup"><span data-stu-id="e5bfd-115">Create an argument named `MachineCred` of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="e5bfd-116">Этот аргумент представляет учетные данные администратора на компьютерах, для проверки и join.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-116">This argument represents the credentials of an administrator on the computers to check and join.</span></span>

5. <span data-ttu-id="e5bfd-117">Добавить **ParallelForEach** действия внутри **последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-117">Add a **ParallelForEach** activity inside the **Sequence** activity.</span></span> <span data-ttu-id="e5bfd-118">Введите `comp` и `ComputerName` в текстовые поля, чтобы цикл выполняет итерацию по элементам `ComputerName` массива.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-118">Enter `comp` and `ComputerName` in the text boxes so that the loop iterates through the elements of the `ComputerName` array.</span></span>

6. <span data-ttu-id="e5bfd-119">Добавить **последовательности** действия в тело **ParallelForEach** действия.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-119">Add a **Sequence** activity to the body of the **ParallelForEach** activity.</span></span> <span data-ttu-id="e5bfd-120">Задайте **DisplayName** свойство последовательности `JoinDomain`.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-120">Set the **DisplayName** property of the sequence to `JoinDomain`.</span></span>

7. <span data-ttu-id="e5bfd-121">Добавить **GetWmiObject** действие **JoinDomain** последовательности.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-121">Add a **GetWmiObject** activity to the **JoinDomain** sequence.</span></span>

8. <span data-ttu-id="e5bfd-122">Изменение свойств **GetWmiObject** действия, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-122">Edit the properties of the **GetWmiObject** activity as follows.</span></span>

   |<span data-ttu-id="e5bfd-123">Свойство</span><span class="sxs-lookup"><span data-stu-id="e5bfd-123">Property</span></span>|<span data-ttu-id="e5bfd-124">Значение</span><span class="sxs-lookup"><span data-stu-id="e5bfd-124">Value</span></span>|
   |--------------|-----------|
   |<span data-ttu-id="e5bfd-125">**Класс**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-125">**Class**</span></span>|<span data-ttu-id="e5bfd-126">"Win32_ComputerSystem"</span><span class="sxs-lookup"><span data-stu-id="e5bfd-126">"Win32_ComputerSystem"</span></span>|
   |<span data-ttu-id="e5bfd-127">**PSComputerName**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-127">**PSComputerName**</span></span>|<span data-ttu-id="e5bfd-128">{comp}</span><span class="sxs-lookup"><span data-stu-id="e5bfd-128">{comp}</span></span>|
   |<span data-ttu-id="e5bfd-129">**PSCredential**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-129">**PSCredential**</span></span>|<span data-ttu-id="e5bfd-130">MachineCred</span><span class="sxs-lookup"><span data-stu-id="e5bfd-130">MachineCred</span></span>|

9. <span data-ttu-id="e5bfd-131">Добавить **AddComputer** действие **JoinDomain** последовательности после **GetWmiObject** действия.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-131">Add an **AddComputer** activity to the **JoinDomain** sequence after the **GetWmiObject** activity.</span></span>

10. <span data-ttu-id="e5bfd-132">Изменение свойств **AddComputer** действия, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-132">Edit the properties of the **AddComputer** activity as follows.</span></span>

    |<span data-ttu-id="e5bfd-133">Свойство</span><span class="sxs-lookup"><span data-stu-id="e5bfd-133">Property</span></span>|<span data-ttu-id="e5bfd-134">Значение</span><span class="sxs-lookup"><span data-stu-id="e5bfd-134">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="e5bfd-135">**ComputerName**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-135">**ComputerName**</span></span>|<span data-ttu-id="e5bfd-136">{comp}</span><span class="sxs-lookup"><span data-stu-id="e5bfd-136">{comp}</span></span>|
    |<span data-ttu-id="e5bfd-137">**DomainCredential**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-137">**DomainCredential**</span></span>|<span data-ttu-id="e5bfd-138">DomainCred</span><span class="sxs-lookup"><span data-stu-id="e5bfd-138">DomainCred</span></span>|

11. <span data-ttu-id="e5bfd-139">Добавить **RestartComputer** действие **JoinDomain** последовательности после **AddComputer** действия.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-139">Add a **RestartComputer** activity to the **JoinDomain** sequence after the **AddComputer** activity.</span></span>

12. <span data-ttu-id="e5bfd-140">Изменение свойств **RestartComputer** действия, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-140">Edit the properties of the **RestartComputer** activity as follows.</span></span>

    |<span data-ttu-id="e5bfd-141">Свойство</span><span class="sxs-lookup"><span data-stu-id="e5bfd-141">Property</span></span>|<span data-ttu-id="e5bfd-142">Значение</span><span class="sxs-lookup"><span data-stu-id="e5bfd-142">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="e5bfd-143">**ComputerName**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-143">**ComputerName**</span></span>|<span data-ttu-id="e5bfd-144">{comp}</span><span class="sxs-lookup"><span data-stu-id="e5bfd-144">{comp}</span></span>|
    |<span data-ttu-id="e5bfd-145">**Учетные данные**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-145">**Credential**</span></span>|<span data-ttu-id="e5bfd-146">MachineCred</span><span class="sxs-lookup"><span data-stu-id="e5bfd-146">MachineCred</span></span>|
    |<span data-ttu-id="e5bfd-147">**для**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-147">**For**</span></span>|<span data-ttu-id="e5bfd-148">Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfd-148">Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell</span></span>|
    |<span data-ttu-id="e5bfd-149">**Force**</span><span class="sxs-lookup"><span data-stu-id="e5bfd-149">**Force**</span></span>|<span data-ttu-id="e5bfd-150">True</span><span class="sxs-lookup"><span data-stu-id="e5bfd-150">True</span></span>|
    |<span data-ttu-id="e5bfd-151">Wait</span><span class="sxs-lookup"><span data-stu-id="e5bfd-151">Wait</span></span>|<span data-ttu-id="e5bfd-152">True</span><span class="sxs-lookup"><span data-stu-id="e5bfd-152">True</span></span>|
    |<span data-ttu-id="e5bfd-153">PSComputerName</span><span class="sxs-lookup"><span data-stu-id="e5bfd-153">PSComputerName</span></span>|<span data-ttu-id="e5bfd-154">{""}</span><span class="sxs-lookup"><span data-stu-id="e5bfd-154">{""}</span></span>|

13. <span data-ttu-id="e5bfd-155">Добавить **GetWmiObject** действие **JoinDomain** последовательности после **RestartComputer** действия.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-155">Add a **GetWmiObject** activity to the **JoinDomain** sequence after the **RestartComputer** activity.</span></span> <span data-ttu-id="e5bfd-156">Изменить свойства, чтобы быть так же, как и при предыдущем **GetWmiObject** действия.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-156">Edit its properties to be the same as the previous **GetWmiObject** activity.</span></span>

    <span data-ttu-id="e5bfd-157">После завершения процедуры окна конструктора рабочего процесса должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e5bfd-157">When you have finished the procedures, the workflow design window should look like this.</span></span>

    <span data-ttu-id="e5bfd-158">![JoinDomain XAML в конструкторе рабочих процессов](../media/joindomainworkflow.png)
    ![JoinDomain XAML в конструкторе рабочих процессов](../media/joindomainworkflow.png "JoinDomainWorkflow")</span><span class="sxs-lookup"><span data-stu-id="e5bfd-158">![JoinDomain XAML in Workflow designer](../media/joindomainworkflow.png)
![JoinDomain XAML in Workflow designer](../media/joindomainworkflow.png "JoinDomainWorkflow")</span></span>