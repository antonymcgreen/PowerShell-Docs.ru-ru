---
title: Создание поставщика навигации | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2fd27314a2b8547a15dd1bb72aa8f970d40b18cc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786787"
---
# <a name="writing-a-navigation-provider"></a>Написание поставщика навигации

В этом разделе описывается реализация методов поставщика Windows PowerShell, поддерживающего вложенные контейнеры (многоуровневые хранилища данных), перемещения элементов и относительных путей. Поставщик навигации должен быть производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .

Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных. Существует несколько вспомогательных методов и классов, используемых для взаимодействия с базой данных. Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample05](./accessdbprovidersample05.md).

Дополнительные сведения о поставщиках Windows PowerShell см. в статье [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).

## <a name="implementing-navigation-methods"></a>Реализация методов навигации

Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) реализует методы, поддерживающие вложенные контейнеры, относительные пути и перемещение элементов. Полный список этих методов см. в разделе [методы NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider?view=pscore-6.2.0#methods).

> [!NOTE]
> В этом разделе содержатся сведения в [кратком руководстве поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md). В этом разделе не рассматриваются основные сведения о настройке проекта поставщика или реализации методов, унаследованных от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) , который создает и удаляет диски. В этом разделе также не рассматривается реализация методов, предоставляемых классами [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) или [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) . Пример реализации командлетов элементов см. в разделе [написание поставщика элементов](./writing-an-item-provider.md). Пример реализации командлетов контейнеров см. в разделе [написание поставщика контейнера](./writing-a-container-provider.md).

### <a name="declaring-the-provider-class"></a>Объявление класса поставщика

Объявите поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) , и добавьте его в класс [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a>Реализация Иситемконтаинер

Метод [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) проверяет, является ли элемент по указанному пути контейнером.

```csharp
protected override bool IsItemContainer(string path)
      {
         if (PathIsDrive(path))
         {
             return true;
         }

         string[] pathChunks = ChunkPath(path);
         string tableName;
         int rowNumber;

         PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

         if (type == PathType.Table)
         {
            foreach (DatabaseTableInfo ti in GetTables())
            {
                if (string.Equals(ti.Name, tableName, StringComparison.OrdinalIgnoreCase))
                {
                    return true;
                }
            } // foreach (DatabaseTableInfo...
         } // if (pathChunks...

         return false;
      }
```

### <a name="implementing-getchildname"></a>Реализация Жетчилднаме

Метод [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) получает свойство Name дочернего элемента по указанному пути. Если элемент по указанному пути не является дочерним по отношению к контейнеру, этот метод должен возвращать путь.

```csharp
protected override string GetChildName(string path)
       {
           if (PathIsDrive(path))
           {
               return path;
           }

           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               return tableName;
           }
           else if (type == PathType.Row)
           {
               return rowNumber.ToString(CultureInfo.CurrentCulture);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

           return null;
       }
```

### <a name="implementing-getparentpath"></a>Реализация Жетпарентпас

Метод [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) Возвращает путь родителя элемента по указанному пути. Если элемент по указанному пути является корнем хранилища данных (поэтому он не имеет родителя), этот метод должен возвращать корневой путь.

```csharp
protected override string GetParentPath(string path, string root)
       {
           // If root is specified then the path has to contain
           // the root. If not nothing should be returned
           if (!String.IsNullOrEmpty(root))
           {
               if (!path.Contains(root))
               {
                   return null;
               }
           }

           return path.Substring(0, path.LastIndexOf(pathSeparator, StringComparison.OrdinalIgnoreCase));
       }
```

### <a name="implementing-makepath"></a>Реализация Макепас

Метод [System. Management. Automation. Provider. Navigationcmdletprovider. макепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) соединяет указанный родительский путь и указанный дочерний путь для создания внутреннего пути поставщика (сведения о типах путей, поддерживаемых поставщиками, см. в [обзоре поставщика Windows PowerShell](./windows-powershell-provider-overview.md). Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. жоинпаскомманд](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) .

```csharp
protected override string MakePath(string parent, string child)
       {
           string result;

           string normalParent = NormalizePath(parent);
           normalParent = RemoveDriveFromPath(normalParent);
           string normalChild = NormalizePath(child);
           normalChild = RemoveDriveFromPath(normalChild);

           if (String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               result = String.Empty;
           }
           else if (String.IsNullOrEmpty(normalParent) && !String.IsNullOrEmpty(normalChild))
           {
               result = normalChild;
           }
           else if (!String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               if (normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent;
               }
               else
               {
                   result = normalParent + pathSeparator;
               }
           } // else if (!String...
           else
           {
               if (!normalParent.Equals(String.Empty) &&
                   !normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent + pathSeparator;
               }
               else
               {
                   result = normalParent;
               }

               if (normalChild.StartsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result += normalChild.Substring(1);
               }
               else
               {
                   result += normalChild;
               }
           } // else

           return result;
       }
```

### <a name="implementing-normalizerelativepath"></a>Реализация Нормализерелативепас

Метод [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) принимает `path` Параметры и `basepath` и Возвращает нормализованный путь, эквивалентный `path` параметру и относящийся к `basepath` параметру.

```csharp
protected override string NormalizeRelativePath(string path,
                                                            string basepath)
       {
           // Normalize the paths first
           string normalPath = NormalizePath(path);
           normalPath = RemoveDriveFromPath(normalPath);
           string normalBasePath = NormalizePath(basepath);
           normalBasePath = RemoveDriveFromPath(normalBasePath);

           if (String.IsNullOrEmpty(normalBasePath))
           {
               return normalPath;
           }
           else
           {
               if (!normalPath.Contains(normalBasePath))
               {
                   return null;
               }

               return normalPath.Substring(normalBasePath.Length + pathSeparator.Length);
           }
       }
```

### <a name="implementing-moveitem"></a>Реализация Мовеитем

Метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) перемещает элемент по указанному пути к указанному пути назначения. Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. мовеитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) .

```csharp
protected override void MoveItem(string path, string destination)
       {
           // Get type, table name and rowNumber from the path
           string tableName, destTableName;
           int rowNumber, destRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           PathType destType = GetNamesFromPath(destination, out destTableName,
                                    out destRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (destType == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(destination);
           }

           if (type == PathType.Table)
           {
               ArgumentException e = new ArgumentException("Move not supported for tables");

               WriteError(new ErrorRecord(e, "MoveNotSupported",
                   ErrorCategory.InvalidArgument, path));

               throw e;
           }
           else
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               OdbcDataAdapter dda = GetAdapterForTable(destTableName);
               if (dda == null)
               {
                   return;
               }

               DataSet dds = GetDataSetForTable(dda, destTableName);
               DataTable destTable = GetDataTable(dds, destTableName);
               DataRow row = table.Rows[rowNumber];

               if (destType == PathType.Table)
               {
                   DataRow destRow = destTable.NewRow();

                   destRow.ItemArray = row.ItemArray;
               }
               else
               {
                   DataRow destRow = destTable.Rows[destRowNumber];

                   destRow.ItemArray = row.ItemArray;
               }

               // Update the changes
               if (ShouldProcess(path, "MoveItem"))
               {
                   WriteItemObject(row, path, false);
                   dda.Update(dds, destTableName);
               }
           }
       }
```

## <a name="see-also"></a>См. также

[Написание поставщика контейнера](./writing-a-container-provider.md)

[Общие сведения о поставщиках Windows PowerShell](./windows-powershell-provider-overview.md)
