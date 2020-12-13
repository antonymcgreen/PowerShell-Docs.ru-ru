---
ms.date: 09/13/2016
ms.topic: reference
title: Как написать бинарный модуль PowerShell
description: Как написать бинарный модуль PowerShell
ms.openlocfilehash: 1d5cea474ac418f78cc782360b7c23b7614d6669
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663072"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="928d0-103">Как написать бинарный модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="928d0-103">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="928d0-104">Двоичным модулем может быть любая сборка (. dll), содержащая классы командлетов.</span><span class="sxs-lookup"><span data-stu-id="928d0-104">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="928d0-105">По умолчанию все командлеты в сборке импортируются при импорте двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="928d0-105">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="928d0-106">Тем не менее можно ограничить импортируемые командлеты, создав манифест модуля, корневым модулем которого является сборка.</span><span class="sxs-lookup"><span data-stu-id="928d0-106">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="928d0-107">(Например, ключ CmdletsToExport манифеста можно использовать для экспорта только необходимых командлетов.) Кроме того, двоичный модуль может содержать дополнительные файлы, структуру каталогов и другие элементы полезных данных управления, которые не могут быть доступны для одного командлета.</span><span class="sxs-lookup"><span data-stu-id="928d0-107">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="928d0-108">В следующей процедуре описывается создание и установка двоичного модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="928d0-108">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="928d0-109">Создание и установка двоичного модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="928d0-109">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="928d0-110">Создайте двоичное решение PowerShell (например, командлет, написанное на языке C#) с необходимыми возможностями и убедитесь, что оно работает правильно.</span><span class="sxs-lookup"><span data-stu-id="928d0-110">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="928d0-111">С точки зрения кода ядро двоичного модуля — это просто сборка командлета.</span><span class="sxs-lookup"><span data-stu-id="928d0-111">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="928d0-112">Фактически, PowerShell будет рассматривать одну сборку командлетов в качестве модуля с точки зрения загрузки и выгрузки без каких-либо дополнительных усилий в части разработчика.</span><span class="sxs-lookup"><span data-stu-id="928d0-112">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="928d0-113">Дополнительные сведения о написании командлета см. [в разделе Написание командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="928d0-113">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="928d0-114">При необходимости создайте остальную часть вашего решения: (Дополнительные командлеты, XML-файлы и т. д.) и опишите их с помощью манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="928d0-114">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="928d0-115">Помимо описания сборок командлетов в решении, манифест модуля может описывать, как вы хотите экспортировать и импортировать модуль, какие командлеты будут предоставлены и какие дополнительные файлы будут помещены в модуль.</span><span class="sxs-lookup"><span data-stu-id="928d0-115">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="928d0-116">Как уже отмечалось ранее, PowerShell может обрабатывать бинарный командлет, например модуль, без дополнительных усилий.</span><span class="sxs-lookup"><span data-stu-id="928d0-116">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="928d0-117">Таким образом, манифест модуля полезен в основном для объединения нескольких файлов в один пакет или для явного управления публикацией для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="928d0-117">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="928d0-118">Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="928d0-118">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="928d0-119">Следующий код является чрезвычайно простым блоком кода C#, который содержит три командлета в одном файле, который можно использовать в качестве модуля.</span><span class="sxs-lookup"><span data-stu-id="928d0-119">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

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

3. <span data-ttu-id="928d0-120">Упакуйте решение и сохраните пакет в другом месте в пути модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="928d0-120">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="928d0-121">`PSModulePath`Глобальная переменная среды описывает пути по умолчанию, которые PowerShell будет использовать для поиска вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="928d0-121">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="928d0-122">Например, общий путь для сохранения модуля в системе — `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` .</span><span class="sxs-lookup"><span data-stu-id="928d0-122">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="928d0-123">Если вы не используете пути по умолчанию, необходимо явно указать расположение модуля во время установки.</span><span class="sxs-lookup"><span data-stu-id="928d0-123">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="928d0-124">Не забудьте создать папку для сохранения модуля в, так как может потребоваться папка для хранения нескольких сборок и файлов для решения.</span><span class="sxs-lookup"><span data-stu-id="928d0-124">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="928d0-125">Обратите внимание, что технически вам не нужно устанавливать модуль в любом месте `PSModulePath` — это просто расположения по умолчанию, которые PowerShell будет искать в вашем модуле.</span><span class="sxs-lookup"><span data-stu-id="928d0-125">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="928d0-126">Однако рекомендуется использовать это решение, если нет веских причин для хранения модуля в другом месте.</span><span class="sxs-lookup"><span data-stu-id="928d0-126">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="928d0-127">Дополнительные сведения см. в статьях [Установка модуля PowerShell](./installing-a-powershell-module.md) и [изменение пути установки модуля PowerShell](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="928d0-127">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="928d0-128">Импортируйте модуль в PowerShell с помощью вызова [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="928d0-128">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="928d0-129">Вызов командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) приведет к загрузке модуля в активную память.</span><span class="sxs-lookup"><span data-stu-id="928d0-129">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="928d0-130">Если вы используете PowerShell 3,0 и более поздней версии, просто вызвав имя модуля в коде, вы также импортируете его. Дополнительные сведения см. [в разделе Импорт модуля PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="928d0-130">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="928d0-131">Импорт сборок оснастки в виде модулей</span><span class="sxs-lookup"><span data-stu-id="928d0-131">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="928d0-132">Командлеты и поставщики, существующие в сборках оснастки, можно загрузить как двоичные модули.</span><span class="sxs-lookup"><span data-stu-id="928d0-132">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="928d0-133">Когда сборки оснастки загружаются в виде двоичных модулей, командлеты и поставщики в оснастке доступны пользователю, но класс оснастки в сборке игнорируется, а оснастка не зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="928d0-133">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="928d0-134">В результате командлеты оснастки, предоставляемые Windows PowerShell, не могут обнаружить оснастку, даже если для сеанса доступны командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="928d0-134">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="928d0-135">Кроме того, любые файлы форматирования или типы, на которые ссылается оснастка, не могут быть импортированы как часть двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="928d0-135">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="928d0-136">Чтобы импортировать файлы форматирования и типы, необходимо создать манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="928d0-136">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="928d0-137">См. раздел Создание [манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="928d0-137">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="928d0-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="928d0-138">See Also</span></span>

[<span data-ttu-id="928d0-139">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="928d0-139">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
