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
# <a name="how-to-write-a-powershell-binary-module"></a>Как написать бинарный модуль PowerShell

Двоичный модуль может быть любой сборки (DLL), содержащий классы командлет. По умолчанию все командлеты в сборке импортируются при импорте двоичных модулей. Тем не менее можно ограничить командлеты, которые импортируются путем создания манифеста модуля, корневой модуль которого представляет сборку. (Например, ключ CmdletsToExport манифеста можно использовать для экспорта только нужные командлеты, которые необходимы.) Кроме того двоичный модуль может содержать дополнительные файлы, используя структуру каталогов и другие фрагменты данных полезно управления, что один командлет не может.

Следующая процедура описывает создание и установка двоичного модуля PowerShell.

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a>Как создать и установить двоичного модуля PowerShell

1. Создайте двоичный решение PowerShell (таких как командлет, написанных на C#), с возможностями необходима и убедитесь, что он работает правильно.

   С точки зрения кода двоичный модуль лежит просто сборкой командлет. На самом деле PowerShell будет считать сборку один командлет модуля с точки зрения загрузку и выгрузку с без дополнительных усилий от разработчика. Дополнительные сведения о написании командлета, см. в разделе [написание командлетов Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).

2. При необходимости создайте остальной части решения: (Дополнительные командлеты, XML-файлы и т. д.) и описание их с помощью манифеста модуля.

   Кроме описания сборок командлет в решении, манифеста модуля можно описать способ экспорта и импорта модуля, какие командлеты будут доступны и дополнительные файлы будет отправлена в модуль.
   Как уже говорилось ранее тем не менее, PowerShell может обрабатывать двоичные командлета типа модуля с без дополнительных усилий.
   Таким образом манифест модуля полезно, главным образом для объединения нескольких файлов в один пакет, или явно управления публикации для данной сборки.
   Дополнительные сведения см. в разделе [как написание манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).

   Ниже приведен предельно простой C# блок кода, содержащий три командлета, в том же файле, который может использоваться в качестве модуля.

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

3. Пакет решения и сохраните пакет в другое место в путь к модулю PowerShell.

   `PSModulePath` Глобальную переменную среды описывает пути по умолчанию, которые будут использовать PowerShell для поиска вашего модуля. Например, общий путь для сохранения модуля в системе будет `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`. Если вы не используете пути по умолчанию, необходимо явно указать расположение вашего модуля во время установки. Не забудьте создать папку для сохранения вашего модуля, как вам может понадобиться папку для хранения нескольких сборок и файлов для вашего решения.

   Обратите внимание, что технически не необходимо установить модуль в любом месте на `PSModulePath` -это просто расположения по умолчанию, которые PowerShell будет выглядеть для вашего модуля. Тем не менее он считается оптимальным образом, чтобы сделать это, если у вас нет веских причин хранить где-то еще модуля. Дополнительные сведения см. в разделе [Установка модуля PowerShell](./installing-a-powershell-module.md) и [изменении пути установки модуля PowerShell](./modifying-the-psmodulepath-installation-path.md).

4. Импорт модуля PowerShell с помощью вызова [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

   Вызов к [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) загрузит вашего модуля в активной памяти. Если вы используете PowerShell 3.0 и более поздней версии, просто вызвав имя модуля в коде также импортирует. Дополнительные сведения см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md).

## <a name="importing-snap-in-assemblies-as-modules"></a>Импортирование сборок оснастки как модули

Командлеты и поставщики, которые существуют в сборках оснастки можно загрузить как двоичные модули. При оснастки сборки загружаются как двоичные модули, командлеты и поставщики в оснастке доступны пользователю, но класс оснастки в сборке пропускается и оснастки не зарегистрирован. Таким образом командлеты оснастки, предоставляемые Windows PowerShell не может обнаружить оснастки, несмотря на то, что командлеты и поставщики, доступные в сеанс.

Кроме того нельзя импортировать файлы форматирования или типы, на которые ссылается эта оснастка в рамках двоичного модуля.
Чтобы импортировать файлы форматирования и типов необходимо создать манифест модуля.
См. в разделе, [способах создания манифеста модуля PowerShell](how-to-write-a-powershell-module-manifest.md).

## <a name="see-also"></a>См. также

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
