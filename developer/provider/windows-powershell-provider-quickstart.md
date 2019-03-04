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
ms.openlocfilehash: ab78bcad301215bca9b5324bdb8de863899edec6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862150"
---
# <a name="windows-powershell-provider-quickstart"></a>Краткое руководство по поставщикам Windows PowerShell

В этом разделе объясняется, как создать поставщик Windows PowerShell, имеющий основные функциональные возможности создания нового диска. Общие сведения о поставщиках см. в разделе [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md). Примеры поставщиков с более полному набору функций, см. в разделе [примеры поставщиков](./provider-samples.md).

## <a name="writing-a-basic-provider"></a>Разработка основных поставщика

Большинство базовых функций поставщика Windows PowerShell — Создание и удаление дисков. В этом примере мы реализуем [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) методы [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класса. Вы также узнаете, как объявить класс поставщика.

При написании поставщика можно указать диски дисков по умолчанию, которые создаются автоматически, когда доступен поставщик. Можно также определить метод для создания новых дисков, которые используют этот поставщик.

Примеры, приведенные в этом разделе основаны на [AccessDBProviderSample02](./accessdbprovidersample02.md) образца, который является частью большого примера, представляющий базу данных Access как диск Windows PowerShell.

### <a name="setting-up-the-project"></a>Настройка проекта

В Visual Studio создайте проект библиотеки классов с именем AccessDBProviderSample. Выполните следующие действия, чтобы настроить проект так, что Windows PowerShell запустится, а поставщик будет загружаться в сеанс, во время построения и запуска проекта.

##### <a name="configure-the-provider-project"></a>Настройка проекта поставщика

1. Добавьте System.Management.Automation сборку как ссылку в проект.

2. Нажмите кнопку **проект > Свойства AccessDBProviderSample > Отладка**. В **проект начальной**, нажмите кнопку **запуск внешней программы**и перейдите к исполняемому файлу, Windows PowerShell (обычно c:\Windows\System32\WindowsPowerShell\v1.0\\. powershell.exe).

3. В разделе **параметры запуска**, введите следующий текст в **аргументы командной строки** поле: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`

### <a name="declaring-the-provider-class"></a>Объявление класса поставщика

Наш поставщик является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класса. Большинство поставщиков, которые предоставляют реальные функции (доступ к и управления элементами, перейдя в хранилище данных и получение и настройка содержимое элементов) являются производными от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.

Помимо указания, что класс является производным от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), необходимо снабдить его с [ System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) как показано в примере.

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

### <a name="implementing-newdrive"></a>Реализация NewDrive

[System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метод вызывается подсистемой Windows PowerShell, когда пользователь вызывает [Microsoft.Powershell.Commands.New-Psdrive](/dotnet/api/Microsoft.PowerShell.Commands.New-PSDrive)командлет, указав имя вашего поставщика. Подсистема Windows PowerShell, передается параметр PSDriveInfo и метод возвращает новый диск подсистемы Windows PowerShell. Этот метод должен объявляться внутри класса, созданный ранее.

Метод сначала проверяет, чтобы убедиться в том, как объект диска, так и в корневом каталоге диска были переданы в существует, возвращая `null` Если любой из них — нет. Затем конструктор внутреннего класса AccessDBPSDriveInfo используется для создания нового диска и представляет подключение к базе данных Access диска.

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

Ниже приведен AccessDBPSDriveInfo внутренний класс, включает конструктор, используемый для создания нового диска, который содержит сведения о состоянии для диска.

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

### <a name="implementing-removedrive"></a>Реализация RemoveDrive

[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод вызывается подсистемой Windows PowerShell, когда пользователь вызывает [Microsoft.Powershell.Commands.Remove-Psdrive](/dotnet/api/Microsoft.PowerShell.Commands.Remove-PSDrive) командлета. Метод в этом поставщике закрывает подключение к базе данных Access.

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