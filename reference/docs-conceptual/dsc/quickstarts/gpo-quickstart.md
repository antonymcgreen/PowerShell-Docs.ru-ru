---
ms.date: 07/09/2019
keywords: DSC,объект групповой политики,powershell,настройка,установка
title: Краткое руководство. Преобразование групповой политики в DSC
ms.openlocfilehash: 852710f261ea1d57228c05d4093c1d78584e0ca5
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236243"
---
# <a name="quickstart-convert-group-policy-into-dsc"></a><span data-ttu-id="e5eb6-103">Краткое руководство. Преобразование групповой политики в DSC</span><span class="sxs-lookup"><span data-stu-id="e5eb6-103">Quickstart: Convert Group Policy into DSC</span></span>

> <span data-ttu-id="e5eb6-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="e5eb6-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="e5eb6-105">Конфигурацию DSC можно создать из групповой политики или базовых показателей Центра безопасности Azure.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-105">You can generate a DSC configuration from a Group Policy or Azure Security Center baseline.</span></span> <span data-ttu-id="e5eb6-106">Модуль [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) содержит следующие команды для выполнения этих задач.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-106">The [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) module includes the following commands for accomplishing this task.</span></span>

- <span data-ttu-id="e5eb6-107">`ConvertFrom-GPO` — преобразование групповых политик, которые хранятся в виде файлов.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-107">`ConvertFrom-GPO` - Converts Group Policies, stored as files.</span></span> <span data-ttu-id="e5eb6-108">Можно также указать каталог, содержащий несколько политик, которые будут объединены в одну конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-108">You can also specify a directory containing multiple policies that will be combined into one Configuration.</span></span>
  - <span data-ttu-id="e5eb6-109">Чтобы экспортировать групповые политики в вашей среде, используйте командлет [Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) или следуйте инструкциям в статье [Экспорт объекта групповой политики в файл](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-109">To export Group Policies in your environment, use the [Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) cmdlet, or follow the instructions in [Export a GPO to a File](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span></span>
- <span data-ttu-id="e5eb6-110">`ConvertFrom-SCM` — преобразование базовых показателей Security Compliance Manager, которые хранятся в виде `.xml`-файлов.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-110">`ConvertFrom-SCM` - Converts Security Compliance Manager baselines, stored as `.xml` files.</span></span>
- <span data-ttu-id="e5eb6-111">`ConvertFrom-ASC` — преобразование базовых показателей Центра безопасности Azure, которые хранятся в виде `.json`-файлов.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-111">`ConvertFrom-ASC` - Converts Azure Security Center baselines, stored as `.json` files.</span></span>
- <span data-ttu-id="e5eb6-112">`Merge-GPOs` — преобразование групповой политики, которая применена на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-112">`Merge-GPOs` - Converts Group Policies applied to a target computer.</span></span>

<span data-ttu-id="e5eb6-113">Командлеты, перечисленные выше, преобразуют базовые показатели в `.mof`-файл DSC.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-113">The cmdlets listed above convert a baseline into a DSC `.mof` file.</span></span> <span data-ttu-id="e5eb6-114">Вы также можете создать сценарий конфигурации (`.ps1`), который можно изменять и перекомпилировать.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-114">You can also choose to output a Configuration script (`.ps1`), that you can edit and recompile.</span></span> <span data-ttu-id="e5eb6-115">Командлеты способны обнаружить ошибки компиляции при наличии отсутствующих ресурсов или повторяющихся блоков.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-115">The cmdlets detect compilation errors for missing resources, or duplicate resource blocks.</span></span> <span data-ttu-id="e5eb6-116">Блоки ресурсов, способные привести к ошибкам компиляции, будут закомментированы.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-116">Resource blocks that would cause compilation errors are commented out.</span></span>

<span data-ttu-id="e5eb6-117">В следующем примере выполняется преобразование [Microsoft Security Baseline](https://www.microsoft.com/download/details.aspx?id=55319) в сценарий конфигурации DSC (`.ps1`) и `.mof`-файл.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-117">The following example converts a [Microsoft Security Baseline](https://www.microsoft.com/download/details.aspx?id=55319) into a DSC configuration script (`.ps1`) and `.mof` file.</span></span>

```powershell
Install-Module BaselineManagement
Import-Module BaselineManagement
ConvertFrom-GPO -Path '.\Windows 10 Version 1903 and Windows Server Version 1903 Security Baseline\GPOs\' -OutputConfigurationScript
```

<span data-ttu-id="e5eb6-118">После выполнения команд, вы увидите два файла в каталоге вывода по умолчанию, созданные по текущему пути.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-118">After running the commands, you see two files in the default "Output" directory created under your current path.</span></span>

```powershell
Get-ChildItem -Path .\Output
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----         7/9/2019   9:35 AM   227.37KB DSCFromGPO.ps1
-a----         7/9/2019   9:35 AM   410.03KB localhost.mof
```

<span data-ttu-id="e5eb6-119">Каждый управляемый узел также потребует следующие два модуля.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-119">Each managed node will also need the following two modules:</span></span>

- [<span data-ttu-id="e5eb6-120">SecurityPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="e5eb6-120">SecurityPolicyDSC</span></span>](https://www.powershellgallery.com/packages/SecurityPolicyDsc)
- [<span data-ttu-id="e5eb6-121">AuditPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="e5eb6-121">AuditPolicyDSC</span></span>](https://www.powershellgallery.com/packages/AuditPolicyDsc)

> [!NOTE]
> <span data-ttu-id="e5eb6-122">**BaselineManagement** — это решение, разработанное сообществом, чтобы сделать поддержку DSC более доступной. Решения сообщества поставляются разработчиками проекта, а не корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e5eb6-122">**BaselineManagement** is a solution developed by the community to make DSC more discoverable for Support for community solutions come from the project maintainers and not from Microsoft.</span></span> <span data-ttu-id="e5eb6-123">Вы можете открыть новую проблему по **BaselineManagement** на [GitHub](https://github.com/microsoft/BaselineManagement).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-123">You can open a new issue for **BaselineManagement** on [GitHub](https://github.com/microsoft/BaselineManagement).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5eb6-124">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="e5eb6-124">Next steps</span></span>

- <span data-ttu-id="e5eb6-125">Чтобы отправить скрипт конфигурации в конфигурацию состояния службы автоматизации Azure, см. раздел [Приступая к работе](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-125">To upload your configuration script into Azure Automation State Configuration, see [Getting Started](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span></span>
- <span data-ttu-id="e5eb6-126">Добавьте модули **SecurityPolicyDSC** и **AuditPolicyDSC** в свою [учетную запись службы автоматизации](/azure/automation/shared-resources/modules).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-126">Add the **SecurityPolicyDSC** and **AuditPolicyDSC** modules to your [Automation Account](/azure/automation/shared-resources/modules).</span></span>
- <span data-ttu-id="e5eb6-127">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="e5eb6-127">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
