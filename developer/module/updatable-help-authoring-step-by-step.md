---
title: 'Создание обновляемой справки: Пошаговые | Документация Майкрософт'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10098160-c6b4-4339-b8ff-2c4f8cc0699b
caps.latest.revision: 13
ms.openlocfilehash: fbc77cc0fafce93d239da1c459d4b761b21ef3cb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860320"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="f7eab-102">Создание обновляемой справки: пошаговые инструкции</span><span class="sxs-lookup"><span data-stu-id="f7eab-102">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="f7eab-103">Этот документ перечислены этапы разработки, обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="f7eab-103">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="f7eab-104">Создание обновляемой справки: пошаговые инструкции</span><span class="sxs-lookup"><span data-stu-id="f7eab-104">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="f7eab-105">Обновляемой справки предназначена для конечных пользователей, но он также обеспечивает значительные преимущества для авторы модулей и записи справки, включая возможность добавления содержимого, исправления ошибок, обеспечивают несколько языков и региональных параметров пользовательского интерфейса и отвечать на комментарии пользователей и запросов, время после модуль был доставлен.</span><span class="sxs-lookup"><span data-stu-id="f7eab-105">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="f7eab-106">В этом разделе объясняется, как вы пакет и файлах справки передачи таким образом, чтобы пользователи могут загрузить и установить их с помощью [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлетов.</span><span class="sxs-lookup"><span data-stu-id="f7eab-106">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="f7eab-107">Ниже приведены общие сведения о поддержке обновляемой справки в процессе.</span><span class="sxs-lookup"><span data-stu-id="f7eab-107">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="f7eab-108">Шаг 1. Найти сайт в Интернете для файлы справки</span><span class="sxs-lookup"><span data-stu-id="f7eab-108">Step 1: Find an Internet site for your help files</span></span>

<span data-ttu-id="f7eab-109">Создание обновляемой справки первым делом для поиска расположения в Интернете для вашего модуля файлы справки.</span><span class="sxs-lookup"><span data-stu-id="f7eab-109">The first step in creating updatable help is to find an Internet location for your module's help files.</span></span> <span data-ttu-id="f7eab-110">На самом деле можно использовать два разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="f7eab-110">Actually, you can use two different locations.</span></span> <span data-ttu-id="f7eab-111">Вы можете сохранить файл сведений о вашего модуля справке (HelpInfo XML - описано ниже) одного расположения в Интернете и CAB-файлы содержимого справки в другом расположении в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f7eab-111">You can keep your module's help information file (HelpInfo XML - described below) at one Internet location and the help content CAB files at another Internet location.</span></span> <span data-ttu-id="f7eab-112">Все файлы с содержимым CAB-файла с справки для модуля должны находиться в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="f7eab-112">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="f7eab-113">CAB-файлы справки для содержимого для различных модулей можно разместить в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="f7eab-113">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="f7eab-114">Шаг 2. Добавить ключ HelpInfoURI в манифесте модуля</span><span class="sxs-lookup"><span data-stu-id="f7eab-114">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="f7eab-115">Добавить **HelpInfoURI** ключа в манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="f7eab-115">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="f7eab-116">Значение ключа является универсальный код ресурса (URI) расположения файла сведения HelpInfo XML для модуля.</span><span class="sxs-lookup"><span data-stu-id="f7eab-116">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="f7eab-117">Для обеспечения безопасности адрес должен начинаться с «http» или «https».</span><span class="sxs-lookup"><span data-stu-id="f7eab-117">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="f7eab-118">URI должен указывать расположение Internet, но не должен включать имя файла HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="f7eab-118">The URI should specify an Internet location, but must not include the HelpInfo XML file name.</span></span>

<span data-ttu-id="f7eab-119">Например:</span><span class="sxs-lookup"><span data-stu-id="f7eab-119">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'http://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="f7eab-120">Шаг 3. Создайте файл HelpInfo XML</span><span class="sxs-lookup"><span data-stu-id="f7eab-120">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="f7eab-121">HelpInfo XML-файле информацию содержит URI расположения в Интернете файлы справки и номера версий новейшие файлы справки для модуля в каждый поддерживаемый язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f7eab-121">The HelpInfo XML information file contains the URI of the Internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="f7eab-122">Каждый модуль Windows PowerShell имеет один XML-файл HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="f7eab-122">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="f7eab-123">При обновлении файлы справки, можно изменить или заменить файл HelpInfo XML; не следует добавлять другой.</span><span class="sxs-lookup"><span data-stu-id="f7eab-123">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="f7eab-124">Дополнительные сведения см. в разделе [способ создания XML-файл HelpInfo](./how-to-create-a-helpinfo-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="f7eab-124">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-sign-your-help-files"></a><span data-ttu-id="f7eab-125">Шаг 4. Подпись файлов справки</span><span class="sxs-lookup"><span data-stu-id="f7eab-125">Step 4: Sign your help files</span></span>

<span data-ttu-id="f7eab-126">Цифровые подписи не являются обязательными, но они являются лучшим рекомендацию всякий раз, когда предоставляется доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="f7eab-126">Digital signatures are not required, but they are a best-practice recommendation whenever you are sharing files.</span></span>

### <a name="step-5-create-cab-files"></a><span data-ttu-id="f7eab-127">Шаг 5. Создание CAB-файлы</span><span class="sxs-lookup"><span data-stu-id="f7eab-127">Step 5: Create CAB files</span></span>

<span data-ttu-id="f7eab-128">Используйте средство, которое создает CAB-файлы, такие как MakeCab.exe для создания. CAB-файл, содержащий файлы справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="f7eab-128">Use a tool that creates cabinet (.cab) files, such as MakeCab.exe, to create a .CAB file that contains the help files for your module.</span></span> <span data-ttu-id="f7eab-129">Создайте отдельный CAB-файл, файлы справки для каждого поддерживаемого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f7eab-129">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="f7eab-130">Дополнительные сведения см. в разделе [как подготовка обновляемых файлов справки CAB](./how-to-prepare-updatable-help-cab-files.md).</span><span class="sxs-lookup"><span data-stu-id="f7eab-130">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-6-upload-your-files"></a><span data-ttu-id="f7eab-131">Шаг 6. Передача файлов</span><span class="sxs-lookup"><span data-stu-id="f7eab-131">Step 6: Upload your files</span></span>

<span data-ttu-id="f7eab-132">Чтобы опубликовать новые или обновленные файлы справки, загрузить CAB-файлы в расположения в Интернете, задаваемый **HelpContentUri** в файле HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="f7eab-132">To publish new or updated help files, upload the CAB files to the Internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="f7eab-133">Отправьте XML-файл HelpInfo для расположения в Интернете, указанный по значению **HelpInfoUri** ключа в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="f7eab-133">Then, upload the HelpInfo XML file to the Internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
