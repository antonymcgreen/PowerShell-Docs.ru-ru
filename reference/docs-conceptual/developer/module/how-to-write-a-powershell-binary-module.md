---
title: Написание двоичного модуля PowerShell | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 92395bd6b8be1bd3741888eb3716d62f0253e213
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779273"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="d6255-102">Как написать бинарный модуль PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6255-102">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="d6255-103">Двоичным модулем может быть любая сборка (. dll), содержащая классы командлетов.</span><span class="sxs-lookup"><span data-stu-id="d6255-103">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="d6255-104">По умолчанию все командлеты в сборке импортируются при импорте двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="d6255-104">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="d6255-105">Тем не менее можно ограничить импортируемые командлеты, создав манифест модуля, корневым модулем которого является сборка.</span><span class="sxs-lookup"><span data-stu-id="d6255-105">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="d6255-106">(Например, ключ CmdletsToExport манифеста можно использовать для экспорта только необходимых командлетов.) Кроме того, двоичный модуль может содержать дополнительные файлы, структуру каталогов и другие элементы полезных данных управления, которые не могут быть доступны для одного командлета.</span><span class="sxs-lookup"><span data-stu-id="d6255-106">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="d6255-107">В следующей процедуре описывается создание и установка двоичного модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6255-107">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="d6255-108">Создание и установка двоичного модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6255-108">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="d6255-109">Создайте двоичное решение PowerShell (например, командлет, написанное на языке C#) с необходимыми возможностями и убедитесь, что оно работает правильно.</span><span class="sxs-lookup"><span data-stu-id="d6255-109">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="d6255-110">С точки зрения кода ядро двоичного модуля — это просто сборка командлета.</span><span class="sxs-lookup"><span data-stu-id="d6255-110">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="d6255-111">Фактически, PowerShell будет рассматривать одну сборку командлетов в качестве модуля с точки зрения загрузки и выгрузки без каких-либо дополнительных усилий в части разработчика.</span><span class="sxs-lookup"><span data-stu-id="d6255-111">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="d6255-112">Дополнительные сведения о написании командлета см. [в разделе Написание командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="d6255-112">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="d6255-113">При необходимости создайте остальную часть вашего решения: (Дополнительные командлеты, XML-файлы и т. д.) и опишите их с помощью манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="d6255-113">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="d6255-114">Помимо описания сборок командлетов в решении, манифест модуля может описывать, как вы хотите экспортировать и импортировать модуль, какие командлеты будут предоставлены и какие дополнительные файлы будут помещены в модуль.</span><span class="sxs-lookup"><span data-stu-id="d6255-114">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="d6255-115">Как уже отмечалось ранее, PowerShell может обрабатывать бинарный командлет, например модуль, без дополнительных усилий.</span><span class="sxs-lookup"><span data-stu-id="d6255-115">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="d6255-116">Таким образом, манифест модуля полезен в основном для объединения нескольких файлов в один пакет или для явного управления публикацией для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="d6255-116">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="d6255-117">Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="d6255-117">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="d6255-118">Следующий код является чрезвычайно простым блоком кода C#, который содержит три командлета в одном файле, который можно использовать в качестве модуля.</span><span class="sxs-lookup"><span data-stu-id="d6255-118">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

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

3. <span data-ttu-id="d6255-119">Упакуйте решение и сохраните пакет в другом месте в пути модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6255-119">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="d6255-120">`PSModulePath`Глобальная переменная среды описывает пути по умолчанию, которые PowerShell будет использовать для поиска вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="d6255-120">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="d6255-121">Например, общий путь для сохранения модуля в системе — `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` .</span><span class="sxs-lookup"><span data-stu-id="d6255-121">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="d6255-122">Если вы не используете пути по умолчанию, необходимо явно указать расположение модуля во время установки.</span><span class="sxs-lookup"><span data-stu-id="d6255-122">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="d6255-123">Не забудьте создать папку для сохранения модуля в, так как может потребоваться папка для хранения нескольких сборок и файлов для решения.</span><span class="sxs-lookup"><span data-stu-id="d6255-123">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="d6255-124">Обратите внимание, что технически вам не нужно устанавливать модуль в любом месте `PSModulePath` — это просто расположения по умолчанию, которые PowerShell будет искать в вашем модуле.</span><span class="sxs-lookup"><span data-stu-id="d6255-124">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="d6255-125">Однако рекомендуется использовать это решение, если нет веских причин для хранения модуля в другом месте.</span><span class="sxs-lookup"><span data-stu-id="d6255-125">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="d6255-126">Дополнительные сведения см. в статьях [Установка модуля PowerShell](./installing-a-powershell-module.md) и [изменение пути установки модуля PowerShell](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="d6255-126">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="d6255-127">Импортируйте модуль в PowerShell с помощью вызова [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="d6255-127">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="d6255-128">Вызов командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) приведет к загрузке модуля в активную память.</span><span class="sxs-lookup"><span data-stu-id="d6255-128">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="d6255-129">Если вы используете PowerShell 3,0 и более поздней версии, просто вызвав имя модуля в коде, вы также импортируете его. Дополнительные сведения см. [в разделе Импорт модуля PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="d6255-129">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="d6255-130">Импорт сборок оснастки в виде модулей</span><span class="sxs-lookup"><span data-stu-id="d6255-130">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="d6255-131">Командлеты и поставщики, существующие в сборках оснастки, можно загрузить как двоичные модули.</span><span class="sxs-lookup"><span data-stu-id="d6255-131">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="d6255-132">Когда сборки оснастки загружаются в виде двоичных модулей, командлеты и поставщики в оснастке доступны пользователю, но класс оснастки в сборке игнорируется, а оснастка не зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="d6255-132">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="d6255-133">В результате командлеты оснастки, предоставляемые Windows PowerShell, не могут обнаружить оснастку, даже если для сеанса доступны командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="d6255-133">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="d6255-134">Кроме того, любые файлы форматирования или типы, на которые ссылается оснастка, не могут быть импортированы как часть двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="d6255-134">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="d6255-135">Чтобы импортировать файлы форматирования и типы, необходимо создать манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="d6255-135">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="d6255-136">См. раздел Создание [манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="d6255-136">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6255-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d6255-137">See Also</span></span>

[<span data-ttu-id="d6255-138">Написание модуля Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6255-138">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
