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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359923"
---
# <a name="windows-powershell-provider-quickstart"></a>Краткое руководство по поставщикам Windows PowerShell

В этом разделе объясняется, как создать поставщик Windows PowerShell с базовой функциональностью создания нового диска. Общие сведения о поставщиках см. в статье Общие сведения о [поставщике Windows PowerShell](./windows-powershell-provider-overview.md). Примеры поставщиков с более полным набором функций см. в статье [примеры поставщиков](./provider-samples.md).

## <a name="writing-a-basic-provider"></a>Написание базового поставщика

Наиболее простой функцией поставщика Windows PowerShell является создание и удаление дисков. В этом примере мы реализуем методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) элемента [управления Класс System. Management. Automation. Provider. Дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Вы также узнаете, как объявить класс поставщика.

При создании поставщика можно указать диски по умолчанию, которые создаются автоматически при доступности поставщика. Вы также определите метод для создания новых дисков, использующих этот поставщик.

Примеры, приведенные в этом разделе, основаны на образце [AccessDBProviderSample02](./accessdbprovidersample02.md) , который является частью более крупного примера, представляющего базу данных Access в качестве диска Windows PowerShell.

### <a name="setting-up-the-project"></a>Настройка проекта

В Visual Studio создайте проект библиотеки классов с именем Акцессдбпровидерсампле. Выполните следующие действия, чтобы настроить проект для запуска Windows PowerShell, и поставщик будет загружен в сеанс при сборке и запуске проекта.

##### <a name="configure-the-provider-project"></a>Настройка проекта поставщика

1. Добавьте сборку System. Management. Automation в качестве ссылки на проект.

2. Щелкните **проект > свойства акцессдбпровидерсампле > Отладка**. В меню **Запуск проекта**выберите пункт **запустить внешнюю программу**и перейдите к исполняемому файлу Windows PowerShell (обычно это c:\windows\system32\windowspowershell\ v1.0\\.powershell.exe).

3. В разделе **Параметры запуска**введите следующий текст в поле **аргументы командной строки** : `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`.

### <a name="declaring-the-provider-class"></a>Объявление класса поставщика

Наш поставщик является производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) . Большинство поставщиков, которые предоставляют реальную функциональность (доступ к элементам и управление ими, перемещение по хранилищу данных, получение и задание содержимого элементов), являются производными от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

Помимо указания того, что класс является производным от [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), необходимо снабдить его атрибутом [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) , как показано в примере. .

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

### <a name="implementing-newdrive"></a>Реализация Невдриве

Метод [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) вызывается подсистемой Windows PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. невпсдривекомманд](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand) , указывающий имя поставщики. Параметр PSDriveInfo передается подсистемой Windows PowerShell, а метод возвращает новый диск подсистеме Windows PowerShell. Этот метод должен быть объявлен в классе, созданном выше.

Сначала метод проверяет, чтобы убедиться в том, что были переданы как объект диска, так и корневой диск, и возвращает `null`, если один из них не имеет. Затем он использует конструктор внутреннего класса Акцессдбпсдривеинфо для создания нового диска и соединения с базой данных Access, которую представляет диск.

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

Ниже приведен внутренний класс Акцессдбпсдривеинфо, который включает конструктор, используемый для создания нового диска, и содержит сведения о состоянии для диска.

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

### <a name="implementing-removedrive"></a>Реализация Ремоведриве

Метод [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) вызывается подсистемой Windows PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. ремовепсдривекомманд](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand) . Метод в этом поставщике закрывает соединение с базой данных Access.

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