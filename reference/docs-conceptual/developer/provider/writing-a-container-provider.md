---
ms.date: 09/13/2016
ms.topic: reference
title: Написание поставщика контейнера
description: Написание поставщика контейнера
ms.openlocfilehash: 17ec3e11258ee77a8e569df1af3a0e9bcd9798b6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354938"
---
# <a name="writing-a-container-provider"></a>Написание поставщика контейнера

В этом разделе описывается реализация методов поставщика Windows PowerShell, поддерживающего элементы, которые содержат другие элементы, такие как папки в поставщике файловой системы. Чтобы иметь возможность поддерживать контейнеры, поставщик должен быть производным от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .

Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных. Существует несколько вспомогательных методов и классов, используемых для взаимодействия с базой данных. Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample04](./accessdbprovidersample04.md).

Дополнительные сведения о поставщиках Windows PowerShell см. в статье [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).

## <a name="implementing-container-methods"></a>Реализация методов контейнера

Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) реализует методы, которые поддерживают контейнеры, а также создают, копируют и удаляют элементы. Полный список этих методов см. в разделе [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider#methods).

> [!NOTE]
> В этом разделе содержатся сведения в [кратком руководстве поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md). В этом разделе не рассматриваются основные сведения о настройке проекта поставщика или реализации методов, унаследованных от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) , который создает и удаляет диски. В этом разделе также не рассматривается реализация методов, предоставляемых классом [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) . Пример реализации командлетов элементов см. в разделе [написание поставщика элементов](./writing-an-item-provider.md).

### <a name="declaring-the-provider-class"></a>Объявление класса поставщика

Объявите поставщика, производного от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) , и добавьте его в класс [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : ContainerCmdletProvider
   {

   }
```

### <a name="implementing-getchilditems"></a>Реализация Жетчилдитемс

Когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. жетчилдитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.Getchilditemcommand) , обработчик PowerShell вызывает метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) . Этот метод возвращает элементы, которые являются дочерними элементами элемента по указанному пути.

В примере с базой данных Access поведение метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) зависит от типа указанного элемента. Если элемент является диском, дочерние элементы являются таблицами, а метод возвращает набор таблиц из базы данных. Если указанный элемент является таблицей, то дочерние элементы являются строками этой таблицы. Если элемент является строкой, то он не имеет дочерних элементов, а метод возвращает только эту строку. Все дочерние элементы отправляются обратно в подсистему PowerShell методом [System. Management. Automation. Provider. кмдлетпровидер. вритеитемобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .

```csharp
protected override void GetChildItems(string path, bool recurse)
       {
           // If path represented is a drive then the children in the path are
           // tables. Hence all tables in the drive represented will have to be
           // returned
           if (PathIsDrive(path))
           {
               foreach (DatabaseTableInfo table in GetTables())
               {
                   WriteItemObject(table, path, true);

                   // if the specified item exists and recurse has been set then
                   // all child items within it have to be obtained as well
                   if (ItemExists(path) && recurse)
                   {
                       GetChildItems(path + pathSeparator + table.Name, recurse);
                   }
               } // foreach (DatabaseTableInfo...
           } // if (PathIsDrive...
           else
           {
               // Get the table name, row number and type of path from the
               // path specified
               string tableName;
               int rowNumber;

               PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

               if (type == PathType.Table)
               {
                   // Obtain all the rows within the table
                   foreach (DatabaseRowInfo row in GetRows(tableName))
                   {
                       WriteItemObject(row, path + pathSeparator + row.RowNumber,
                               false);
                   } // foreach (DatabaseRowInfo...
               }
               else if (type == PathType.Row)
               {
                   // In this case the user has directly specified a row, hence
                   // just give that particular row
                   DatabaseRowInfo row = GetRow(tableName, rowNumber);
                   WriteItemObject(row, path + pathSeparator + row.RowNumber,
                               false);
               }
               else
               {
                   // In this case, the path specified is not valid
                   ThrowTerminatingInvalidPathException(path);
               }
           } // else
       }
```

### <a name="implementing-getchildnames"></a>Реализация Жетчилднамес

Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) аналогичен методу [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) , за исключением того, что он возвращает только свойство Name элементов, а не сами элементы.

```csharp
protected override void GetChildNames(string path,
                                     ReturnContainers returnContainers)
       {
           // If the path represented is a drive, then the child items are
           // tables. get the names of all the tables in the drive.
           if (PathIsDrive(path))
           {
               foreach (DatabaseTableInfo table in GetTables())
               {
                   WriteItemObject(table.Name, path, true);
               } // foreach (DatabaseTableInfo...
           } // if (PathIsDrive...
           else
           {
               // Get type, table name and row number from path specified
               string tableName;
               int rowNumber;

               PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

               if (type == PathType.Table)
               {
                   // Get all the rows in the table and then write out the
                   // row numbers.
                   foreach (DatabaseRowInfo row in GetRows(tableName))
                   {
                       WriteItemObject(row.RowNumber, path, false);
                   } // foreach (DatabaseRowInfo...
               }
               else if (type == PathType.Row)
               {
                   // In this case the user has directly specified a row, hence
                   // just give that particular row
                   DatabaseRowInfo row = GetRow(tableName, rowNumber);

                   WriteItemObject(row.RowNumber, path, false);
               }
               else
               {
                   ThrowTerminatingInvalidPathException(path);
               }
           } // else
       }
```

### <a name="implementing-newitem"></a>Реализация NewItem

Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) создает новый элемент указанного типа по указанному пути. Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. невитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.newitemcommand) .

В этом примере метод реализует логику для определения совпадения пути и типа. Это значит, что только таблица может быть создана непосредственно под диском (базой данных), а в таблице может быть создана только строка. Если указанный путь и тип элемента не совпадают таким образом, метод создает исключение.

```csharp
protected override void NewItem(string path, string type,
                                   object newItemValue)
       {
           string tableName;
           int rowNumber;

           PathType pt = GetNamesFromPath(path, out tableName, out rowNumber);

           if (pt == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           // Check if type is either "table" or "row", if not throw an
           // exception
           if (!String.Equals(type, "table", StringComparison.OrdinalIgnoreCase)
               && !String.Equals(type, "row", StringComparison.OrdinalIgnoreCase))
           {
               WriteError(new ErrorRecord
                                 (new ArgumentException("Type must be either a table or row"),
                                     "CannotCreateSpecifiedObject",
                                        ErrorCategory.InvalidArgument,
                                             path
                                  )
                         );

               throw new ArgumentException("This provider can only create items of type \"table\" or \"row\"");
           }

           // Path type is the type of path of the container. So if a drive
           // is specified, then a table can be created under it and if a table
           // is specified, then a row can be created under it. For the sake of
           // completeness, if a row is specified, then if the row specified by
           // the path does not exist, a new row is created. However, the row
           // number may not match as the row numbers only get incremented based
           // on the number of rows

           if (PathIsDrive(path))
           {
               if (String.Equals(type, "table", StringComparison.OrdinalIgnoreCase))
               {
                   // Execute command using ODBC connection to create a table
                   try
                   {
                       // create the table using an sql statement
                       string newTableName = newItemValue.ToString();

                       if (!TableNameIsValid(newTableName))
                       {
                           return;
                       }
                       string sql = "create table " + newTableName
                                            + " (ID INT)";

                       // Create the table using the Odbc connection from the
                       // drive.
                       AccessDBPSDriveInfo di = this.PSDriveInfo as AccessDBPSDriveInfo;

                       if (di == null)
                       {
                           return;
                       }
                       OdbcConnection connection = di.Connection;

                       if (ShouldProcess(newTableName, "create"))
                       {
                           OdbcCommand cmd = new OdbcCommand(sql, connection);
                           cmd.ExecuteScalar();
                       }
                   }
                   catch (Exception ex)
                   {
                       WriteError(new ErrorRecord(ex, "CannotCreateSpecifiedTable",
                                 ErrorCategory.InvalidOperation, path)
                                 );
                   }
               } // if (String...
               else if (String.Equals(type, "row", StringComparison.OrdinalIgnoreCase))
               {
                   throw new
                       ArgumentException("A row cannot be created under a database, specify a path that represents a Table");
               }
           }// if (PathIsDrive...
           else
           {
               if (String.Equals(type, "table", StringComparison.OrdinalIgnoreCase))
               {
                   if (rowNumber < 0)
                   {
                       throw new
                           ArgumentException("A table cannot be created within another table, specify a path that represents a database");
                   }
                   else
                   {
                       throw new
                           ArgumentException("A table cannot be created inside a row, specify a path that represents a database");
                   }
               } //if (String.Equals....
               // if path specified is a row, create a new row
               else if (String.Equals(type, "row", StringComparison.OrdinalIgnoreCase))
               {
                   // The user is required to specify the values to be inserted
                   // into the table in a single string separated by commas
                   string value = newItemValue as string;

                   if (String.IsNullOrEmpty(value))
                   {
                       throw new
                           ArgumentException("Value argument must have comma separated values of each column in a row");
                   }
                   string[] rowValues = value.Split(',');

                   OdbcDataAdapter da = GetAdapterForTable(tableName);

                   if (da == null)
                   {
                       return;
                   }

                   DataSet ds = GetDataSetForTable(da, tableName);
                   DataTable table = GetDataTable(ds, tableName);

                   if (rowValues.Length != table.Columns.Count)
                   {
                       string message =
                            String.Format(CultureInfo.CurrentCulture,
                                            "The table has {0} columns and the value specified must have so many comma separated values",
                                                table.Columns.Count);

                       throw new ArgumentException(message);
                   }

                   if (!Force && (rowNumber >=0 && rowNumber < table.Rows.Count))
                   {
                       string message = String.Format(CultureInfo.CurrentCulture,
                                                        "The row {0} already exists. To create a new row specify row number as {1}, or specify path to a table, or use the -Force parameter",
                                                            rowNumber, table.Rows.Count);

                       throw new ArgumentException(message);
                   }

                   if (rowNumber > table.Rows.Count)
                   {
                       string message = String.Format(CultureInfo.CurrentCulture,
                                            "To create a new row specify row number as {0}, or specify path to a table",
                                                table.Rows.Count);

                       throw new ArgumentException(message);
                   }

                   // Create a new row and update the row with the input
                   // provided by the user
                   DataRow row = table.NewRow();
                   for (int i = 0; i < rowValues.Length; i++)
                   {
                       row[i] = rowValues[i];
                   }
                   table.Rows.Add(row);

                   if (ShouldProcess(tableName, "update rows"))
                   {
                       // Update the table from memory back to the data source
                       da.Update(ds, tableName);
                   }

               }// else if (String...
           }// else ...

       }
```

### <a name="implementing-copyitem"></a>Реализация CopyItem

Объект [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) Копирует указанный элемент по указанному пути. Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. копитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.copyitemcommand) . Этот метод также может быть рекурсивным, копируя все дочерние элементы в дополнение к самому элементу.

Аналогично методу [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) этот метод выполняет логику, чтобы убедиться, что указанный элемент имеет правильный тип пути, в который он копируется. Например, если целевой путь является таблицей, то копируемый элемент должен быть строкой.

```csharp
protected override void CopyItem(string path, string copyPath, bool recurse)
       {
           string tableName, copyTableName;
           int rowNumber, copyRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);
           PathType copyType = GetNamesFromPath(copyPath, out copyTableName, out copyRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(copyPath);
           }

           // Get the table and the table to copy to
           OdbcDataAdapter da = GetAdapterForTable(tableName);
           if (da == null)
           {
               return;
           }

           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           OdbcDataAdapter cda = GetAdapterForTable(copyTableName);
           if (cda == null)
           {
               return;
           }

           DataSet cds = GetDataSetForTable(cda, copyTableName);
           DataTable copyTable = GetDataTable(cds, copyTableName);

           // if source represents a table
           if (type == PathType.Table)
           {
               // if copyPath does not represent a table
               if (copyType != PathType.Table)
               {
                   ArgumentException e = new ArgumentException("Table can only be copied on to another table location");

                   WriteError(new ErrorRecord(e, "PathNotValid",
                       ErrorCategory.InvalidArgument, copyPath));

                   throw e;
               }

               // if table already exists then force parameter should be set
               // to force a copy
               if (!Force && GetTable(copyTableName) != null)
               {
                   throw new ArgumentException("Specified path already exists");
               }

               for (int i = 0; i < table.Rows.Count; i++)
               {
                   DataRow row = table.Rows[i];
                   DataRow copyRow = copyTable.NewRow();

                   copyRow.ItemArray = row.ItemArray;
                   copyTable.Rows.Add(copyRow);
               }
           } // if (type == ...
           // if source represents a row
           else
           {
               if (copyType == PathType.Row)
               {
                   if (!Force && (copyRowNumber < copyTable.Rows.Count))
                   {
                       throw new ArgumentException("Specified path already exists.");
                   }

                   DataRow row = table.Rows[rowNumber];
                   DataRow copyRow = null;

                   if (copyRowNumber < copyTable.Rows.Count)
                   {
                       // copy to an existing row
                       copyRow = copyTable.Rows[copyRowNumber];
                       copyRow.ItemArray = row.ItemArray;
                       copyRow[0] = GetNextID(copyTable);
                   }
                   else if (copyRowNumber == copyTable.Rows.Count)
                   {
                       // copy to the next row in the table that will
                       // be created
                       copyRow = copyTable.NewRow();
                       copyRow.ItemArray = row.ItemArray;
                       copyRow[0] = GetNextID(copyTable);
                       copyTable.Rows.Add(copyRow);
                   }
                   else
                   {
                       // attempting to copy to a nonexistent row or a row
                       // that cannot be created now - throw an exception
                       string message = String.Format(CultureInfo.CurrentCulture,
                                             "The item cannot be specified to the copied row. Specify row number as {0}, or specify a path to the table.",
                                                    table.Rows.Count);

                       throw new ArgumentException(message);
                   }
               }
               else
               {
                   // destination path specified represents a table,
                   // create a new row and copy the item
                   DataRow copyRow = copyTable.NewRow();
                   copyRow.ItemArray = table.Rows[rowNumber].ItemArray;
                   copyRow[0] = GetNextID(copyTable);
                   copyTable.Rows.Add(copyRow);
               }
           }

           if (ShouldProcess(copyTableName, "CopyItems"))
           {
               cda.Update(cds, copyTableName);
           }

       } //CopyItem
```

### <a name="implementing-removeitem"></a>Реализация RemoveItem

Метод [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) удаляет элемент по указанному пути. Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. ремовеитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.removeitemcommand) .

```csharp
protected override void RemoveItem(string path, bool recurse)
       {
           string tableName;
           int rowNumber = 0;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               // if recurse flag has been specified, delete all the rows as well
               if (recurse)
               {
                   OdbcDataAdapter da = GetAdapterForTable(tableName);
                   if (da == null)
                   {
                       return;
                   }

                   DataSet ds = GetDataSetForTable(da, tableName);
                   DataTable table = GetDataTable(ds, tableName);

                   for (int i = 0; i < table.Rows.Count; i++)
                   {
                       table.Rows[i].Delete();
                   }

                   if (ShouldProcess(path, "RemoveItem"))
                   {
                       da.Update(ds, tableName);
                       RemoveTable(tableName);
                   }
               }//if (recurse...
               else
               {
                   // Remove the table
                   if (ShouldProcess(path, "RemoveItem"))
                   {
                       RemoveTable(tableName);
                   }
               }
           }
           else if (type == PathType.Row)
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               table.Rows[rowNumber].Delete();

               if (ShouldProcess(path, "RemoveItem"))
               {
                   da.Update(ds, tableName);
               }
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

## <a name="next-steps"></a>Дальнейшие действия

Обычный поставщик реального мира способен перемещать элементы из одного пути в другой на диске.
Пример поставщика, поддерживающего перемещение элементов, см. в разделе [написание поставщика навигации](./writing-a-navigation-provider.md).

## <a name="see-also"></a>См. также:

[Написание поставщика навигации](./writing-a-navigation-provider.md)

[Общие сведения о поставщиках Windows PowerShell](./windows-powershell-provider-overview.md)
