---
ms.date: 09/13/2016
ms.topic: reference
title: Написание поставщика навигации
description: Написание поставщика навигации
ms.openlocfilehash: 3123672d3365c97714557bd0e72a6e444ac228a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355227"
---
# <a name="writing-a-navigation-provider"></a><span data-ttu-id="61a05-103">Написание поставщика навигации</span><span class="sxs-lookup"><span data-stu-id="61a05-103">Writing a navigation provider</span></span>

<span data-ttu-id="61a05-104">В этом разделе описывается реализация методов поставщика Windows PowerShell, поддерживающего вложенные контейнеры (многоуровневые хранилища данных), перемещения элементов и относительных путей.</span><span class="sxs-lookup"><span data-stu-id="61a05-104">This topic describes how to implement the methods of a Windows PowerShell provider that support nested containers (multi-level data stores), moving items, and relative paths.</span></span> <span data-ttu-id="61a05-105">Поставщик навигации должен быть производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="61a05-105">A navigation provider must derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="61a05-106">Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="61a05-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="61a05-107">Существует несколько вспомогательных методов и классов, используемых для взаимодействия с базой данных.</span><span class="sxs-lookup"><span data-stu-id="61a05-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="61a05-108">Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="61a05-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>

<span data-ttu-id="61a05-109">Дополнительные сведения о поставщиках Windows PowerShell см. в статье [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61a05-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-navigation-methods"></a><span data-ttu-id="61a05-110">Реализация методов навигации</span><span class="sxs-lookup"><span data-stu-id="61a05-110">Implementing navigation methods</span></span>

<span data-ttu-id="61a05-111">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) реализует методы, поддерживающие вложенные контейнеры, относительные пути и перемещение элементов.</span><span class="sxs-lookup"><span data-stu-id="61a05-111">The [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class implements methods that support nested containers, relative paths, and moving items.</span></span> <span data-ttu-id="61a05-112">Полный список этих методов см. в разделе [методы NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span><span class="sxs-lookup"><span data-stu-id="61a05-112">For a complete list of these methods, see [NavigationCmdletProvider Methods](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span></span>

> [!NOTE]
> <span data-ttu-id="61a05-113">В этом разделе содержатся сведения в [кратком руководстве поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="61a05-113">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="61a05-114">В этом разделе не рассматриваются основные сведения о настройке проекта поставщика или реализации методов, унаследованных от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) , который создает и удаляет диски.</span><span class="sxs-lookup"><span data-stu-id="61a05-114">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="61a05-115">В этом разделе также не рассматривается реализация методов, предоставляемых классами [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) или [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="61a05-115">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) or [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) classes.</span></span> <span data-ttu-id="61a05-116">Пример реализации командлетов элементов см. в разделе [написание поставщика элементов](./writing-an-item-provider.md).</span><span class="sxs-lookup"><span data-stu-id="61a05-116">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span> <span data-ttu-id="61a05-117">Пример реализации командлетов контейнеров см. в разделе [написание поставщика контейнера](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="61a05-117">For an example that shows how to implement container cmdlets, see [Writing a container provider](./writing-a-container-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="61a05-118">Объявление класса поставщика</span><span class="sxs-lookup"><span data-stu-id="61a05-118">Declaring the provider class</span></span>

<span data-ttu-id="61a05-119">Объявите поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) , и добавьте его в класс [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="61a05-119">Declare the provider to derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a><span data-ttu-id="61a05-120">Реализация Иситемконтаинер</span><span class="sxs-lookup"><span data-stu-id="61a05-120">Implementing IsItemContainer</span></span>

<span data-ttu-id="61a05-121">Метод [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) проверяет, является ли элемент по указанному пути контейнером.</span><span class="sxs-lookup"><span data-stu-id="61a05-121">The [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method checks whether the item at the specified path is a container.</span></span>

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

### <a name="implementing-getchildname"></a><span data-ttu-id="61a05-122">Реализация Жетчилднаме</span><span class="sxs-lookup"><span data-stu-id="61a05-122">Implementing GetChildName</span></span>

<span data-ttu-id="61a05-123">Метод [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) получает свойство Name дочернего элемента по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="61a05-123">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method gets the name property of the child item at the specified path.</span></span> <span data-ttu-id="61a05-124">Если элемент по указанному пути не является дочерним по отношению к контейнеру, этот метод должен возвращать путь.</span><span class="sxs-lookup"><span data-stu-id="61a05-124">If the item at the specified path is not a child of a container, then this method should return the path.</span></span>

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

### <a name="implementing-getparentpath"></a><span data-ttu-id="61a05-125">Реализация Жетпарентпас</span><span class="sxs-lookup"><span data-stu-id="61a05-125">Implementing GetParentPath</span></span>

<span data-ttu-id="61a05-126">Метод [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) Возвращает путь родителя элемента по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="61a05-126">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method gets the path of the parent of the item at the specified path.</span></span> <span data-ttu-id="61a05-127">Если элемент по указанному пути является корнем хранилища данных (поэтому он не имеет родителя), этот метод должен возвращать корневой путь.</span><span class="sxs-lookup"><span data-stu-id="61a05-127">If the item at the specified path is the root of the data store (so it has no parent), then this method should return the root path.</span></span>

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

### <a name="implementing-makepath"></a><span data-ttu-id="61a05-128">Реализация Макепас</span><span class="sxs-lookup"><span data-stu-id="61a05-128">Implementing MakePath</span></span>

<span data-ttu-id="61a05-129">Метод [System. Management. Automation. Provider. Navigationcmdletprovider. макепас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) соединяет указанный родительский путь и указанный дочерний путь для создания внутреннего пути поставщика (сведения о типах путей, поддерживаемых поставщиками, см. в [обзоре поставщика Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61a05-129">The [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method joins a specified parent path and a specified child path to create a provider-internal path (for information about path types that providers can support, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="61a05-130">Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. жоинпаскомманд](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) .</span><span class="sxs-lookup"><span data-stu-id="61a05-130">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) cmdlet.</span></span>

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

### <a name="implementing-normalizerelativepath"></a><span data-ttu-id="61a05-131">Реализация Нормализерелативепас</span><span class="sxs-lookup"><span data-stu-id="61a05-131">Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="61a05-132">Метод [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) принимает `path` Параметры и `basepath` и Возвращает нормализованный путь, эквивалентный `path` параметру и относящийся к `basepath` параметру.</span><span class="sxs-lookup"><span data-stu-id="61a05-132">The [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method takes `path` and `basepath` parameters, and returns a normalized path that is equivalent to the `path` parameter and relative to the `basepath` parameter.</span></span>

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

### <a name="implementing-moveitem"></a><span data-ttu-id="61a05-133">Реализация Мовеитем</span><span class="sxs-lookup"><span data-stu-id="61a05-133">Implementing MoveItem</span></span>

<span data-ttu-id="61a05-134">Метод [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) перемещает элемент по указанному пути к указанному пути назначения.</span><span class="sxs-lookup"><span data-stu-id="61a05-134">The [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method moves an item from the specified path to the specified destination path.</span></span> <span data-ttu-id="61a05-135">Обработчик PowerShell вызывает этот метод, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. мовеитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) .</span><span class="sxs-lookup"><span data-stu-id="61a05-135">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) cmdlet.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="61a05-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="61a05-136">See Also</span></span>

[<span data-ttu-id="61a05-137">Написание поставщика контейнера</span><span class="sxs-lookup"><span data-stu-id="61a05-137">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="61a05-138">Общие сведения о поставщиках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61a05-138">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
