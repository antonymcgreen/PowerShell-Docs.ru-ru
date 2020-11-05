---
ms.date: 07/08/2020
keywords: dsc,powershell,конфигурация,установка
title: Создание пользовательских ресурсов настройки требуемого состояния Windows PowerShell
description: В этой статье приведены общие сведения о разработке ресурсов, а также ссылки на статьи с подробной информацией и примерами.
ms.openlocfilehash: ff9a0c8ae10583155217fbeccc62e6e1c94f9a11
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656412"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="b1e14-104">Создание пользовательских ресурсов настройки требуемого состояния Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1e14-104">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="b1e14-105">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b1e14-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="b1e14-106">Настройка требуемого состояния (DSC) Windows PowerShell включает встроенные ресурсы для настройки среды.</span><span class="sxs-lookup"><span data-stu-id="b1e14-106">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="b1e14-107">В этой статье приведены общие сведения о разработке ресурсов, а также ссылки на статьи с подробной информацией и примерами.</span><span class="sxs-lookup"><span data-stu-id="b1e14-107">This article provides an overview of developing resources and links to articles with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="b1e14-108">Компоненты ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="b1e14-108">DSC resource components</span></span>

<span data-ttu-id="b1e14-109">Ресурс DSC — это модуль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1e14-109">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="b1e14-110">Модуль содержит схему (определение настраиваемых свойств) и реализацию (код, выполняющий заданную конфигурацией работу) для ресурса.</span><span class="sxs-lookup"><span data-stu-id="b1e14-110">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="b1e14-111">Схема ресурсов DSC может быть определена в MOF-файле, а реализация выполняется модулем сценариев.</span><span class="sxs-lookup"><span data-stu-id="b1e14-111">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="b1e14-112">С добавлением поддержки классов PowerShell в версии 5 появилась возможность определять схему и реализацию в классе.</span><span class="sxs-lookup"><span data-stu-id="b1e14-112">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="b1e14-113">Более подробные инструкции по созданию ресурсов DSC см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="b1e14-113">The following articles describe in more detail how to create DSC resources.</span></span>

- [<span data-ttu-id="b1e14-114">Написание пользовательских ресурсов DSC с использованием MOF</span><span class="sxs-lookup"><span data-stu-id="b1e14-114">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
- [<span data-ttu-id="b1e14-115">Реализация ресурса DSC на языке C#</span><span class="sxs-lookup"><span data-stu-id="b1e14-115">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md)
- [<span data-ttu-id="b1e14-116">Написание пользовательских ресурсов DSC с использованием классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1e14-116">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md)
- [<span data-ttu-id="b1e14-117">Составные ресурсы: использование DSC как ресурса</span><span class="sxs-lookup"><span data-stu-id="b1e14-117">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)
- [<span data-ttu-id="b1e14-118">Использование конструктора ресурсов</span><span class="sxs-lookup"><span data-stu-id="b1e14-118">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md)
