---
title: Примеры использования Windows PowerShell поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e879ba7-c334-460b-94a1-3e9b63d3d8de
caps.latest.revision: 5
ms.openlocfilehash: 151b7125afe1b0d386467a0e5f89225716857ac2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080889"
---
# <a name="windows-powershell-provider-quickstart"></a><span data-ttu-id="a2b2b-102">Краткое руководство по поставщикам Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2b2b-102">Windows PowerShell Provider Quickstart</span></span>

<span data-ttu-id="a2b2b-103">В этом разделе объясняется, как создать поставщик Windows PowerShell, имеющий основные функциональные возможности создания нового диска.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-103">This topic explains how to create a Windows PowerShell provider that has basic functionality of creating a new drive.</span></span> <span data-ttu-id="a2b2b-104">Общие сведения о поставщиках см. в разделе [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a2b2b-104">For general information about providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="a2b2b-105">Примеры поставщиков с более полному набору функций, см. в разделе [примеры поставщиков](./provider-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a2b2b-105">For examples of providers with more complete functionality, see [Provider Samples](./provider-samples.md).</span></span>

## <a name="writing-a-basic-provider"></a><span data-ttu-id="a2b2b-106">Разработка основных поставщика</span><span class="sxs-lookup"><span data-stu-id="a2b2b-106">Writing a basic provider</span></span>

<span data-ttu-id="a2b2b-107">Большинство базовых функций поставщика Windows PowerShell — Создание и удаление дисков.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-107">The most basic functionality of a Windows PowerShell provider is to create and remove drives.</span></span> <span data-ttu-id="a2b2b-108">В этом примере мы реализуем [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) методы [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-108">In this example, we implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="a2b2b-109">Вы также узнаете, как объявить класс поставщика.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-109">You will also see how to declare a provider class.</span></span>

<span data-ttu-id="a2b2b-110">При написании поставщика можно указать диски дисков по умолчанию, которые создаются автоматически, когда доступен поставщик.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-110">When you write a provider, you can specify default drives-drives that are created automatically when the provider is available.</span></span> <span data-ttu-id="a2b2b-111">Можно также определить метод для создания новых дисков, которые используют этот поставщик.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-111">You also define a method to create new drives that use that provider.</span></span>

<span data-ttu-id="a2b2b-112">Примеры, приведенные в этом разделе основаны на [AccessDBProviderSample02](./accessdbprovidersample02.md) образца, который является частью большого примера, представляющий базу данных Access как диск Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-112">The examples provided in this topic are based on the [AccessDBProviderSample02](./accessdbprovidersample02.md) sample, which is part of a larger sample that represents an Access database as a Windows PowerShell drive.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="a2b2b-113">Настройка проекта</span><span class="sxs-lookup"><span data-stu-id="a2b2b-113">Setting up the project</span></span>

<span data-ttu-id="a2b2b-114">В Visual Studio создайте проект библиотеки классов с именем AccessDBProviderSample.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-114">In Visual Studio, create a Class Library project named AccessDBProviderSample.</span></span> <span data-ttu-id="a2b2b-115">Выполните следующие действия, чтобы настроить проект так, что Windows PowerShell запустится, а поставщик будет загружаться в сеанс, во время построения и запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-115">Complete the following steps to configure your project so that Windows PowerShell will start, and the provider will be loaded into the session, when you build and start your project.</span></span>

##### <a name="configure-the-provider-project"></a><span data-ttu-id="a2b2b-116">Настройка проекта поставщика</span><span class="sxs-lookup"><span data-stu-id="a2b2b-116">Configure the provider project</span></span>

1. <span data-ttu-id="a2b2b-117">Добавьте System.Management.Automation сборку как ссылку в проект.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-117">Add the System.Management.Automation assembly as a reference to your project.</span></span>

2. <span data-ttu-id="a2b2b-118">Нажмите кнопку **проект > Свойства AccessDBProviderSample > Отладка**.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-118">Click **Project > AccessDBProviderSample Properties > Debug**.</span></span> <span data-ttu-id="a2b2b-119">В **проект начальной**, нажмите кнопку **запуск внешней программы**и перейдите к исполняемому файлу, Windows PowerShell (обычно c:\Windows\System32\WindowsPowerShell\v1.0\\. powershell.exe).</span><span class="sxs-lookup"><span data-stu-id="a2b2b-119">In **Start project**, click **Start external program**, and navigate to the Windows PowerShell executable (typically c:\Windows\System32\WindowsPowerShell\v1.0\\.powershell.exe).</span></span>

3. <span data-ttu-id="a2b2b-120">В разделе **параметры запуска**, введите следующий текст в **аргументы командной строки** поле: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span><span class="sxs-lookup"><span data-stu-id="a2b2b-120">Under **Start Options**, enter the following into the **Command line arguments** box: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="a2b2b-121">Объявление класса поставщика</span><span class="sxs-lookup"><span data-stu-id="a2b2b-121">Declaring the provider class</span></span>

<span data-ttu-id="a2b2b-122">Наш поставщик является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-122">Our provider derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="a2b2b-123">Большинство поставщиков, которые предоставляют реальные функции (доступ к и управления элементами, перейдя в хранилище данных и получение и настройка содержимое элементов) являются производными от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-123">Most providers that provide real functionality (accessing and manipulating items, navigating the data store, and getting and setting content of items) derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="a2b2b-124">Помимо указания, что класс является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), необходимо снабдить его с [ System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-124">In addition to specifying that the class derives from [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), you must decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) as shown in the example.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System;
  using System.Data;
  using System.Data.Odbc;
  using System.IO;
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  #region AccessDBProvider

  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : DriveCmdletProvider
  {

}
}
```

### <a name="implementing-newdrive"></a><span data-ttu-id="a2b2b-125">Реализация NewDrive</span><span class="sxs-lookup"><span data-stu-id="a2b2b-125">Implementing NewDrive</span></span>

<span data-ttu-id="a2b2b-126">[System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метод вызывается подсистемой Windows PowerShell, когда пользователь вызывает [Microsoft.PowerShell.Commands.New-PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.New-PSDrive)командлет, указав имя вашего поставщика.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-126">The [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.New-PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.New-PSDrive) cmdlet specifying the name of your provider.</span></span> <span data-ttu-id="a2b2b-127">Подсистема Windows PowerShell, передается параметр PSDriveInfo и метод возвращает новый диск подсистемы Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-127">The PSDriveInfo parameter is passed by the Windows PowerShell engine, and the method returns the new drive to the Windows PowerShell engine.</span></span> <span data-ttu-id="a2b2b-128">Этот метод должен объявляться внутри класса, созданный ранее.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-128">This method must be declared within the class created above.</span></span>

<span data-ttu-id="a2b2b-129">Метод сначала проверяет, чтобы убедиться в том, как объект диска, так и в корневом каталоге диска были переданы в существует, возвращая `null` Если любой из них — нет.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-129">The method first checks to make sure both the drive object and the drive root that were passed in exist, returning `null` if either of them do not.</span></span> <span data-ttu-id="a2b2b-130">Затем конструктор внутреннего класса AccessDBPSDriveInfo используется для создания нового диска и представляет подключение к базе данных Access диска.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-130">It then uses a constructor of the internal class AccessDBPSDriveInfo to create a new drive and a connection to the Access database the drive represents.</span></span>

```csharp
protected override PSDriveInfo NewDrive(PSDriveInfo drive)
    {
      // Check if the drive object is null.
      if (drive == null)
      {
        WriteError(new ErrorRecord(
                   new ArgumentNullException("drive"),
                   "NullDrive",
                   ErrorCategory.InvalidArgument,
                   null));

        return null;
      }

      // Check if the drive root is not null or empty
      // and if it is an existing file.
      if (String.IsNullOrEmpty(drive.Root) || (File.Exists(drive.Root) == false))
      {
        WriteError(new ErrorRecord(
                   new ArgumentException("drive.Root"),
                   "NoRoot",
                   ErrorCategory.InvalidArgument,
                   drive));

        return null;
      }

      // Create a new drive and create an ODBC connection to the new drive.
      AccessDBPSDriveInfo accessDBPSDriveInfo = new AccessDBPSDriveInfo(drive);
      OdbcConnectionStringBuilder builder = new OdbcConnectionStringBuilder();

      builder.Driver = "Microsoft Access Driver (*.mdb)";
      builder.Add("DBQ", drive.Root);

      OdbcConnection conn = new OdbcConnection(builder.ConnectionString);
      conn.Open();
      accessDBPSDriveInfo.Connection = conn;

      return accessDBPSDriveInfo;
    }
```

<span data-ttu-id="a2b2b-131">Ниже приведен AccessDBPSDriveInfo внутренний класс, включает конструктор, используемый для создания нового диска, который содержит сведения о состоянии для диска.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-131">The following is the AccessDBPSDriveInfo internal class that includes the constructor used to create a new drive, and contains the state information for the drive.</span></span>

```csharp
internal class AccessDBPSDriveInfo : PSDriveInfo
  {
    /// <summary>
    /// A reference to the connection to the database.
    /// </summary>
    private OdbcConnection connection;

    /// <summary>
    /// Initializes a new instance of the AccessDBPSDriveInfo class.
    /// The constructor takes a single argument.
    /// </summary>
    /// <param name="driveInfo">Drive defined by this provider</param>
    public AccessDBPSDriveInfo(PSDriveInfo driveInfo)
           : base(driveInfo)
    {
    }

    /// <summary>
    /// Gets or sets the ODBC connection information.
    /// </summary>
    public OdbcConnection Connection
    {
        get { return this.connection; }
        set { this.connection = value; }
    }
  }
```

### <a name="implementing-removedrive"></a><span data-ttu-id="a2b2b-132">Реализация RemoveDrive</span><span class="sxs-lookup"><span data-stu-id="a2b2b-132">Implementing RemoveDrive</span></span>

<span data-ttu-id="a2b2b-133">[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод вызывается подсистемой Windows PowerShell, когда пользователь вызывает [Microsoft.PowerShell.Commands.Remove-PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.Remove-PSDrive) командлета.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-133">The [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.Remove-PSDrive](/dotnet/api/Microsoft.PowerShell.Commands.Remove-PSDrive) cmdlet.</span></span> <span data-ttu-id="a2b2b-134">Метод в этом поставщике закрывает подключение к базе данных Access.</span><span class="sxs-lookup"><span data-stu-id="a2b2b-134">The method in this provider closes the connection to the Access database.</span></span>

```csharp
protected override PSDriveInfo RemoveDrive(PSDriveInfo drive)
    {
      // Check if drive object is null.
      if (drive == null)
      {
        WriteError(new ErrorRecord(
                   new ArgumentNullException("drive"),
                   "NullDrive",
                   ErrorCategory.InvalidArgument,
                   drive));

        return null;
      }

      // Close the ODBC connection to the drive.
      AccessDBPSDriveInfo accessDBPSDriveInfo = drive as AccessDBPSDriveInfo;

      if (accessDBPSDriveInfo == null)
      {
         return null;
      }

      accessDBPSDriveInfo.Connection.Close();

      return accessDBPSDriveInfo;
    }
```