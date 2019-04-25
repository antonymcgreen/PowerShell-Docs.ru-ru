---
title: Создание поставщика элемента | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 606c880c-6cf1-4ea6-8730-dbf137bfabff
caps.latest.revision: 5
ms.openlocfilehash: 9285a2f0e673de8b86084157423512bdeeda109d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080821"
---
# <a name="writing-an-item-provider"></a>Написание поставщика элемента

В этом разделе описывается реализация методов поставщика Windows PowerShell, доступа и работы с элементами в хранилище данных. Чтобы иметь возможность получать доступ к элементам, поставщик должен быть производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.

Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных. Существует несколько вспомогательные методы и классы, используемые для взаимодействия с базой данных. Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample03](./accessdbprovidersample03.md)

Дополнительные сведения о поставщиках Windows PowerShell см. в разделе [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).

## <a name="implementing-item-methods"></a>Реализация методов элемента

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класс предоставляет несколько методов, которые могут использоваться для доступа и работы с элементами в хранилище данных. Полный список этих методов, см. в разделе [ItemCmdletProvider методы](http://msdn.microsoft.com/library/system.management.automation.provider.itemcmdletprovider_methods\(v=vs.85\).aspx). В этом примере мы будем реализовывать четыре из этих методов. [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) возвращает элемент по указанному пути. [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) задает значение указанного элемента. [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) проверяет, существует ли элемент по указанному пути. [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) проверяет путь к см. в разделе, если он преобразуется в расположение в хранилище данных.

> [!NOTE]
> Материал данной статьи основан на информации из [QuickStart поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md). В этом разделе рассматриваются базовые сведения о настройке проекта поставщика, или как реализовать методы унаследована от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс, создавать и удалять диски.

### <a name="declaring-the-provider-class"></a>Объявление класса поставщика

Объявите поставщику о необходимости получения из [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса и установить для него с помощью [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a>Реализация GetItem

[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) вызывается модулем PowerShell в том случае, когда пользователь вызывает [Microsoft.PowerShell.Commands.Get-Item](/dotnet/api/Microsoft.PowerShell.Commands.Get-Item) командлет на вашей Поставщик. Метод возвращает элемент по указанному пути. В примере базы данных Access метод проверяет, является ли элемент на самом диске, таблицы в базе данных или строки в базе данных. Метод отправляет элемент подсистемы PowerShell путем вызова [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) метод.

```csharp
protected override void GetItem(string path)
      {
          // check if the path represented is a drive
          if (PathIsDrive(path))
          {
              WriteItemObject(this.PSDriveInfo, path, true);
              return;
          }// if (PathIsDrive...

           // Get table name and row information from the path and do
           // necessary actions
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               DatabaseTableInfo table = GetTable(tableName);
               WriteItemObject(table, path, true);
           }
           else if (type == PathType.Row)
           {
               DatabaseRowInfo row = GetRow(tableName, rowNumber);
               WriteItemObject(row, path, false);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

### <a name="implementing-setitem"></a>Реализация SetItem

[System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) вызывается подсистемой PowerShell вызывается метод, когда пользователь вызывает [Microsoft.PowerShell.Commands.Set-Item](/dotnet/api/Microsoft.PowerShell.Commands.Set-Item) командлета . Он задает значение элемента по указанному пути.

В примере базы данных Access, имеет смысл только в том случае, если этот элемент является строкой, поэтому метод вызывает исключение, задайте значение элемента [NotSupportedException](http://msdn.microsoft.com/library/system.notsupportedexception\(v=vs.110\).aspx) когда элемент не является строкой.

```csharp
protected override void SetItem(string path, object values)
       {
           // Get type, table name and row number from the path specified
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type != PathType.Row)
           {
               WriteError(new ErrorRecord(new NotSupportedException(
                     "SetNotSupported"), "",
                  ErrorCategory.InvalidOperation, path));

               return;
           }

           // Get in-memory representation of table
           OdbcDataAdapter da = GetAdapterForTable(tableName);

           if (da == null)
           {
               return;
           }
           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           if (rowNumber >= table.Rows.Count)
           {
               // The specified row number has to be available. If not
               // NewItem has to be used to add a new row
               throw new ArgumentException("Row specified is not available");
           } // if (rowNum...

           string[] colValues = (values as string).Split(',');

           // set the specified row
           DataRow row = table.Rows[rowNumber];

           for (int i = 0; i < colValues.Length; i++)
           {
               row[i] = colValues[i];
           }

           // Update the table
           if (ShouldProcess(path, "SetItem"))
           {
               da.Update(ds, tableName);
           }

       }
```

### <a name="implementing-itemexists"></a>Реализация ItemExists

[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) метод вызывается подсистемой PowerShell, когда пользователь вызывает [Microsoft.PowerShell.Commands.Test-Path](/dotnet/api/Microsoft.PowerShell.Commands.Test-Path) командлета. Этот метод определяет, имеется ли элемент по указанному пути. Если элемент существует, метод передает его в модуль PowerShell, вызвав [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).

```csharp
protected override bool ItemExists(string path)
       {
           // check if the path represented is a drive
           if (PathIsDrive(path))
           {
               return true;
           }

           // Obtain type, table name and row number from path
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           DatabaseTableInfo table = GetTable(tableName);

           if (type == PathType.Table)
           {
               // if specified path represents a table then DatabaseTableInfo
               // object for the same should exist
               if (table != null)
               {
                   return true;
               }
           }
           else if (type == PathType.Row)
           {
               // if specified path represents a row then DatabaseTableInfo should
               // exist for the table and then specified row number must be within
               // the maximum row count in the table
               if (table != null && rowNumber < table.RowCount)
               {
                   return true;
               }
           }

           return false;

       }
```

### <a name="implementing-isvalidpath"></a>Реализация IsValidPath

[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) метод проверяет, является ли указанный путь синтаксически допустимым для текущего поставщика. Он не проверяет, существует ли элемент по пути.

```csharp
protected override bool IsValidPath(string path)
       {
           bool result = true;

           // check if the path is null or empty
           if (String.IsNullOrEmpty(path))
           {
               result = false;
           }

           // convert all separators in the path to a uniform one
           path = NormalizePath(path);

           // split the path into individual chunks
           string[] pathChunks = path.Split(pathSeparator.ToCharArray());

           foreach (string pathChunk in pathChunks)
           {
               if (pathChunk.Length == 0)
               {
                   result = false;
               }
           }
           return result;
       }
```

## <a name="next-steps"></a>Дальнейшие действия

Поставщик типичных реальных способен поддерживать элементы, содержащие другие элементы и перемещать элементы из одного расположения в пределах диска. Пример поставщика, который поддерживает контейнеры, см. в разделе [разработка поставщика контейнера](./writing-a-container-provider.md). Пример поставщика, который поддерживает перемещение элементов, см. в разделе [разработка поставщика навигации](./writing-a-navigation-provider.md).

## <a name="see-also"></a>См. также

[Разработка поставщика контейнера](./writing-a-container-provider.md)

[Разработка поставщика навигации](./writing-a-navigation-provider.md)

[Общие сведения о поставщике PowerShell Windows](./windows-powershell-provider-overview.md)