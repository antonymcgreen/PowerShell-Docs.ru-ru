---
title: Разработка поставщика навигации | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98bcfda0-6ee2-46f5-bbc7-5fab8b780d6a
caps.latest.revision: 5
ms.openlocfilehash: a789b392bddd344ad583c93a1a55302329df9917
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863540"
---
# <a name="writing-a-navigation-provider"></a><span data-ttu-id="d115a-102">Написание поставщика навигации</span><span class="sxs-lookup"><span data-stu-id="d115a-102">Writing a navigation provider</span></span>

<span data-ttu-id="d115a-103">В этом разделе описывается, как реализовать методы поставщика Windows PowerShell, которые поддерживают вложенные контейнеры (многоуровневыми данными магазинов), перемещение элементов и относительные пути.</span><span class="sxs-lookup"><span data-stu-id="d115a-103">This topic describes how to implement the methods of a Windows PowerShell provider that support nested containers (multi-level data stores), moving items, and relative paths.</span></span> <span data-ttu-id="d115a-104">Поставщик навигации должен быть производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="d115a-104">A navigation provider must derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="d115a-105">Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="d115a-105">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="d115a-106">Существует несколько вспомогательные методы и классы, используемые для взаимодействия с базой данных.</span><span class="sxs-lookup"><span data-stu-id="d115a-106">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="d115a-107">Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="d115a-107">For the complete sample that includes the helper methods, see [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>

<span data-ttu-id="d115a-108">Дополнительные сведения о поставщиках Windows PowerShell см. в разделе [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d115a-108">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-navigation-methods"></a><span data-ttu-id="d115a-109">Реализация методов навигации</span><span class="sxs-lookup"><span data-stu-id="d115a-109">Implementing navigation methods</span></span>

<span data-ttu-id="d115a-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс реализует методы, которые поддерживают вложенные контейнеры, относительные пути и перемещение элементов.</span><span class="sxs-lookup"><span data-stu-id="d115a-110">The [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class implements methods that support nested containers, relative paths, and moving items.</span></span> <span data-ttu-id="d115a-111">Полный список этих методов, см. в разделе [NavigationCmdletProvider методы](http://msdn.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider_methods\(v=vs.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d115a-111">For a complete list of these methods, see [NavigationCmdletProvider Methods](http://msdn.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider_methods\(v=vs.85\).aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="d115a-112">Материал данной статьи основан на информации из [QuickStart поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="d115a-112">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="d115a-113">В этом разделе рассматриваются базовые сведения о настройке проекта поставщика, или как реализовать методы унаследована от [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) класс, создавать и удалять диски.</span><span class="sxs-lookup"><span data-stu-id="d115a-113">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="d115a-114">В этом разделе также рассматривается способ реализации методов, предоставляемых [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) или [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) классы.</span><span class="sxs-lookup"><span data-stu-id="d115a-114">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) or [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) classes.</span></span> <span data-ttu-id="d115a-115">Пример, демонстрирующий способы реализации командлетов item, см. в разделе [Создание поставщика элемента](./writing-an-item-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d115a-115">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span> <span data-ttu-id="d115a-116">Пример, демонстрирующий способы реализации командлетов контейнера, см. в разделе [разработка поставщика контейнера](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d115a-116">For an example that shows how to implement container cmdlets, see [Writing a container provider](./writing-a-container-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="d115a-117">Объявление класса поставщика</span><span class="sxs-lookup"><span data-stu-id="d115a-117">Declaring the provider class</span></span>

<span data-ttu-id="d115a-118">Объявите поставщику о необходимости получения из [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса и установить для него с помощью [System.Management.Automation.Provider.Cmdletproviderattribute ](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="d115a-118">Declare the provider to derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a><span data-ttu-id="d115a-119">Реализация IsItemContainer</span><span class="sxs-lookup"><span data-stu-id="d115a-119">Implementing IsItemContainer</span></span>

<span data-ttu-id="d115a-120">[System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) метод проверяет, является ли элемент по указанному пути контейнера.</span><span class="sxs-lookup"><span data-stu-id="d115a-120">The [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method checks whether the item at the specified path is a container.</span></span>

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

### <a name="implementing-getchildname"></a><span data-ttu-id="d115a-121">Реализация GetChildName</span><span class="sxs-lookup"><span data-stu-id="d115a-121">Implementing GetChildName</span></span>

<span data-ttu-id="d115a-122">[System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) метод получает свойство имени дочернего элемента по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="d115a-122">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method gets the name property of the child item at the specified path.</span></span> <span data-ttu-id="d115a-123">Если элемент по указанному пути, не являющийся потомком контейнера, этот метод должен возвращать путь.</span><span class="sxs-lookup"><span data-stu-id="d115a-123">If the item at the specified path is not a child of a container, then this method should return the path.</span></span>

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

### <a name="implementing-getparentpath"></a><span data-ttu-id="d115a-124">Реализация GetParentPath</span><span class="sxs-lookup"><span data-stu-id="d115a-124">Implementing GetParentPath</span></span>

<span data-ttu-id="d115a-125">[System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) метод получает путь родительского элемента по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="d115a-125">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method gets the path of the parent of the item at the specified path.</span></span> <span data-ttu-id="d115a-126">Если элемент по указанному пути корневого хранилища данных (поэтому он не имеет родительского элемента), этот метод должен возвращать корневой путь.</span><span class="sxs-lookup"><span data-stu-id="d115a-126">If the item at the specified path is the root of the data store (so it has no parent), then this method should return the root path.</span></span>

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

### <a name="implementing-makepath"></a><span data-ttu-id="d115a-127">Реализация MakePath</span><span class="sxs-lookup"><span data-stu-id="d115a-127">Implementing MakePath</span></span>

<span data-ttu-id="d115a-128">[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) метод объединяет указанного родительского пути и пути указанного дочернего элемента для создания поставщика внутреннего пути (для типов сведений о пути, которые Поставщики могут поддерживать, см. в разделе [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d115a-128">The [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method joins a specified parent path and a specified child path to create a provider-internal path (for information about path types that providers can support, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="d115a-129">Подсистема PowerShell вызывает этот метод, когда пользователь вызывает [Microsoft.Powershell.Commands.Join-Path](/dotnet/api/Microsoft.PowerShell.Commands.Join-Path) командлета.</span><span class="sxs-lookup"><span data-stu-id="d115a-129">The PowerShell engine calls this method when a user calls the [Microsoft.Powershell.Commands.Join-Path](/dotnet/api/Microsoft.PowerShell.Commands.Join-Path) cmdlet.</span></span>

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

### <a name="implementing-normalizerelativepath"></a><span data-ttu-id="d115a-130">Реализация NormalizeRelativePath</span><span class="sxs-lookup"><span data-stu-id="d115a-130">Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="d115a-131">[System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) альбома `path` и `basepath` параметры и возвращает нормализованный путь, который эквивалентен `path`параметр и относительно `basepath` параметра.</span><span class="sxs-lookup"><span data-stu-id="d115a-131">The [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method takes `path` and `basepath` parameters, and returns a normalized path that is equivalent to the `path` parameter and relative to the `basepath` parameter.</span></span>

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

### <a name="implementing-moveitem"></a><span data-ttu-id="d115a-132">Реализация MoveItem</span><span class="sxs-lookup"><span data-stu-id="d115a-132">Implementing MoveItem</span></span>

<span data-ttu-id="d115a-133">[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) метод перемещает элемент из указанного пути в указанный целевой путь.</span><span class="sxs-lookup"><span data-stu-id="d115a-133">The [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method moves an item from the specified path to the specified destination path.</span></span> <span data-ttu-id="d115a-134">Подсистема PowerShell вызывает этот метод, когда пользователь вызывает [Microsoft.Powershell.Commands.Move-Item](/dotnet/api/Microsoft.PowerShell.Commands.Move-Item) командлета.</span><span class="sxs-lookup"><span data-stu-id="d115a-134">The PowerShell engine calls this method when a user calls the [Microsoft.Powershell.Commands.Move-Item](/dotnet/api/Microsoft.PowerShell.Commands.Move-Item) cmdlet.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d115a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d115a-135">See Also</span></span>

[<span data-ttu-id="d115a-136">Разработка поставщика контейнера</span><span class="sxs-lookup"><span data-stu-id="d115a-136">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="d115a-137">Общие сведения о поставщике PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="d115a-137">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)