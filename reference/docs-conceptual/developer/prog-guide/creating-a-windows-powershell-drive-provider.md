---
title: Создание поставщика диска Windows PowerShell | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.openlocfilehash: 2a2178714ed548986fe1a1a4de8828e8e0a938cb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787195"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="009ad-102">Создание поставщика дисков Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="009ad-102">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="009ad-103">В этом разделе описывается создание поставщика диска Windows PowerShell, предоставляющего способ доступа к хранилищу данных с помощью диска Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="009ad-103">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="009ad-104">Этот тип поставщика также называются поставщиками дисков Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="009ad-104">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="009ad-105">Диски Windows PowerShell, используемые поставщиком, предоставляют средства для подключения к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="009ad-105">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="009ad-106">Поставщик диска Windows PowerShell, описанный здесь, предоставляет доступ к базе данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="009ad-106">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span>
<span data-ttu-id="009ad-107">Для этого поставщика диск Windows PowerShell представляет базу данных (можно добавить любое количество дисков к поставщику накопителя), контейнеры верхнего уровня диска представляют таблицы в базе данных, а элементы контейнеров представляют строки в таблицах.</span><span class="sxs-lookup"><span data-stu-id="009ad-107">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="009ad-108">Определение класса поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="009ad-108">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="009ad-109">Поставщик дисков должен определять класс .NET, производный от базового класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="009ad-109">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="009ad-110">Ниже приведено определение класса для этого поставщика диска:</span><span class="sxs-lookup"><span data-stu-id="009ad-110">Here is the class definition for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="29-30":::

<span data-ttu-id="009ad-111">Обратите внимание, что в этом примере атрибут [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) указывает понятное имя поставщика и возможности Windows PowerShell, которые поставщик предоставляет среде выполнения Windows PowerShell во время обработки команды.</span><span class="sxs-lookup"><span data-stu-id="009ad-111">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span>
<span data-ttu-id="009ad-112">Возможные значения для возможностей поставщика определяются перечислением [System. Management. Automation. Provider. провидеркапабилитиес](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) .</span><span class="sxs-lookup"><span data-stu-id="009ad-112">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="009ad-113">Этот поставщик дисков не поддерживает ни одну из этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="009ad-113">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="009ad-114">Определение базовых функций</span><span class="sxs-lookup"><span data-stu-id="009ad-114">Defining Base Functionality</span></span>

<span data-ttu-id="009ad-115">Как описано в статье [проектирование поставщика Windows PowerShell](./designing-your-windows-powershell-provider.md), класс [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) является производным от базового класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) , который определяет методы, необходимые для инициализации и деинициализации поставщика.</span><span class="sxs-lookup"><span data-stu-id="009ad-115">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="009ad-116">Сведения о реализации функций для добавления сведений об инициализации для конкретного сеанса и освобождения ресурсов, используемых поставщиком, см. в разделе [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="009ad-116">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="009ad-117">Однако большинство поставщиков (включая описанный здесь поставщик) могут использовать реализацию этой функции по умолчанию, предоставляемую Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="009ad-117">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="009ad-118">Создание сведений о состоянии диска</span><span class="sxs-lookup"><span data-stu-id="009ad-118">Creating Drive State Information</span></span>

<span data-ttu-id="009ad-119">Все поставщики Windows PowerShell считаются без отслеживания состояния. Это означает, что поставщику дисков необходимо создать все сведения о состоянии, необходимые среде выполнения Windows PowerShell при вызове поставщика.</span><span class="sxs-lookup"><span data-stu-id="009ad-119">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="009ad-120">Для этого поставщика дисков сведения о состоянии включают подключение к базе данных, которая хранится в составе сведений о диске.</span><span class="sxs-lookup"><span data-stu-id="009ad-120">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="009ad-121">Ниже приведен код, который показывает, как эта информация хранится в объекте [System.Management.Automation.PSDривеинфо](/dotnet/api/System.Management.Automation.PSDriveInfo) , описывающем диск:</span><span class="sxs-lookup"><span data-stu-id="009ad-121">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="130-151":::

## <a name="creating-a-drive"></a><span data-ttu-id="009ad-122">Создание диска</span><span class="sxs-lookup"><span data-stu-id="009ad-122">Creating a Drive</span></span>

<span data-ttu-id="009ad-123">Чтобы разрешить среде выполнения Windows PowerShell создать диск, поставщик накопителя должен реализовать метод [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) .</span><span class="sxs-lookup"><span data-stu-id="009ad-123">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="009ad-124">В следующем коде показана реализация метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для данного поставщика накопителя:</span><span class="sxs-lookup"><span data-stu-id="009ad-124">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="42-84":::

<span data-ttu-id="009ad-125">Переопределение этого метода должно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="009ad-125">Your override of this method should do the following:</span></span>

- <span data-ttu-id="009ad-126">Убедитесь, что [System.Management.Automation.PSDривеинфо. Член root \*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) существует и может быть установлено подключение к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="009ad-126">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>
- <span data-ttu-id="009ad-127">Создайте диск и заполните член соединения, чтобы он поддерживал `New-PSDrive` командлет.</span><span class="sxs-lookup"><span data-stu-id="009ad-127">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>
- <span data-ttu-id="009ad-128">Проверьте объект [System.Management.Automation.PSDривеинфо](/dotnet/api/System.Management.Automation.PSDriveInfo) для предложенного диска.</span><span class="sxs-lookup"><span data-stu-id="009ad-128">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>
- <span data-ttu-id="009ad-129">Измените объект [System.Management.Automation.PSDривеинфо](/dotnet/api/System.Management.Automation.PSDriveInfo) , который описывает диск с любой необходимой информацией о производительности или надежности, или предоставьте дополнительные данные для вызывающих объектов с помощью диска.</span><span class="sxs-lookup"><span data-stu-id="009ad-129">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>
- <span data-ttu-id="009ad-130">Обработка сбоев с помощью метода [System. Management. Automation. Provider. кмдлетпровидер. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) и возврата `null` .</span><span class="sxs-lookup"><span data-stu-id="009ad-130">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="009ad-131">Этот метод возвращает либо сведения о диске, которые были переданы методу, либо зависящую от поставщика версию этого метода.</span><span class="sxs-lookup"><span data-stu-id="009ad-131">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="009ad-132">Присоединение динамических параметров к Невдриве</span><span class="sxs-lookup"><span data-stu-id="009ad-132">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="009ad-133">Для `New-PSDrive` командлета, поддерживаемого поставщиком дисков, могут потребоваться дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="009ad-133">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="009ad-134">Чтобы присоединить эти динамические параметры к командлету, поставщик реализует метод [System. Management. Automation. Provider. дривекмдлетпровидер. невдривединамикпараметерс \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) .</span><span class="sxs-lookup"><span data-stu-id="009ad-134">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="009ad-135">Этот метод возвращает объект со свойствами и полями с атрибутами синтаксического анализа, похожими на класс командлета или объект [System. Management. Automation. рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) .</span><span class="sxs-lookup"><span data-stu-id="009ad-135">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="009ad-136">Этот метод не переопределяется этим поставщиком диска.</span><span class="sxs-lookup"><span data-stu-id="009ad-136">This drive provider does not override this method.</span></span> <span data-ttu-id="009ad-137">Однако следующий код демонстрирует реализацию этого метода по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="009ad-137">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="009ad-138">Удаление диска</span><span class="sxs-lookup"><span data-stu-id="009ad-138">Removing a Drive</span></span>

<span data-ttu-id="009ad-139">Чтобы закрыть подключение к базе данных, поставщик накопителя должен реализовать метод [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) .</span><span class="sxs-lookup"><span data-stu-id="009ad-139">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="009ad-140">Этот метод закрывает подключение к диску после очистки сведений, относящихся к поставщику.</span><span class="sxs-lookup"><span data-stu-id="009ad-140">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="009ad-141">В следующем коде показана реализация метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для данного поставщика накопителя:</span><span class="sxs-lookup"><span data-stu-id="009ad-141">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="91-116":::

<span data-ttu-id="009ad-142">Если диск можно удалить, метод должен вернуть сведения, передаваемые в метод, с помощью `drive` параметра.</span><span class="sxs-lookup"><span data-stu-id="009ad-142">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="009ad-143">Если диск не может быть удален, метод должен записать исключение, а затем вернуть значение `null` .</span><span class="sxs-lookup"><span data-stu-id="009ad-143">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="009ad-144">Если поставщик не переопределяет этот метод, реализация по умолчанию этого метода просто возвращает сведения о диске, переданные в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="009ad-144">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="009ad-145">Инициализация дисков по умолчанию</span><span class="sxs-lookup"><span data-stu-id="009ad-145">Initializing Default Drives</span></span>

<span data-ttu-id="009ad-146">Поставщик дисков реализует метод [System.Management.Automation.Provider.Drivecmdletprovider.Iniтиализедефаултдривес \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) для подключения дисков.</span><span class="sxs-lookup"><span data-stu-id="009ad-146">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="009ad-147">Например, поставщик Active Directory может подключить диск для контекста именования по умолчанию, если компьютер присоединен к домену.</span><span class="sxs-lookup"><span data-stu-id="009ad-147">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="009ad-148">Этот метод возвращает коллекцию сведений о инициализированных дисках или пустую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="009ad-148">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="009ad-149">Вызов этого метода выполняется после того, как среда выполнения Windows PowerShell вызывает метод [System. Management. Automation. Provider. кмдлетпровидер. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) для инициализации поставщика.</span><span class="sxs-lookup"><span data-stu-id="009ad-149">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="009ad-150">Этот поставщик дисков не переопределяет метод [System.Management.Automation.Provider.Drivecmdletprovider.Iniтиализедефаултдривес \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) .</span><span class="sxs-lookup"><span data-stu-id="009ad-150">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="009ad-151">Однако в следующем коде показана реализация по умолчанию, которая возвращает пустую коллекцию Drive:</span><span class="sxs-lookup"><span data-stu-id="009ad-151">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="009ad-152">Вопросы, связанные с реализацией Инитиализедефаултдривес</span><span class="sxs-lookup"><span data-stu-id="009ad-152">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="009ad-153">Все поставщики дисков должны подключить корневой диск, чтобы помочь пользователю с его обнаружением.</span><span class="sxs-lookup"><span data-stu-id="009ad-153">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="009ad-154">Корневой диск может иметь список расположений, которые служат корнями для других подключенных дисков.</span><span class="sxs-lookup"><span data-stu-id="009ad-154">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="009ad-155">Например, поставщик Active Directory может создать диск, содержащий список контекстов именования, находящихся в `namingContext` атрибутах в корневой распределенной системной среде (DSE).</span><span class="sxs-lookup"><span data-stu-id="009ad-155">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="009ad-156">Это помогает пользователям обнаружить точки подключения для других дисков.</span><span class="sxs-lookup"><span data-stu-id="009ad-156">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="009ad-157">Образец кода</span><span class="sxs-lookup"><span data-stu-id="009ad-157">Code Sample</span></span>

<span data-ttu-id="009ad-158">Полный пример кода см. в разделе [пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md).</span><span class="sxs-lookup"><span data-stu-id="009ad-158">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="009ad-159">Тестирование поставщика диска Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="009ad-159">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="009ad-160">Когда ваш поставщик Windows PowerShell зарегистрирован в Windows PowerShell, его можно протестировать, запустив в командной строке поддерживаемые командлеты, включая все командлеты, доступные при наследовании.</span><span class="sxs-lookup"><span data-stu-id="009ad-160">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="009ad-161">Давайте протестируем пример поставщика дисков.</span><span class="sxs-lookup"><span data-stu-id="009ad-161">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="009ad-162">Выполните `Get-PSProvider` командлет, чтобы получить список поставщиков, чтобы убедиться в наличии поставщика диска акцессдб.</span><span class="sxs-lookup"><span data-stu-id="009ad-162">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="009ad-163">**> PS`Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="009ad-163">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="009ad-164">Появится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="009ad-164">The following output appears:</span></span>

   ```Output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. <span data-ttu-id="009ad-165">Убедитесь, что имя сервера базы данных (DSN) существует для базы данных, путем доступа к части **данных** **средств администрирования** для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="009ad-165">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="009ad-166">В таблице **пользовательское имя пользователя** дважды щелкните **база данных MS Access** и добавьте путь к диску `C:\ps\northwind.mdb` .</span><span class="sxs-lookup"><span data-stu-id="009ad-166">In the **User DSN** table, double-click **MS Access Database** and add the drive path `C:\ps\northwind.mdb`.</span></span>

3. <span data-ttu-id="009ad-167">Создайте новый диск с помощью образца поставщика дисков:</span><span class="sxs-lookup"><span data-stu-id="009ad-167">Create a new drive using the sample drive provider:</span></span>

   ```powershell
   new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb`
   ```

   <span data-ttu-id="009ad-168">Появится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="009ad-168">The following output appears:</span></span>

   ```Output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="009ad-169">Проверьте подключение.</span><span class="sxs-lookup"><span data-stu-id="009ad-169">Validate the connection.</span></span> <span data-ttu-id="009ad-170">Так как подключение определено как член диска, его можно проверить с помощью командлета Get-Пддриве.</span><span class="sxs-lookup"><span data-stu-id="009ad-170">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="009ad-171">Пользователь еще не может взаимодействовать с поставщиком как диск, так как поставщику требуются функциональные возможности контейнера для этого взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="009ad-171">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="009ad-172">Дополнительные сведения см. [в разделе Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="009ad-172">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="009ad-173">**> PS ("Get-PSDrive MyDB"). подключение**</span><span class="sxs-lookup"><span data-stu-id="009ad-173">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="009ad-174">Появится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="009ad-174">The following output appears:</span></span>

   ```Output
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

5. <span data-ttu-id="009ad-175">Удалите диск и завершите работу оболочки:</span><span class="sxs-lookup"><span data-stu-id="009ad-175">Remove the drive and exit the shell:</span></span>

   ```powershell
   PS> remove-psdrive mydb
   PS> exit
   ```

## <a name="see-also"></a><span data-ttu-id="009ad-176">См. также:</span><span class="sxs-lookup"><span data-stu-id="009ad-176">See Also</span></span>

[<span data-ttu-id="009ad-177">Создание поставщиков Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="009ad-177">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="009ad-178">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="009ad-178">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="009ad-179">Создание базового поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="009ad-179">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)
