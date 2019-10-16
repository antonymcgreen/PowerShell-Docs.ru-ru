---
title: Создание поставщика элементов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 606c880c-6cf1-4ea6-8730-dbf137bfabff
caps.latest.revision: 5
ms.openlocfilehash: 12d2cb8c40c9fd6278bb964a6259d03167536195
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359883"
---
# <a name="writing-an-item-provider"></a>Написание поставщика элемента

В этом разделе описывается реализация методов поставщика Windows PowerShell, которые обращаются к элементам в хранилище данных и управляют ими. Чтобы иметь возможность доступа к элементам, поставщик должен быть производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .

Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных. Существует несколько вспомогательных методов и классов, используемых для взаимодействия с базой данных. Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample03](./accessdbprovidersample03.md)

Дополнительные сведения о поставщиках Windows PowerShell см. в статье [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).

## <a name="implementing-item-methods"></a>Реализация методов элементов

Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) предоставляет несколько методов, которые можно использовать для доступа к элементам в хранилище данных и управления ими. Полный список этих методов см. в разделе [методы итемкмдлетпровидер](/dotnet/api/system.management.automation.provider.itemcmdletprovider?view=pscore-6.2.0#methods). В этом примере мы реализуем четыре из этих методов. [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) получает элемент по указанному пути. [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) задает значение указанного элемента. [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) проверяет, существует ли элемент по указанному пути. [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) проверяет путь, сопоставляемый с расположением в хранилище данных.

> [!NOTE]
> В этом разделе содержатся сведения в [кратком руководстве поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md). В этом разделе не рассматриваются основные сведения о настройке проекта поставщика или реализации методов, унаследованных от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) , который создает и удаляет диски.

### <a name="declaring-the-provider-class"></a>Объявление класса поставщика

Объявите поставщика, производного от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) , и добавьте его в класс [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a>Реализация элемента Item

Метод [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) вызывается подсистемой PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. жетитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) для вашего поставщика. Метод возвращает элемент по указанному пути. В примере базы данных Access метод проверяет, является ли элемент самим диском, таблицей в базе данных или строкой в базе данных. Метод отправляет элемент в подсистему PowerShell, вызывая метод [System. Management. автоматизации. Provider. кмдлетпровидер. вритеитемобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .

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

### <a name="implementing-setitem"></a>Реализация Сетитем

Метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) вызывается обработчиком PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. сетитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) . Он задает значение элемента по указанному пути.

В примере базы данных Access имеет смысл установить значение элемента только в том случае, если этот элемент является строкой, поэтому метод создает исключение [NotSupportedException](/dotnet/api/system.notsupportedexception?view=netframework-4.8) , если элемент не является строкой.

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

### <a name="implementing-itemexists"></a>Реализация Итемексистс

Метод [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) вызывается подсистемой PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. тестпаскомманд](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) . Метод определяет, существует ли элемент по указанному пути. Если элемент существует, метод передает его в подсистему PowerShell, вызывая [System. Management. Automation. Provider. кмдлетпровидер. вритеитемобжект *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).

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

### <a name="implementing-isvalidpath"></a>Реализация Исвалидпас

Метод [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) проверяет, является ли указанный путь синтаксически допустимым для текущего поставщика. Он не проверяет, существует ли элемент по указанному пути.

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

Обычный поставщик в реальном времени может поддерживать элементы, содержащие другие элементы, и перемещать элементы из одного пути в другой на диске. Пример поставщика, который поддерживает контейнеры, см. [в разделе Написание поставщика контейнера](./writing-a-container-provider.md). Пример поставщика, поддерживающего перемещение элементов, см. в разделе [написание поставщика навигации](./writing-a-navigation-provider.md).

## <a name="see-also"></a>См. также:

[Создание поставщика контейнера](./writing-a-container-provider.md)

[Создание поставщика навигации](./writing-a-navigation-provider.md)

[Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md)
