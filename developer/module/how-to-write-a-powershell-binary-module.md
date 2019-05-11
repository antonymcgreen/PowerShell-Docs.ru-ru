---
title: Как написать модуль двоичных файлов PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb4e72e6-24c4-42b6-b7b9-a62585c17f26
caps.latest.revision: 15
ms.openlocfilehash: ed614de125f78cbcf8411cc334baf3c95933dd47
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229335"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="9ca06-102">Как написать бинарный модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca06-102">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="9ca06-103">Двоичный модуль может быть любой сборки (DLL), содержащий классы командлет.</span><span class="sxs-lookup"><span data-stu-id="9ca06-103">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="9ca06-104">По умолчанию все командлеты в сборке импортируются при импорте двоичных модулей.</span><span class="sxs-lookup"><span data-stu-id="9ca06-104">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="9ca06-105">Тем не менее можно ограничить командлеты, которые импортируются путем создания манифеста модуля, корневой модуль которого представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="9ca06-105">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="9ca06-106">(Например, ключ CmdletsToExport манифеста можно использовать для экспорта только нужные командлеты, которые необходимы.) Кроме того двоичный модуль может содержать дополнительные файлы, используя структуру каталогов и другие фрагменты данных полезно управления, что один командлет не может.</span><span class="sxs-lookup"><span data-stu-id="9ca06-106">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="9ca06-107">Следующая процедура описывает создание и установка двоичного модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ca06-107">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="9ca06-108">Как создать и установить двоичного модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca06-108">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="9ca06-109">Создайте двоичный решение PowerShell (таких как командлет, написанных на C#), с возможностями необходима и убедитесь, что он работает правильно.</span><span class="sxs-lookup"><span data-stu-id="9ca06-109">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="9ca06-110">С точки зрения кода двоичный модуль лежит просто сборкой командлет.</span><span class="sxs-lookup"><span data-stu-id="9ca06-110">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="9ca06-111">На самом деле PowerShell будет считать сборку один командлет модуля с точки зрения загрузку и выгрузку с без дополнительных усилий от разработчика.</span><span class="sxs-lookup"><span data-stu-id="9ca06-111">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="9ca06-112">Дополнительные сведения о написании командлета, см. в разделе [написание командлетов Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="9ca06-112">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="9ca06-113">При необходимости создайте остальной части решения: (Дополнительные командлеты, XML-файлы и т. д.) и описание их с помощью манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-113">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="9ca06-114">Кроме описания сборок командлет в решении, манифеста модуля можно описать способ экспорта и импорта модуля, какие командлеты будут доступны и дополнительные файлы будет отправлена в модуль.</span><span class="sxs-lookup"><span data-stu-id="9ca06-114">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="9ca06-115">Как уже говорилось ранее тем не менее, PowerShell может обрабатывать двоичные командлета типа модуля с без дополнительных усилий.</span><span class="sxs-lookup"><span data-stu-id="9ca06-115">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="9ca06-116">Таким образом манифест модуля полезно, главным образом для объединения нескольких файлов в один пакет, или явно управления публикации для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="9ca06-116">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="9ca06-117">Дополнительные сведения см. в разделе [как написание манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="9ca06-117">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="9ca06-118">Ниже приведен предельно простой C# блок кода, содержащий три командлета, в том же файле, который может использоваться в качестве модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-118">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. <span data-ttu-id="9ca06-119">Пакет решения и сохраните пакет в другое место в путь к модулю PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ca06-119">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="9ca06-120">`PSModulePath` Глобальную переменную среды описывает пути по умолчанию, которые будут использовать PowerShell для поиска вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-120">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="9ca06-121">Например, общий путь для сохранения модуля в системе будет `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span><span class="sxs-lookup"><span data-stu-id="9ca06-121">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="9ca06-122">Если вы не используете пути по умолчанию, необходимо явно указать расположение вашего модуля во время установки.</span><span class="sxs-lookup"><span data-stu-id="9ca06-122">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="9ca06-123">Не забудьте создать папку для сохранения вашего модуля, как вам может понадобиться папку для хранения нескольких сборок и файлов для вашего решения.</span><span class="sxs-lookup"><span data-stu-id="9ca06-123">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="9ca06-124">Обратите внимание, что технически не необходимо установить модуль в любом месте на `PSModulePath` -это просто расположения по умолчанию, которые PowerShell будет выглядеть для вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-124">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="9ca06-125">Тем не менее он считается оптимальным образом, чтобы сделать это, если у вас нет веских причин хранить где-то еще модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-125">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="9ca06-126">Дополнительные сведения см. в разделе [Установка модуля PowerShell](./installing-a-powershell-module.md) и [изменении пути установки модуля PowerShell](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="9ca06-126">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="9ca06-127">Импорт модуля PowerShell с помощью вызова [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="9ca06-127">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="9ca06-128">Вызов к [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) загрузит вашего модуля в активной памяти.</span><span class="sxs-lookup"><span data-stu-id="9ca06-128">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="9ca06-129">Если вы используете PowerShell 3.0 и более поздней версии, просто вызвав имя модуля в коде также импортирует. Дополнительные сведения см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="9ca06-129">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="9ca06-130">Импортирование сборок оснастки как модули</span><span class="sxs-lookup"><span data-stu-id="9ca06-130">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="9ca06-131">Командлеты и поставщики, которые существуют в сборках оснастки можно загрузить как двоичные модули.</span><span class="sxs-lookup"><span data-stu-id="9ca06-131">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="9ca06-132">При оснастки сборки загружаются как двоичные модули, командлеты и поставщики в оснастке доступны пользователю, но класс оснастки в сборке пропускается и оснастки не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="9ca06-132">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="9ca06-133">Таким образом командлеты оснастки, предоставляемые Windows PowerShell не может обнаружить оснастки, несмотря на то, что командлеты и поставщики, доступные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="9ca06-133">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="9ca06-134">Кроме того нельзя импортировать файлы форматирования или типы, на которые ссылается эта оснастка в рамках двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-134">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="9ca06-135">Чтобы импортировать файлы форматирования и типов необходимо создать манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="9ca06-135">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="9ca06-136">См. в разделе, [способах создания манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="9ca06-136">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ca06-137">См. также</span><span class="sxs-lookup"><span data-stu-id="9ca06-137">See Also</span></span>

[<span data-ttu-id="9ca06-138">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca06-138">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
