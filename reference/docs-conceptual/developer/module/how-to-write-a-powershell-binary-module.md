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
# <a name="how-to-write-a-powershell-binary-module"></a>Как написать бинарный модуль PowerShell

Двоичным модулем может быть любая сборка (. dll), содержащая классы командлетов. По умолчанию все командлеты в сборке импортируются при импорте двоичного модуля. Тем не менее можно ограничить импортируемые командлеты, создав манифест модуля, корневым модулем которого является сборка. (Например, ключ CmdletsToExport манифеста можно использовать для экспорта только необходимых командлетов.) Кроме того, двоичный модуль может содержать дополнительные файлы, структуру каталогов и другие элементы полезных данных управления, которые не могут быть доступны для одного командлета.

В следующей процедуре описывается создание и установка двоичного модуля PowerShell.

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a>Создание и установка двоичного модуля PowerShell

1. Создайте двоичное решение PowerShell (например, командлет, написанное на языке C#) с необходимыми возможностями и убедитесь, что оно работает правильно.

   С точки зрения кода ядро двоичного модуля — это просто сборка командлета. Фактически, PowerShell будет рассматривать одну сборку командлетов в качестве модуля с точки зрения загрузки и выгрузки без каких-либо дополнительных усилий в части разработчика. Дополнительные сведения о написании командлета см. [в разделе Написание командлета Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).

2. При необходимости создайте остальную часть вашего решения: (Дополнительные командлеты, XML-файлы и т. д.) и опишите их с помощью манифеста модуля.

   Помимо описания сборок командлетов в решении, манифест модуля может описывать, как вы хотите экспортировать и импортировать модуль, какие командлеты будут предоставлены и какие дополнительные файлы будут помещены в модуль.
   Как уже отмечалось ранее, PowerShell может обрабатывать бинарный командлет, например модуль, без дополнительных усилий.
   Таким образом, манифест модуля полезен в основном для объединения нескольких файлов в один пакет или для явного управления публикацией для данной сборки.
   Дополнительные сведения см. в статье Создание [манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).

   Следующий код является чрезвычайно простым блоком кода C#, который содержит три командлета в одном файле, который можно использовать в качестве модуля.

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

3. Упакуйте решение и сохраните пакет в другом месте в пути модуля PowerShell.

   `PSModulePath`Глобальная переменная среды описывает пути по умолчанию, которые PowerShell будет использовать для поиска вашего модуля. Например, общий путь для сохранения модуля в системе — `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` . Если вы не используете пути по умолчанию, необходимо явно указать расположение модуля во время установки. Не забудьте создать папку для сохранения модуля в, так как может потребоваться папка для хранения нескольких сборок и файлов для решения.

   Обратите внимание, что технически вам не нужно устанавливать модуль в любом месте `PSModulePath` — это просто расположения по умолчанию, которые PowerShell будет искать в вашем модуле. Однако рекомендуется использовать это решение, если нет веских причин для хранения модуля в другом месте. Дополнительные сведения см. в статьях [Установка модуля PowerShell](./installing-a-powershell-module.md) и [изменение пути установки модуля PowerShell](./modifying-the-psmodulepath-installation-path.md).

4. Импортируйте модуль в PowerShell с помощью вызова [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

   Вызов командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) приведет к загрузке модуля в активную память. Если вы используете PowerShell 3,0 и более поздней версии, просто вызвав имя модуля в коде, вы также импортируете его. Дополнительные сведения см. [в разделе Импорт модуля PowerShell](./importing-a-powershell-module.md).

## <a name="importing-snap-in-assemblies-as-modules"></a>Импорт сборок оснастки в виде модулей

Командлеты и поставщики, существующие в сборках оснастки, можно загрузить как двоичные модули. Когда сборки оснастки загружаются в виде двоичных модулей, командлеты и поставщики в оснастке доступны пользователю, но класс оснастки в сборке игнорируется, а оснастка не зарегистрирована. В результате командлеты оснастки, предоставляемые Windows PowerShell, не могут обнаружить оснастку, даже если для сеанса доступны командлеты и поставщики.

Кроме того, любые файлы форматирования или типы, на которые ссылается оснастка, не могут быть импортированы как часть двоичного модуля.
Чтобы импортировать файлы форматирования и типы, необходимо создать манифест модуля.
См. раздел Создание [манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).

## <a name="see-also"></a>См. также

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
