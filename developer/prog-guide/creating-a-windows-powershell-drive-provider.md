---
title: Создание поставщика Windows PowerShell диска | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.assetid: 2b446841-6616-4720-9ff8-50801d7576ed
caps.latest.revision: 6
ms.openlocfilehash: 174d3a6860790295e1b73f32d9c1bad46b653917
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055656"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="47c44-102">Создание поставщика дисков Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47c44-102">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="47c44-103">В этом разделе описывается создание поставщика диска Windows PowerShell, который предоставляет способ доступа к хранилищу данных через диск Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47c44-103">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="47c44-104">Этот тип поставщиков также называется поставщики диск Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47c44-104">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="47c44-105">На дисках Windows PowerShell, используемый поставщиком предоставляют средства для подключения к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="47c44-105">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="47c44-106">Поставщик диск Windows PowerShell, описанные здесь предоставляет доступ к базе данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="47c44-106">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span> <span data-ttu-id="47c44-107">Для этого поставщика на диск Windows PowerShell представляет базу данных (это можно добавить любое количество дисков в поставщик диска), контейнеров верхнего уровня диска представления таблиц в базе данных и строки указывают элементы из контейнеров таблицы.</span><span class="sxs-lookup"><span data-stu-id="47c44-107">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

<span data-ttu-id="47c44-108">Ниже приведен список разделов этой статьи.</span><span class="sxs-lookup"><span data-stu-id="47c44-108">Here is a list of the sections in this topic.</span></span> <span data-ttu-id="47c44-109">Если вы не знакомы с разработка поставщика диска Windows PowerShell, прочтите эти разделы в порядке их появления.</span><span class="sxs-lookup"><span data-stu-id="47c44-109">If you are unfamiliar with writing a Windows PowerShell drive provider, read these sections in the order that they appear.</span></span> <span data-ttu-id="47c44-110">Тем не менее если вы знакомы с записью поставщик диска, перейдите непосредственно к сведениям, вам потребуется.</span><span class="sxs-lookup"><span data-stu-id="47c44-110">However, if you are familiar with writing a drive provider, please go directly to the information that you need.</span></span>

- [<span data-ttu-id="47c44-111">Определение класса поставщика PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="47c44-111">Defining the Windows PowerShell Provider Class</span></span>](#Defining-the-Windows-PowerShell-Provider-Class)

- [<span data-ttu-id="47c44-112">Определение базовой функциональности</span><span class="sxs-lookup"><span data-stu-id="47c44-112">Defining Base Functionality</span></span>](#Defining-Base-Functionality)

- [<span data-ttu-id="47c44-113">Создание сведений о состоянии дисков</span><span class="sxs-lookup"><span data-stu-id="47c44-113">Creating Drive State Information</span></span>](#Creating-Drive-State-Information)

- [<span data-ttu-id="47c44-114">Создание диска</span><span class="sxs-lookup"><span data-stu-id="47c44-114">Creating a Drive</span></span>](#Creating-a-Drive)

- [<span data-ttu-id="47c44-115">Присоединение к NewDrive динамических параметров</span><span class="sxs-lookup"><span data-stu-id="47c44-115">Attaching Dynamic Parameters to NewDrive</span></span>](#Attaching-Dynamic-Parameters-to-NewDrive)

- [<span data-ttu-id="47c44-116">Удаление диска</span><span class="sxs-lookup"><span data-stu-id="47c44-116">Removing a Drive</span></span>](#Removing-a-Drive)

- [<span data-ttu-id="47c44-117">Инициализация по умолчанию диски</span><span class="sxs-lookup"><span data-stu-id="47c44-117">Initializing Default Drives</span></span>](#Initializing-Default-Drives)

- [<span data-ttu-id="47c44-118">Пример кода</span><span class="sxs-lookup"><span data-stu-id="47c44-118">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="47c44-119">Проверка поставщика диск PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="47c44-119">Testing the Windows PowerShell Drive Provider</span></span>](#Testing-the-Windows-PowerShell-Drive-Provider)

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="47c44-120">Определение класса поставщика PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="47c44-120">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="47c44-121">Ваш поставщик диска необходимо определить класс .NET, который является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) базового класса.</span><span class="sxs-lookup"><span data-stu-id="47c44-121">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="47c44-122">Ниже приведен в определении класса для этого поставщика диска.</span><span class="sxs-lookup"><span data-stu-id="47c44-122">Here is the class definition for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

<span data-ttu-id="47c44-123">Обратите внимание, что в этом примере [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) атрибут задает понятное имя для поставщика и специальной совместимости с Windows PowerShell, поставщик предоставляет доступ к среде выполнения Windows PowerShell во время обработки команды.</span><span class="sxs-lookup"><span data-stu-id="47c44-123">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="47c44-124">Возможные значения для возможностей поставщика определяются [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) перечисления.</span><span class="sxs-lookup"><span data-stu-id="47c44-124">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="47c44-125">Этот диск поставщик не поддерживает эти возможности.</span><span class="sxs-lookup"><span data-stu-id="47c44-125">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="47c44-126">Определение базовой функциональности</span><span class="sxs-lookup"><span data-stu-id="47c44-126">Defining Base Functionality</span></span>

<span data-ttu-id="47c44-127">Как описано в разделе [разработки ваш поставщик Windows PowerShell](./designing-your-windows-powershell-provider.md), [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс является производным от [ System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) базового класса, который определяет методы, необходимые для инициализации и Отмена инициализации поставщика.</span><span class="sxs-lookup"><span data-stu-id="47c44-127">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="47c44-128">Чтобы реализовать функциональные возможности для добавления сведений инициализации сеанса, а также для освобождения ресурсов, которые используются поставщиком, см. в разделе [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="47c44-128">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="47c44-129">Тем не менее большинство поставщиков (включая поставщика, описанные здесь) можно использовать реализацию по умолчанию эта функция, предоставляемая Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47c44-129">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="47c44-130">Создание сведений о состоянии дисков</span><span class="sxs-lookup"><span data-stu-id="47c44-130">Creating Drive State Information</span></span>

<span data-ttu-id="47c44-131">Всеми поставщиками Windows PowerShell, считаются без отслеживания состояния, что означает, что ваш поставщик диска необходимо создать все сведения о состоянии, который необходим средой выполнения Windows PowerShell, при вызове поставщика.</span><span class="sxs-lookup"><span data-stu-id="47c44-131">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="47c44-132">Для этого поставщика диска сведения о состоянии включает соединение с базой данных, который хранится как часть сведений о диске.</span><span class="sxs-lookup"><span data-stu-id="47c44-132">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="47c44-133">Ниже приведен код, который показывает, каким образом эти сведения хранятся в [: System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) , описывающий диска:</span><span class="sxs-lookup"><span data-stu-id="47c44-133">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a><span data-ttu-id="47c44-134">Создание диска</span><span class="sxs-lookup"><span data-stu-id="47c44-134">Creating a Drive</span></span>

<span data-ttu-id="47c44-135">Чтобы среда выполнения Windows PowerShell для создания диска, диск поставщик должен реализовывать [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метод.</span><span class="sxs-lookup"><span data-stu-id="47c44-135">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="47c44-136">Следующий код показывает реализацию [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метода для данного поставщика диска:</span><span class="sxs-lookup"><span data-stu-id="47c44-136">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

<span data-ttu-id="47c44-137">Переопределение этого метода следует сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="47c44-137">Your override of this method should do the following:</span></span>

- <span data-ttu-id="47c44-138">Убедитесь, что [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) элемент существует и в хранилище данных можно установить соединение.</span><span class="sxs-lookup"><span data-stu-id="47c44-138">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>

- <span data-ttu-id="47c44-139">Создание диска и заполнить элемент подключения поддержки `New-PSDrive` командлета.</span><span class="sxs-lookup"><span data-stu-id="47c44-139">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>

- <span data-ttu-id="47c44-140">Проверка [: System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) объекта для предложенных диска.</span><span class="sxs-lookup"><span data-stu-id="47c44-140">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>

- <span data-ttu-id="47c44-141">Изменить [: System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) объект, описывающий на диск с обязательным производительности или надежности сведения или установить дополнительные данные для вызывающих объектов, с помощью диска.</span><span class="sxs-lookup"><span data-stu-id="47c44-141">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>

- <span data-ttu-id="47c44-142">Обработка ошибок с помощью [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) метод, а затем возвратить `null`.</span><span class="sxs-lookup"><span data-stu-id="47c44-142">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="47c44-143">Этот метод возвращает либо сведениями о диске, переданный к методу или его версию поставщика.</span><span class="sxs-lookup"><span data-stu-id="47c44-143">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="47c44-144">Присоединение к NewDrive динамических параметров</span><span class="sxs-lookup"><span data-stu-id="47c44-144">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="47c44-145">`New-PSDrive` Командлета поддерживается поставщиком диска могут потребовать дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="47c44-145">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="47c44-146">Чтобы присоединить эти динамические параметры командлета, поставщик реализует [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) метод.</span><span class="sxs-lookup"><span data-stu-id="47c44-146">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="47c44-147">Этот метод возвращает объект, имеющий свойства и поля с разбор атрибутов, аналогично классу командлета или [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) объекта.</span><span class="sxs-lookup"><span data-stu-id="47c44-147">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="47c44-148">Этот поставщик диска не Переопределите этот метод.</span><span class="sxs-lookup"><span data-stu-id="47c44-148">This drive provider does not override this method.</span></span> <span data-ttu-id="47c44-149">Тем не менее приведенный ниже показана реализация по умолчанию этого метода:</span><span class="sxs-lookup"><span data-stu-id="47c44-149">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="47c44-150">Удаление диска</span><span class="sxs-lookup"><span data-stu-id="47c44-150">Removing a Drive</span></span>

<span data-ttu-id="47c44-151">Чтобы закрыть подключение к базе данных, необходимо реализовать поставщика [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод.</span><span class="sxs-lookup"><span data-stu-id="47c44-151">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="47c44-152">Этот метод закрывает соединение на диск после очистки любые сведения о поставщике.</span><span class="sxs-lookup"><span data-stu-id="47c44-152">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="47c44-153">Следующий код показывает реализацию [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метода для данного поставщика диска:</span><span class="sxs-lookup"><span data-stu-id="47c44-153">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

<span data-ttu-id="47c44-154">Если диск может быть удален, метод должен вернуть информацию, передаваемую методу через `drive` параметра.</span><span class="sxs-lookup"><span data-stu-id="47c44-154">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="47c44-155">Если не удается удалить диск, метод должен записи исключение и затем возврата `null`.</span><span class="sxs-lookup"><span data-stu-id="47c44-155">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="47c44-156">Если ваш поставщик не переопределять этот метод, реализация по умолчанию этот метод просто возвращает диск информацию, передаваемую в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="47c44-156">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="47c44-157">Инициализация по умолчанию диски</span><span class="sxs-lookup"><span data-stu-id="47c44-157">Initializing Default Drives</span></span>

<span data-ttu-id="47c44-158">Пользовательский поставщик реализует диск [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) метод для подключения дисков.</span><span class="sxs-lookup"><span data-stu-id="47c44-158">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="47c44-159">Например поставщик Active Directory может подключить диск для контекста именования, если компьютер присоединен к домену по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47c44-159">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="47c44-160">Этот метод возвращает коллекцию сведений о диске об инициализации дисков, или пустая коллекция.</span><span class="sxs-lookup"><span data-stu-id="47c44-160">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="47c44-161">Вызов этого метода выполняется после вызова среды выполнения Windows PowerShell [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) метод для инициализации поставщика.</span><span class="sxs-lookup"><span data-stu-id="47c44-161">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="47c44-162">Этот поставщик диска не переопределяет [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) метод.</span><span class="sxs-lookup"><span data-stu-id="47c44-162">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="47c44-163">Тем не менее в следующем коде показано реализации по умолчанию, которая возвращает коллекцию пустой диск:</span><span class="sxs-lookup"><span data-stu-id="47c44-163">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="47c44-164">О чем следует помнить о реализации InitializeDefaultDrives</span><span class="sxs-lookup"><span data-stu-id="47c44-164">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="47c44-165">Все поставщики диск следует подключать корневой диск, чтобы помочь пользователю с возможность обнаружения.</span><span class="sxs-lookup"><span data-stu-id="47c44-165">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="47c44-166">В корне диска могут быть перечислены расположения, которые служат в качестве корневых элементов для других подключенных дисков.</span><span class="sxs-lookup"><span data-stu-id="47c44-166">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="47c44-167">Например, создать поставщик Active Directory на диск, который перечисляет контексты именования в `namingContext` атрибуты в корне среды Distributed System (DSE).</span><span class="sxs-lookup"><span data-stu-id="47c44-167">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="47c44-168">Это позволяет пользователям обнаруживать точки подключения для других дисков.</span><span class="sxs-lookup"><span data-stu-id="47c44-168">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="47c44-169">Пример кода</span><span class="sxs-lookup"><span data-stu-id="47c44-169">Code Sample</span></span>

<span data-ttu-id="47c44-170">Полный пример кода см. в разделе [пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).</span><span class="sxs-lookup"><span data-stu-id="47c44-170">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="47c44-171">Проверка поставщика диск PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="47c44-171">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="47c44-172">После регистрации поставщиком Windows PowerShell с помощью Windows PowerShell, можно проверить его, выполнив Поддерживаемые командлеты в командной строке, включая все командлеты, доступные через наследование.</span><span class="sxs-lookup"><span data-stu-id="47c44-172">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="47c44-173">Давайте протестируем диска к образцу поставщика.</span><span class="sxs-lookup"><span data-stu-id="47c44-173">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="47c44-174">Запустите `Get-PSProvider` командлет, чтобы получить список поставщиков, чтобы убедиться, что поставщика AccessDB присутствует:</span><span class="sxs-lookup"><span data-stu-id="47c44-174">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="47c44-175">**PS &GT; `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="47c44-175">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="47c44-176">Появляется следующий результат:</span><span class="sxs-lookup"><span data-stu-id="47c44-176">The following output appears:</span></span>

   ```output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. <span data-ttu-id="47c44-177">Убедитесь, что имя сервера базы данных (DSN) существует для базы данных, обратившись к **источников данных** часть **Администрирование** для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="47c44-177">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="47c44-178">В **DSN пользователя** таблицы, дважды щелкните **базы данных MS Access** и добавьте путь к диску C:\ps\northwind.mdb.</span><span class="sxs-lookup"><span data-stu-id="47c44-178">In the **User DSN** table, double-click **MS Access Database** and add the drive path C:\ps\northwind.mdb.</span></span>

3. <span data-ttu-id="47c44-179">Создание нового диска с помощью диска к образцу поставщика:</span><span class="sxs-lookup"><span data-stu-id="47c44-179">Create a new drive using the sample drive provider:</span></span>

   <span data-ttu-id="47c44-180">**PS > новый psdrive-name mydb-корневой c:\ps\northwind.mdb - psprovider AccessDb**</span><span class="sxs-lookup"><span data-stu-id="47c44-180">**PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**</span></span>

   <span data-ttu-id="47c44-181">Появляется следующий результат:</span><span class="sxs-lookup"><span data-stu-id="47c44-181">The following output appears:</span></span>

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="47c44-182">Проверка подключения.</span><span class="sxs-lookup"><span data-stu-id="47c44-182">Validate the connection.</span></span> <span data-ttu-id="47c44-183">Так как соединение определяется как член диска, можно проверить с помощью командлета Get-PDDrive.</span><span class="sxs-lookup"><span data-stu-id="47c44-183">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47c44-184">Пользователь еще не может взаимодействовать с поставщиком как диск, как поставщик должен функциональные возможности контейнеров, реализуемый.</span><span class="sxs-lookup"><span data-stu-id="47c44-184">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="47c44-185">Дополнительные сведения см. в разделе [Создание поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="47c44-185">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="47c44-186">**PS > .connection (get-psdrive mydb)**</span><span class="sxs-lookup"><span data-stu-id="47c44-186">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="47c44-187">Появляется следующий результат:</span><span class="sxs-lookup"><span data-stu-id="47c44-187">The following output appears:</span></span>

   ```output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. <span data-ttu-id="47c44-188">Удалите диск и выйдите из оболочки:</span><span class="sxs-lookup"><span data-stu-id="47c44-188">Remove the drive and exit the shell:</span></span>

   <span data-ttu-id="47c44-189">**PS > remove-psdrive mydb**</span><span class="sxs-lookup"><span data-stu-id="47c44-189">**PS> remove-psdrive mydb**</span></span>

   <span data-ttu-id="47c44-190">**PS > выйти из**</span><span class="sxs-lookup"><span data-stu-id="47c44-190">**PS> exit**</span></span>

## <a name="see-also"></a><span data-ttu-id="47c44-191">См. также</span><span class="sxs-lookup"><span data-stu-id="47c44-191">See Also</span></span>

[<span data-ttu-id="47c44-192">Создание поставщиков Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47c44-192">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="47c44-193">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47c44-193">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="47c44-194">Создание поставщика базовый Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47c44-194">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)