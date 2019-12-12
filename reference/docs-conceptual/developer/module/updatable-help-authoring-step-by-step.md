---
title: 'Обновляемая Справка по разработке: пошаговая операция | Документация Майкрософт'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10098160-c6b4-4339-b8ff-2c4f8cc0699b
caps.latest.revision: 13
ms.openlocfilehash: fbc77cc0fafce93d239da1c459d4b761b21ef3cb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366993"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="40647-102">Создание обновляемой справки: пошаговые инструкции</span><span class="sxs-lookup"><span data-stu-id="40647-102">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="40647-103">В этом документе перечислены этапы процесса создания обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="40647-103">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="40647-104">Создание обновляемой справки: пошаговое руководство</span><span class="sxs-lookup"><span data-stu-id="40647-104">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="40647-105">Обновляемая справка предназначена для конечных пользователей, но она также предоставляет значительные преимущества авторам модулей и средствам записи справки, включая возможность добавления содержимого, исправления ошибок, доставки в нескольких культурах пользовательского интерфейса и реагирования на комментарии и запросы пользователя, долго после модуль отправлен.</span><span class="sxs-lookup"><span data-stu-id="40647-105">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="40647-106">В этом разделе объясняется, как упаковывать и отправлять файлы справки, чтобы пользователи могли загружать и устанавливать их с помощью командлетов [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) .</span><span class="sxs-lookup"><span data-stu-id="40647-106">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="40647-107">В следующих шагах представлен обзор процесса поддержки обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="40647-107">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="40647-108">Шаг 1. Поиск веб-сайта для файлов справки</span><span class="sxs-lookup"><span data-stu-id="40647-108">Step 1: Find an Internet site for your help files</span></span>

<span data-ttu-id="40647-109">Первым шагом в создании обновляемой справки является поиск расположения в Интернете для файлов справки вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="40647-109">The first step in creating updatable help is to find an Internet location for your module's help files.</span></span> <span data-ttu-id="40647-110">На самом деле можно использовать два разных расположения.</span><span class="sxs-lookup"><span data-stu-id="40647-110">Actually, you can use two different locations.</span></span> <span data-ttu-id="40647-111">Файл справочной информации о модуле (HelpInfo XML) можно разместить в одном расположении в Интернете, а CAB-файлы содержимого справки — в другом расположении в Интернете.</span><span class="sxs-lookup"><span data-stu-id="40647-111">You can keep your module's help information file (HelpInfo XML - described below) at one Internet location and the help content CAB files at another Internet location.</span></span> <span data-ttu-id="40647-112">Все CAB-файлы содержимого справки для модуля должны находиться в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="40647-112">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="40647-113">Вы можете поместить CAB-файлы содержимого справки для разных модулей в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="40647-113">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="40647-114">Шаг 2. Добавление ключа HelpInfoURI в манифест модуля</span><span class="sxs-lookup"><span data-stu-id="40647-114">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="40647-115">Добавьте ключ **HelpInfoURI** в манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="40647-115">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="40647-116">Значение ключа — это универсальный код ресурса (URI) расположения XML-файла данных HelpInfo для модуля.</span><span class="sxs-lookup"><span data-stu-id="40647-116">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="40647-117">В целях безопасности адрес должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="40647-117">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="40647-118">URI должен указывать расположение в Интернете, но не должно включать имя XML-файла HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="40647-118">The URI should specify an Internet location, but must not include the HelpInfo XML file name.</span></span>

<span data-ttu-id="40647-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="40647-119">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'http://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="40647-120">Шаг 3. Создание XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="40647-120">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="40647-121">Файл сведений HelpInfo XML содержит универсальный код ресурса (URI) расположения файлов справки в Интернете и номера версий самых новых файлов справки для модуля в каждой поддерживаемой культуре пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="40647-121">The HelpInfo XML information file contains the URI of the Internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="40647-122">Каждый модуль Windows PowerShell имеет один XML-файл HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="40647-122">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="40647-123">При обновлении файлов справки вы редактируете или заменяете XML-файл HelpInfo; Вы не добавите еще одну.</span><span class="sxs-lookup"><span data-stu-id="40647-123">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="40647-124">Дополнительные сведения см. [в разделе Создание XML-файла HelpInfo](./how-to-create-a-helpinfo-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="40647-124">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-sign-your-help-files"></a><span data-ttu-id="40647-125">Шаг 4. Подписание файлов справки</span><span class="sxs-lookup"><span data-stu-id="40647-125">Step 4: Sign your help files</span></span>

<span data-ttu-id="40647-126">Цифровые подписи не требуются, но они являются рекомендациями при совместном использовании файлов.</span><span class="sxs-lookup"><span data-stu-id="40647-126">Digital signatures are not required, but they are a best-practice recommendation whenever you are sharing files.</span></span>

### <a name="step-5-create-cab-files"></a><span data-ttu-id="40647-127">Шаг 5. Создание CAB-файлов</span><span class="sxs-lookup"><span data-stu-id="40647-127">Step 5: Create CAB files</span></span>

<span data-ttu-id="40647-128">Используйте средство, которое создает CAB-файлы (например, MakeCab. exe) для создания. CAB-файл, содержащий файлы справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="40647-128">Use a tool that creates cabinet (.cab) files, such as MakeCab.exe, to create a .CAB file that contains the help files for your module.</span></span> <span data-ttu-id="40647-129">Создайте отдельный CAB-файл для файлов справки в каждой поддерживаемой культуре пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="40647-129">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="40647-130">Дополнительные сведения см. [в разделе Подготовка обновляемых CAB-файлов справки](./how-to-prepare-updatable-help-cab-files.md).</span><span class="sxs-lookup"><span data-stu-id="40647-130">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-6-upload-your-files"></a><span data-ttu-id="40647-131">Шаг 6. Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="40647-131">Step 6: Upload your files</span></span>

<span data-ttu-id="40647-132">Чтобы опубликовать новые или обновленные файлы справки, отправьте CAB-файлы в расположение в Интернете, указанное элементом **хелпконтентури** в файле HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="40647-132">To publish new or updated help files, upload the CAB files to the Internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="40647-133">Затем отправьте XML-файл HelpInfo в расположение в Интернете, указанное значением ключа **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="40647-133">Then, upload the HelpInfo XML file to the Internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
