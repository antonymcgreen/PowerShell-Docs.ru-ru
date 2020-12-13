---
ms.date: 09/13/2016
ms.topic: reference
title: Обновляемая Справка — пошаговое создание
description: Обновляемая Справка — пошаговое создание
ms.openlocfilehash: c4aecdb801cac16c9cb07853317835fd87e6a0a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658825"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="9ddfa-103">Создание обновляемой справки: пошаговые инструкции</span><span class="sxs-lookup"><span data-stu-id="9ddfa-103">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="9ddfa-104">В этом документе перечислены этапы процесса создания обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-104">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="9ddfa-105">Создание обновляемой справки: пошаговое руководство</span><span class="sxs-lookup"><span data-stu-id="9ddfa-105">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="9ddfa-106">Обновляемая справка предназначена для конечных пользователей, но она также предоставляет значительные преимущества авторам модулей и средствам записи справки, включая возможность добавления содержимого, исправления ошибок, доставки в нескольких культурах пользовательского интерфейса и реагирования на пользовательские комментарии и запросы, долго после доставки модуля.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-106">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="9ddfa-107">В этом разделе объясняется, как упаковывать и отправлять файлы справки, чтобы пользователи могли загружать и устанавливать их с помощью командлетов [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="9ddfa-107">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="9ddfa-108">В следующих шагах представлен обзор процесса поддержки обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-108">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="9ddfa-109">Шаг 1. Поиск веб-сайта для файлов справки</span><span class="sxs-lookup"><span data-stu-id="9ddfa-109">Step 1: Find an internet site for your help files</span></span>

<span data-ttu-id="9ddfa-110">Первым шагом в создании обновляемой справки является поиск расположения в Интернете для файлов справки вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-110">The first step in creating updatable help is to find an internet location for your module's help files.</span></span> <span data-ttu-id="9ddfa-111">На самом деле можно использовать два разных расположения.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-111">Actually, you can use two different locations.</span></span> <span data-ttu-id="9ddfa-112">Файл справочной информации о модуле (HelpInfo XML) можно разместить в одном расположении в Интернете, а CAB-файлы содержимого справки — в другом расположении в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-112">You can keep your module's help information file (HelpInfo XML - described below) at one internet location and the help content CAB files at another internet location.</span></span> <span data-ttu-id="9ddfa-113">Все CAB-файлы содержимого справки для модуля должны находиться в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-113">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="9ddfa-114">Вы можете поместить CAB-файлы содержимого справки для разных модулей в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-114">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="9ddfa-115">Шаг 2. Добавление ключа HelpInfoURI в манифест модуля</span><span class="sxs-lookup"><span data-stu-id="9ddfa-115">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="9ddfa-116">Добавьте ключ **HelpInfoURI** в манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-116">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="9ddfa-117">Значение ключа — это универсальный код ресурса (URI) расположения XML-файла данных HelpInfo для модуля.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-117">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="9ddfa-118">В целях безопасности адрес должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="9ddfa-118">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="9ddfa-119">URI должен указывать расположение в Интернете, но не должно включать имя XML-файла HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-119">The URI should specify an internet location, but must not include the HelpInfo XML filename.</span></span>

<span data-ttu-id="9ddfa-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="9ddfa-120">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'https://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="9ddfa-121">Шаг 3. Создание XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="9ddfa-121">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="9ddfa-122">Файл сведений HelpInfo XML содержит универсальный код ресурса (URI) расположения файлов справки в Интернете и номера версий самых новых файлов справки для модуля в каждой поддерживаемой культуре пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-122">The HelpInfo XML information file contains the URI of the internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="9ddfa-123">Каждый модуль Windows PowerShell имеет один XML-файл HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-123">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="9ddfa-124">При обновлении файлов справки вы редактируете или заменяете XML-файл HelpInfo; Вы не добавите еще одну.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-124">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="9ddfa-125">Дополнительные сведения см. [в разделе Создание XML-файла HelpInfo](./how-to-create-a-helpinfo-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="9ddfa-125">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-create-cab-files"></a><span data-ttu-id="9ddfa-126">Шаг 4. Создание CAB-файлов</span><span class="sxs-lookup"><span data-stu-id="9ddfa-126">Step 4: Create CAB files</span></span>

<span data-ttu-id="9ddfa-127">Используйте средство, которое создает CAB- `.cab` файлы (например,), `MakeCab.exe` чтобы создать CAB-файл, содержащий файлы справки для вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-127">Use a tool that creates cabinet (`.cab`) files, such as `MakeCab.exe`, to create a CAB file that contains the help files for your module.</span></span> <span data-ttu-id="9ddfa-128">Создайте отдельный CAB-файл для файлов справки в каждой поддерживаемой культуре пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-128">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="9ddfa-129">Дополнительные сведения см. [в разделе Подготовка обновляемых CAB-файлов справки](./how-to-prepare-updatable-help-cab-files.md).</span><span class="sxs-lookup"><span data-stu-id="9ddfa-129">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-5-upload-your-files"></a><span data-ttu-id="9ddfa-130">Шаг 5. Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="9ddfa-130">Step 5: Upload your files</span></span>

<span data-ttu-id="9ddfa-131">Чтобы опубликовать новые или обновленные файлы справки, отправьте CAB-файлы в расположение в Интернете, указанное элементом **хелпконтентури** в файле HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-131">To publish new or updated help files, upload the CAB files to the internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="9ddfa-132">Затем отправьте XML-файл HelpInfo в расположение в Интернете, указанное значением ключа **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="9ddfa-132">Then, upload the HelpInfo XML file to the internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
