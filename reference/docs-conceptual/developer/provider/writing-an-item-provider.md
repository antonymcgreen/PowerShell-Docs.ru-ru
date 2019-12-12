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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359883"
---
# <a name="writing-an-item-provider"></a><span data-ttu-id="aba7b-102">Написание поставщика элемента</span><span class="sxs-lookup"><span data-stu-id="aba7b-102">Writing an item provider</span></span>

<span data-ttu-id="aba7b-103">В этом разделе описывается реализация методов поставщика Windows PowerShell, которые обращаются к элементам в хранилище данных и управляют ими.</span><span class="sxs-lookup"><span data-stu-id="aba7b-103">This topic describes how to implement the methods of a Windows PowerShell provider that access and manipulate items in the data store.</span></span> <span data-ttu-id="aba7b-104">Чтобы иметь возможность доступа к элементам, поставщик должен быть производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="aba7b-104">To be able to access items, a provider must derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

<span data-ttu-id="aba7b-105">Поставщик в примерах в этом разделе использует базу данных Access в качестве хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="aba7b-105">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="aba7b-106">Существует несколько вспомогательных методов и классов, используемых для взаимодействия с базой данных.</span><span class="sxs-lookup"><span data-stu-id="aba7b-106">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="aba7b-107">Полный пример, включающий вспомогательные методы, см. в разделе [AccessDBProviderSample03](./accessdbprovidersample03.md)</span><span class="sxs-lookup"><span data-stu-id="aba7b-107">For the complete sample that includes the helper methods, see [AccessDBProviderSample03](./accessdbprovidersample03.md)</span></span>

<span data-ttu-id="aba7b-108">Дополнительные сведения о поставщиках Windows PowerShell см. в статье [Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aba7b-108">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-item-methods"></a><span data-ttu-id="aba7b-109">Реализация методов элементов</span><span class="sxs-lookup"><span data-stu-id="aba7b-109">Implementing item methods</span></span>

<span data-ttu-id="aba7b-110">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) предоставляет несколько методов, которые можно использовать для доступа к элементам в хранилище данных и управления ими.</span><span class="sxs-lookup"><span data-stu-id="aba7b-110">The [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class exposes several methods that can be used to access and manipulate the items in a data store.</span></span> <span data-ttu-id="aba7b-111">Полный список этих методов см. в разделе [методы итемкмдлетпровидер](/dotnet/api/system.management.automation.provider.itemcmdletprovider?view=pscore-6.2.0#methods).</span><span class="sxs-lookup"><span data-stu-id="aba7b-111">For a complete list of these methods, see [ItemCmdletProvider Methods](/dotnet/api/system.management.automation.provider.itemcmdletprovider?view=pscore-6.2.0#methods).</span></span> <span data-ttu-id="aba7b-112">В этом примере мы реализуем четыре из этих методов.</span><span class="sxs-lookup"><span data-stu-id="aba7b-112">In this example, we will implement four of these methods.</span></span> <span data-ttu-id="aba7b-113">[System. Management. Automation. Provider. итемкмдлетпровидер. DataItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) получает элемент по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="aba7b-113">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) gets an item at a specified path.</span></span> <span data-ttu-id="aba7b-114">[System. Management. Automation. Provider. итемкмдлетпровидер. сетитем \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) задает значение указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="aba7b-114">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) sets the value of the specified item.</span></span> <span data-ttu-id="aba7b-115">[System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) проверяет, существует ли элемент по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="aba7b-115">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) checks whether an item exists at the specified path.</span></span> <span data-ttu-id="aba7b-116">[System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) проверяет путь, сопоставляемый с расположением в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="aba7b-116">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) checks a path to see if it maps to a location in the data store.</span></span>

> [!NOTE]
> <span data-ttu-id="aba7b-117">В этом разделе содержатся сведения в [кратком руководстве поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="aba7b-117">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="aba7b-118">В этом разделе не рассматриваются основные сведения о настройке проекта поставщика или реализации методов, унаследованных от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) , который создает и удаляет диски.</span><span class="sxs-lookup"><span data-stu-id="aba7b-118">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="aba7b-119">Объявление класса поставщика</span><span class="sxs-lookup"><span data-stu-id="aba7b-119">Declaring the provider class</span></span>

<span data-ttu-id="aba7b-120">Объявите поставщика, производного от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) , и добавьте его в класс [System. Management. Automation. Provider. кмдлетпровидераттрибуте](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="aba7b-120">Declare the provider to derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a><span data-ttu-id="aba7b-121">Реализация элемента Item</span><span class="sxs-lookup"><span data-stu-id="aba7b-121">Implementing GetItem</span></span>

<span data-ttu-id="aba7b-122">Метод [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) вызывается подсистемой PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. жетитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) для вашего поставщика.</span><span class="sxs-lookup"><span data-stu-id="aba7b-122">The [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) cmdlet on your provider.</span></span> <span data-ttu-id="aba7b-123">Метод возвращает элемент по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="aba7b-123">The method returns the item at the specified path.</span></span> <span data-ttu-id="aba7b-124">В примере базы данных Access метод проверяет, является ли элемент самим диском, таблицей в базе данных или строкой в базе данных.</span><span class="sxs-lookup"><span data-stu-id="aba7b-124">In the Access database example, the method checks whether the item is the drive itself, a table in the database, or a row in the database.</span></span> <span data-ttu-id="aba7b-125">Метод отправляет элемент в подсистему PowerShell, вызывая метод [System. Management. автоматизации. Provider. кмдлетпровидер. вритеитемобжект \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) .</span><span class="sxs-lookup"><span data-stu-id="aba7b-125">The method sends the item to the PowerShell engine by calling the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

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

### <a name="implementing-setitem"></a><span data-ttu-id="aba7b-126">Реализация Сетитем</span><span class="sxs-lookup"><span data-stu-id="aba7b-126">Implementing SetItem</span></span>

<span data-ttu-id="aba7b-127">Метод [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) вызывается обработчиком PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. сетитемкомманд](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) .</span><span class="sxs-lookup"><span data-stu-id="aba7b-127">The [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method is called by the PowerShell engine calls when a user calls the [Microsoft.PowerShell.Commands.SetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) cmdlet.</span></span> <span data-ttu-id="aba7b-128">Он задает значение элемента по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="aba7b-128">It sets the value of the item at the specified path.</span></span>

<span data-ttu-id="aba7b-129">В примере базы данных Access имеет смысл установить значение элемента только в том случае, если этот элемент является строкой, поэтому метод создает исключение [NotSupportedException](/dotnet/api/system.notsupportedexception?view=netframework-4.8) , если элемент не является строкой.</span><span class="sxs-lookup"><span data-stu-id="aba7b-129">In the Access database example, it makes sense to set the value of an item only if that item is a row, so the method throws [NotSupportedException](/dotnet/api/system.notsupportedexception?view=netframework-4.8) when the item is not a row.</span></span>

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

### <a name="implementing-itemexists"></a><span data-ttu-id="aba7b-130">Реализация Итемексистс</span><span class="sxs-lookup"><span data-stu-id="aba7b-130">Implementing ItemExists</span></span>

<span data-ttu-id="aba7b-131">Метод [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) вызывается подсистемой PowerShell, когда пользователь вызывает командлет [Microsoft. PowerShell. Commands. тестпаскомманд](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) .</span><span class="sxs-lookup"><span data-stu-id="aba7b-131">The [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) cmdlet.</span></span> <span data-ttu-id="aba7b-132">Метод определяет, существует ли элемент по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="aba7b-132">The method determines whether there is an item at the specified path.</span></span> <span data-ttu-id="aba7b-133">Если элемент существует, метод передает его в подсистему PowerShell, вызывая [System. Management. Automation. Provider. кмдлетпровидер. вритеитемобжект \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span><span class="sxs-lookup"><span data-stu-id="aba7b-133">If the item does exist, the method passes it back to the PowerShell engine by calling [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span></span>

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

### <a name="implementing-isvalidpath"></a><span data-ttu-id="aba7b-134">Реализация Исвалидпас</span><span class="sxs-lookup"><span data-stu-id="aba7b-134">Implementing IsValidPath</span></span>

<span data-ttu-id="aba7b-135">Метод [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) проверяет, является ли указанный путь синтаксически допустимым для текущего поставщика.</span><span class="sxs-lookup"><span data-stu-id="aba7b-135">The [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method checks whether the specified path is syntactically valid for the current provider.</span></span> <span data-ttu-id="aba7b-136">Он не проверяет, существует ли элемент по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="aba7b-136">It does not check whether an item exists at the path.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="aba7b-137">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="aba7b-137">Next steps</span></span>

<span data-ttu-id="aba7b-138">Обычный поставщик в реальном времени может поддерживать элементы, содержащие другие элементы, и перемещать элементы из одного пути в другой на диске.</span><span class="sxs-lookup"><span data-stu-id="aba7b-138">A typical real-world provider is capable of supporting items that contain other items, and of moving items from one path to another within the drive.</span></span> <span data-ttu-id="aba7b-139">Пример поставщика, который поддерживает контейнеры, см. [в разделе Написание поставщика контейнера](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="aba7b-139">For an example of a provider that supports containers, see [Writing a container provider](./writing-a-container-provider.md).</span></span> <span data-ttu-id="aba7b-140">Пример поставщика, поддерживающего перемещение элементов, см. в разделе [написание поставщика навигации](./writing-a-navigation-provider.md).</span><span class="sxs-lookup"><span data-stu-id="aba7b-140">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aba7b-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="aba7b-141">See Also</span></span>

[<span data-ttu-id="aba7b-142">Создание поставщика контейнера</span><span class="sxs-lookup"><span data-stu-id="aba7b-142">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="aba7b-143">Создание поставщика навигации</span><span class="sxs-lookup"><span data-stu-id="aba7b-143">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="aba7b-144">Общие сведения о поставщике Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aba7b-144">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
