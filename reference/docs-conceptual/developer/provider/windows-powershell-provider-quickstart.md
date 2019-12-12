---
title: Краткое руководство по поставщику Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e879ba7-c334-460b-94a1-3e9b63d3d8de
caps.latest.revision: 5
ms.openlocfilehash: 949c0d63b1e5bca1bfe670362df4297c29e98fcc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359923"
---
# <a name="windows-powershell-provider-quickstart"></a><span data-ttu-id="7550a-102">Краткое руководство по поставщикам Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7550a-102">Windows PowerShell Provider Quickstart</span></span>

<span data-ttu-id="7550a-103">В этом разделе объясняется, как создать поставщик Windows PowerShell с базовой функциональностью создания нового диска.</span><span class="sxs-lookup"><span data-stu-id="7550a-103">This topic explains how to create a Windows PowerShell provider that has basic functionality of creating a new drive.</span></span> <span data-ttu-id="7550a-104">Общие сведения о поставщиках см. в статье Общие сведения о [поставщике Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7550a-104">For general information about providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="7550a-105">Примеры поставщиков с более полным набором функций см. в статье [примеры поставщиков](./provider-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7550a-105">For examples of providers with more complete functionality, see [Provider Samples](./provider-samples.md).</span></span>

## <a name="writing-a-basic-provider"></a><span data-ttu-id="7550a-106">Написание базового поставщика</span><span class="sxs-lookup"><span data-stu-id="7550a-106">Writing a basic provider</span></span>

<span data-ttu-id="7550a-107">Наиболее простой функцией поставщика Windows PowerShell является создание и удаление дисков.</span><span class="sxs-lookup"><span data-stu-id="7550a-107">The most basic functionality of a Windows PowerShell provider is to create and remove drives.</span></span> <span data-ttu-id="7550a-108">В этом примере мы реализуем методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. Ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="7550a-108">In this example, we implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="7550a-109">Вы также узнаете, как объявить класс поставщика.</span><span class="sxs-lookup"><span data-stu-id="7550a-109">You will also see how to declare a provider class.</span></span>

<span data-ttu-id="7550a-110">При создании поставщика можно указать диски по умолчанию, которые создаются автоматически при доступности поставщика.</span><span class="sxs-lookup"><span data-stu-id="7550a-110">When you write a provider, you can specify default drives-drives that are created automatically when the provider is available.</span></span> <span data-ttu-id="7550a-111">Вы также определите метод для создания новых дисков, использующих этот поставщик.</span><span class="sxs-lookup"><span data-stu-id="7550a-111">You also define a method to create new drives that use that provider.</span></span>

<span data-ttu-id="7550a-112">Примеры, приведенные в этом разделе, основаны на образце [AccessDBProviderSample02](./accessdbprovidersample02.md) , который является частью более крупного примера, представляющего базу данных Access в качестве диска Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7550a-112">The examples provided in this topic are based on the [AccessDBProviderSample02](./accessdbprovidersample02.md) sample, which is part of a larger sample that represents an Access database as a Windows PowerShell drive.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="7550a-113">Настройка проекта</span><span class="sxs-lookup"><span data-stu-id="7550a-113">Setting up the project</span></span>

<span data-ttu-id="7550a-114">В Visual Studio создайте проект библиотеки классов с именем Акцессдбпровидерсампле.</span><span class="sxs-lookup"><span data-stu-id="7550a-114">In Visual Studio, create a Class Library project named AccessDBProviderSample.</span></span> <span data-ttu-id="7550a-115">Выполните следующие действия, чтобы настроить проект для запуска Windows PowerShell, и поставщик будет загружен в сеанс при сборке и запуске проекта.</span><span class="sxs-lookup"><span data-stu-id="7550a-115">Complete the following steps to configure your project so that Windows PowerShell will start, and the provider will be loaded into the session, when you build and start your project.</span></span>

##### <a name="configure-the-provider-project"></a><span data-ttu-id="7550a-116">Настройка проекта поставщика</span><span class="sxs-lookup"><span data-stu-id="7550a-116">Configure the provider project</span></span>

1. <span data-ttu-id="7550a-117">Добавьте сборку System. Management. Automation в качестве ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="7550a-117">Add the System.Management.Automation assembly as a reference to your project.</span></span>

2. <span data-ttu-id="7550a-118">Щелкните **проект > свойства акцессдбпровидерсампле > Отладка**.</span><span class="sxs-lookup"><span data-stu-id="7550a-118">Click **Project > AccessDBProviderSample Properties > Debug**.</span></span> <span data-ttu-id="7550a-119">В меню **Запуск проекта**щелкните **запустить внешнюю программу**и перейдите к исполняемому файлу Windows PowerShell (обычно это c:\Windows\System32\WindowsPowerShell\v1.0\\. PowerShell. exe).</span><span class="sxs-lookup"><span data-stu-id="7550a-119">In **Start project**, click **Start external program**, and navigate to the Windows PowerShell executable (typically c:\Windows\System32\WindowsPowerShell\v1.0\\.powershell.exe).</span></span>

3. <span data-ttu-id="7550a-120">В разделе **Параметры запуска**введите следующий текст в поле **аргументы командной строки** : `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span><span class="sxs-lookup"><span data-stu-id="7550a-120">Under **Start Options**, enter the following into the **Command line arguments** box: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="7550a-121">Объявление класса поставщика</span><span class="sxs-lookup"><span data-stu-id="7550a-121">Declaring the provider class</span></span>

<span data-ttu-id="7550a-122">Наш поставщик является производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="7550a-122">Our provider derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="7550a-123">Большинство поставщиков, которые предоставляют реальную функциональность (доступ к элементам и управление ими, перемещение по хранилищу данных, получение и задание содержимого элементов), являются производными от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="7550a-123">Most providers that provide real functionality (accessing and manipulating items, navigating the data store, and getting and setting content of items) derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="7550a-124">Помимо указания того, что класс является производным от [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), необходимо снабдить его атрибутом [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) , как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="7550a-124">In addition to specifying that the class derives from [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), you must decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) as shown in the example.</span></span>

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

### <a name="implementing-newdrive"></a><span data-ttu-id="7550a-125">Реализация Невдриве</span><span class="sxs-lookup"><span data-stu-id="7550a-125">Implementing NewDrive</span></span>

<span data-ttu-id="7550a-126">Метод [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) вызывается подсистемой Windows PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. невпсдривекомманд](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand) , указывающий имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="7550a-126">The [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.NewPSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand) cmdlet specifying the name of your provider.</span></span> <span data-ttu-id="7550a-127">Параметр PSDriveInfo передается подсистемой Windows PowerShell, а метод возвращает новый диск подсистеме Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7550a-127">The PSDriveInfo parameter is passed by the Windows PowerShell engine, and the method returns the new drive to the Windows PowerShell engine.</span></span> <span data-ttu-id="7550a-128">Этот метод должен быть объявлен в классе, созданном выше.</span><span class="sxs-lookup"><span data-stu-id="7550a-128">This method must be declared within the class created above.</span></span>

<span data-ttu-id="7550a-129">Сначала метод проверяет, чтобы убедиться, что были переданы как объект диска, так и корневой диск, и возвращает `null`, если один из них не имеет.</span><span class="sxs-lookup"><span data-stu-id="7550a-129">The method first checks to make sure both the drive object and the drive root that were passed in exist, returning `null` if either of them do not.</span></span> <span data-ttu-id="7550a-130">Затем он использует конструктор внутреннего класса Акцессдбпсдривеинфо для создания нового диска и соединения с базой данных Access, которую представляет диск.</span><span class="sxs-lookup"><span data-stu-id="7550a-130">It then uses a constructor of the internal class AccessDBPSDriveInfo to create a new drive and a connection to the Access database the drive represents.</span></span>

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

<span data-ttu-id="7550a-131">Ниже приведен внутренний класс Акцессдбпсдривеинфо, который включает конструктор, используемый для создания нового диска, и содержит сведения о состоянии для диска.</span><span class="sxs-lookup"><span data-stu-id="7550a-131">The following is the AccessDBPSDriveInfo internal class that includes the constructor used to create a new drive, and contains the state information for the drive.</span></span>

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

### <a name="implementing-removedrive"></a><span data-ttu-id="7550a-132">Реализация Ремоведриве</span><span class="sxs-lookup"><span data-stu-id="7550a-132">Implementing RemoveDrive</span></span>

<span data-ttu-id="7550a-133">Метод [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) вызывается подсистемой Windows PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. ремовепсдривекомманд](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand) .</span><span class="sxs-lookup"><span data-stu-id="7550a-133">The [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.RemovePSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand) cmdlet.</span></span> <span data-ttu-id="7550a-134">Метод в этом поставщике закрывает соединение с базой данных Access.</span><span class="sxs-lookup"><span data-stu-id="7550a-134">The method in this provider closes the connection to the Access database.</span></span>

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