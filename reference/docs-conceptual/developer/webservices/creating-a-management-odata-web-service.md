---
title: Создание веб-службы OData для управления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06b1b050-0bf7-48f5-ba05-43f489d597c0
caps.latest.revision: 10
ms.openlocfilehash: 476fce9fc087b870bad93a9204a820c5a84df99e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359723"
---
# <a name="creating-a-management-odata-web-service"></a><span data-ttu-id="57fbe-102">Создание веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="57fbe-102">Creating a Management OData Web Service</span></span>

<span data-ttu-id="57fbe-103">Расширение IIS ODATA для управления — это инфраструктура для создания конечной точки веб-службы ASP.NET, которая предоставляет доступ к данным управления, доступным через командлеты и скрипты Windows PowerShell, как сущности веб-службы OData.</span><span class="sxs-lookup"><span data-stu-id="57fbe-103">Management ODATA IIS Extension is an infrastructure for creating an ASP.NET web service end point that exposes your management data, accessed through Windows PowerShell cmdlets and scripts, as OData Web service entities.</span></span> <span data-ttu-id="57fbe-104">Это достигается путем обработки запросов OData и их преобразования в вызов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57fbe-104">It does that by processing OData requests and converting them into a Windows PowerShell invocation.</span></span> <span data-ttu-id="57fbe-105">Группы разработчиков продукта могут создавать поверх этой инфраструктуры для создания конечных точек, предоставляющих определенные наборы данных управления.</span><span class="sxs-lookup"><span data-stu-id="57fbe-105">Product teams can build on top of this infrastructure to create endpoints that expose specific sets of management data.</span></span>

<span data-ttu-id="57fbe-106">Скачайте и установите образец [псвсролебаседплугинс](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) .</span><span class="sxs-lookup"><span data-stu-id="57fbe-106">Download and install the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="57fbe-107">Следуйте инструкциям по развертыванию веб-службы.</span><span class="sxs-lookup"><span data-stu-id="57fbe-107">Follow the instructions to deploy the web service.</span></span> <span data-ttu-id="57fbe-108">Эта веб-служба предоставляет службы и процессы с помощью операций создания, чтения, обновления и удаления (CRUD).</span><span class="sxs-lookup"><span data-stu-id="57fbe-108">This web service exposes Services and Processes through Create, Read, Update, and Delete (CRUD) operations.</span></span> <span data-ttu-id="57fbe-109">Запросы CRUD, выполненные в веб-службе, вызывают команды Windows PowerShell, выполняющие запрошенные операции.</span><span class="sxs-lookup"><span data-stu-id="57fbe-109">CRUD requests made to the web service invoke  Windows PowerShell commands that perform the requested operations.</span></span> <span data-ttu-id="57fbe-110">Сопоставление между операциями CRUD и базовыми командами Windows PowerShell реализуется двумя файлами схемы: schema. mof и Schema. XML.</span><span class="sxs-lookup"><span data-stu-id="57fbe-110">A mapping between the CRUD operations and the underlying Windows PowerShell commands is implemented by two schema files, schema.mof and schema.xml.</span></span> <span data-ttu-id="57fbe-111">Файл Schema. mof использует стандарт [Distributed Management Task Force](https://www.dmtf.org/) (DMTF) Standard.</span><span class="sxs-lookup"><span data-stu-id="57fbe-111">The schema.mof file uses the [Distributed Management  Task Force](https://www.dmtf.org/) (DMTF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="57fbe-112">Файл Schema. XML использует схему XML, описанную в разделе [схема сопоставления ресурсов](./resource-mapping-schema.md).</span><span class="sxs-lookup"><span data-stu-id="57fbe-112">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57fbe-113">Прежде чем включать расширение IIS ODATA для управления в Windows Server 2008 R2 с пакетом обновления 1 (SP1), необходимо включить следующие функции.</span><span class="sxs-lookup"><span data-stu-id="57fbe-113">Before you enabling Management ODATA IIS Extension on Windows Server 2008 R2 SP1, the following features must be enabled.</span></span>
>
> 1.  <span data-ttu-id="57fbe-114">IIS — Вебсерверроле</span><span class="sxs-lookup"><span data-stu-id="57fbe-114">IIS-WebServerRole</span></span>
> 2.  <span data-ttu-id="57fbe-115">IIS-WebServer</span><span class="sxs-lookup"><span data-stu-id="57fbe-115">IIS-WebServer</span></span>
> 3.  <span data-ttu-id="57fbe-116">IIS-HttpTracing</span><span class="sxs-lookup"><span data-stu-id="57fbe-116">IIS-HttpTracing</span></span>
> 4.  <span data-ttu-id="57fbe-117">IIS — Манажементодата</span><span class="sxs-lookup"><span data-stu-id="57fbe-117">IIS-ManagementOData</span></span>

## <a name="steps-for-creating-a-management-odata-web-service"></a><span data-ttu-id="57fbe-118">Действия по созданию веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-118">Steps for creating a Management OData web service</span></span>

<span data-ttu-id="57fbe-119">В следующих разделах описывается создание и развертывание веб-службы OData управления.</span><span class="sxs-lookup"><span data-stu-id="57fbe-119">The following topics describe how to create and deploy a Management OData web service.</span></span>

- [<span data-ttu-id="57fbe-120">Добавление ресурсов в веб-службу управления OData</span><span class="sxs-lookup"><span data-stu-id="57fbe-120">Adding Resources to a Management OData Web Service</span></span>](./adding-resources-to-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-121">Реализация пользовательской авторизации для веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-121">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-122">Реализация Сессионконфигуратион для веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-122">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-123">Создание файла схемы MOF для веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-124">Создание файла схемы XML для веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-124">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-125">Создание файла Web. config для веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-125">Authoring the Web.config file for a Management OData web service</span></span>](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-126">Развертывание веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-126">Deploying a Management OData web service</span></span>](./deploying-a-management-odata-web-service.md)

- [<span data-ttu-id="57fbe-127">Связывание сущностей OData управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-127">Associating Management OData Entities</span></span>](./associating-management-odata-entities.md)

## <a name="see-also"></a><span data-ttu-id="57fbe-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="57fbe-128">See Also</span></span>

[<span data-ttu-id="57fbe-129">Файлы схемы расширения IIS ODATA для управления</span><span class="sxs-lookup"><span data-stu-id="57fbe-129">Management ODATA IIS Extension Schema Files</span></span>](./management-odata-iis-extension-schema-files.md)
