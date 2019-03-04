---
title: Создание службы управления веб-OData | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06b1b050-0bf7-48f5-ba05-43f489d597c0
caps.latest.revision: 10
ms.openlocfilehash: 476fce9fc087b870bad93a9204a820c5a84df99e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856630"
---
# <a name="creating-a-management-odata-web-service"></a><span data-ttu-id="c8b10-102">Создание веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="c8b10-102">Creating a Management OData Web Service</span></span>

<span data-ttu-id="c8b10-103">Расширение IIS ODATA для управления — это инфраструктура для создания ASP.NET web конечной точки службы, предоставляющей данные управления, через командлеты Windows PowerShell и сценариев, как сущности службы веб-OData.</span><span class="sxs-lookup"><span data-stu-id="c8b10-103">Management ODATA IIS Extension is an infrastructure for creating an ASP.NET web service end point that exposes your management data, accessed through Windows PowerShell cmdlets and scripts, as OData Web service entities.</span></span> <span data-ttu-id="c8b10-104">Он делает это путем обработки запросов OData и преобразовывая их в вызове в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8b10-104">It does that by processing OData requests and converting them into a Windows PowerShell invocation.</span></span> <span data-ttu-id="c8b10-105">Группы разработки продуктов можно создавать на основе этой инфраструктуры для создания конечных точек, которые предоставляют определенные наборы данных управления.</span><span class="sxs-lookup"><span data-stu-id="c8b10-105">Product teams can build on top of this infrastructure to create endpoints that expose specific sets of management data.</span></span>

<span data-ttu-id="c8b10-106">Скачайте и установите [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) образца.</span><span class="sxs-lookup"><span data-stu-id="c8b10-106">Download and install the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="c8b10-107">Следуйте инструкциям для развертывания веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c8b10-107">Follow the instructions to deploy the web service.</span></span> <span data-ttu-id="c8b10-108">Этот веб-служба предоставляет служб и процессов с помощью операций создания, чтения, обновления и удаления (CRUD).</span><span class="sxs-lookup"><span data-stu-id="c8b10-108">This web service exposes Services and Processes through Create, Read, Update, and Delete (CRUD) operations.</span></span> <span data-ttu-id="c8b10-109">CRUD, запросы к веб-службы вызова команд Windows PowerShell, выполнения запрошенных операций.</span><span class="sxs-lookup"><span data-stu-id="c8b10-109">CRUD requests made to the web service invoke  Windows PowerShell commands that perform the requested operations.</span></span> <span data-ttu-id="c8b10-110">Сопоставление операции CRUD и базовые команды Windows PowerShell реализуется файлы две схемы, schema.mof и schema.xml.</span><span class="sxs-lookup"><span data-stu-id="c8b10-110">A mapping between the CRUD operations and the underlying Windows PowerShell commands is implemented by two schema files, schema.mof and schema.xml.</span></span> <span data-ttu-id="c8b10-111">Schema.MOF-файл использует [Distributed Management Task Force](https://www.dmtf.org/) standard (DMTF) управляемого объекта (MOF).</span><span class="sxs-lookup"><span data-stu-id="c8b10-111">The schema.mof file uses the [Distributed Management  Task Force](https://www.dmtf.org/) (DMTF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="c8b10-112">Файл schema.xml использует схему XML, описанной в [схема сопоставления ресурсов](./resource-mapping-schema.md).</span><span class="sxs-lookup"><span data-stu-id="c8b10-112">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8b10-113">Прежде чем включить расширение IIS ODATA для управления на Windows Server 2008 R2 SP1 необходимо включить следующие функции.</span><span class="sxs-lookup"><span data-stu-id="c8b10-113">Before you enabling Management ODATA IIS Extension on Windows Server 2008 R2 SP1, the following features must be enabled.</span></span>
>
> 1.  <span data-ttu-id="c8b10-114">IIS-WebServerRole</span><span class="sxs-lookup"><span data-stu-id="c8b10-114">IIS-WebServerRole</span></span>
> 2.  <span data-ttu-id="c8b10-115">IIS-WebServer</span><span class="sxs-lookup"><span data-stu-id="c8b10-115">IIS-WebServer</span></span>
> 3.  <span data-ttu-id="c8b10-116">IIS-HttpTracing</span><span class="sxs-lookup"><span data-stu-id="c8b10-116">IIS-HttpTracing</span></span>
> 4.  <span data-ttu-id="c8b10-117">IIS ManagementOData</span><span class="sxs-lookup"><span data-stu-id="c8b10-117">IIS-ManagementOData</span></span>

## <a name="steps-for-creating-a-management-odata-web-service"></a><span data-ttu-id="c8b10-118">Инструкции по созданию веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-118">Steps for creating a Management OData web service</span></span>

<span data-ttu-id="c8b10-119">Следующие разделы описывают создание и развертывание веб-службы OData для управления.</span><span class="sxs-lookup"><span data-stu-id="c8b10-119">The following topics describe how to create and deploy a Management OData web service.</span></span>

- [<span data-ttu-id="c8b10-120">Добавление ресурсов в OData веб-службы управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-120">Adding Resources to a Management OData Web Service</span></span>](./adding-resources-to-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-121">Авторизация на настраиваемый веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-121">Implementing Custom Authorization for a Management OData web service</span></span>](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-122">Реализация Конфигурациясеанса OData для управления веб-службы</span><span class="sxs-lookup"><span data-stu-id="c8b10-122">Implementing SessionConfiguration for a Management OData web service</span></span>](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-123">Создание схемы MOF-файл для веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-124">Создание файла схемы XML для веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-124">Authoring the XML schema file for a Management OData web service</span></span>](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-125">Создание файла Web.config для веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-125">Authoring the Web.config file for a Management OData web service</span></span>](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-126">Развертывание веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-126">Deploying a Management OData web service</span></span>](./deploying-a-management-odata-web-service.md)

- [<span data-ttu-id="c8b10-127">Связывание сущностей OData для управления</span><span class="sxs-lookup"><span data-stu-id="c8b10-127">Associating Management OData Entities</span></span>](./associating-management-odata-entities.md)

## <a name="see-also"></a><span data-ttu-id="c8b10-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c8b10-128">See Also</span></span>

[<span data-ttu-id="c8b10-129">Схема расширения ODATA IIS для управления файлами</span><span class="sxs-lookup"><span data-stu-id="c8b10-129">Management ODATA IIS Extension Schema Files</span></span>](./management-odata-iis-extension-schema-files.md)
