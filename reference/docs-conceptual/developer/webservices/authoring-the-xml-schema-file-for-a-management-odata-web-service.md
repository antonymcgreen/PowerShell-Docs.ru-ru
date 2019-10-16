---
title: Создание файла схемы XML для веб-службы OData управления | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e83c9d9-6d06-4247-94d9-e3bfd4013b11
caps.latest.revision: 4
ms.openlocfilehash: a806d012097d107b6cc35710b9a93f2b27dd1ace
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359803"
---
# <a name="authoring-the-xml-schema-file-for-a-management-odata-web-service"></a><span data-ttu-id="d6cee-102">Создание файла схемы XML для веб-службы управления OData</span><span class="sxs-lookup"><span data-stu-id="d6cee-102">Authoring the XML schema file for a Management OData web service</span></span>

<span data-ttu-id="d6cee-103">После определения ресурсов, которые будет предоставлять веб-служба (см. раздел [Создание файла схемы MOF для веб-службы OData управления](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)), сопоставьте эти ресурсы с базовыми командлетами Windows PowerShell, которые реализуют поддерживаемые операции для каждого ресурс путем создания XML-файла, который соответствует [схеме сопоставления ресурсов](./resource-mapping-schema.md).</span><span class="sxs-lookup"><span data-stu-id="d6cee-103">After you define the resources your web service will expose (see [Authoring the MOF schema file for a Management OData web service](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)), you map those resources to the underlying Windows PowerShell cmdlets that implement the supported operations for each resource by creating an XML file that conforms to the [Resource Mapping Schema](./resource-mapping-schema.md).</span></span> <span data-ttu-id="d6cee-104">XML-файл также указывает URL-адреса, используемые клиентом для доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="d6cee-104">The XML file also specifies the URLs that are used by the client to access the resources.</span></span>

## <a name="mappng-resources-to-urls"></a><span data-ttu-id="d6cee-105">Маппнг ресурсы по URL-адресам</span><span class="sxs-lookup"><span data-stu-id="d6cee-105">Mappng resources to URLs</span></span>

<span data-ttu-id="d6cee-106">Первая часть XML-файла сопоставляет ресурсы, определенные в файле схемы MOF, с URL-адресами, используемыми для доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="d6cee-106">The first part of the XML file maps the resources defined in the MOF schema file to the URLs that are used to access them.</span></span> <span data-ttu-id="d6cee-107">В следующем примере показано сопоставление.</span><span class="sxs-lookup"><span data-stu-id="d6cee-107">The following example shows that mapping.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<ResourceMetadata xmlns="http://schemas.microsoft.com/powershell-web-services/2010/09">
    <SchemaNamespace>PswsTest</SchemaNamespace>
    <ContainerName>PSWSEntityContainer</ContainerName>
    <Resources>
        <Resource>
            <RelativeUrl>Service</RelativeUrl>
            <Class>PswsTest_Service</Class>
        </Resource>
        <Resource>
            <RelativeUrl>Process</RelativeUrl>
            <Class>PswsTest_Process</Class>
        </Resource>
    </Resources>
```

## <a name="mapping-cmdlets-to-crud-operations"></a><span data-ttu-id="d6cee-108">Сопоставление командлетов с операциями CRUD</span><span class="sxs-lookup"><span data-stu-id="d6cee-108">Mapping cmdlets to CRUD operations</span></span>

<span data-ttu-id="d6cee-109">Затем необходимо указать командлеты, соответствующие операциям CRUD (создание, чтение, обновление и удаление), которые поддерживаются ресурсами.</span><span class="sxs-lookup"><span data-stu-id="d6cee-109">You then specify the cmdlets that correspond to the CRUD (create, read, update, and delete) operations that the resources support.</span></span> <span data-ttu-id="d6cee-110">Операции CRUD в [схеме сопоставления ресурсов](./resource-mapping-schema.md)OData управления сопоставляются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d6cee-110">In the Management OData [Resource Mapping Schema](./resource-mapping-schema.md), the CRUD operations are mapped as follows.</span></span>

|<span data-ttu-id="d6cee-111">CRUD, команда</span><span class="sxs-lookup"><span data-stu-id="d6cee-111">CRUD command</span></span>|<span data-ttu-id="d6cee-112">XML-элемент</span><span class="sxs-lookup"><span data-stu-id="d6cee-112">XML element</span></span>|
|------------------|-----------------|
|<span data-ttu-id="d6cee-113">Создать</span><span class="sxs-lookup"><span data-stu-id="d6cee-113">Create</span></span>|<span data-ttu-id="d6cee-114">Создать</span><span class="sxs-lookup"><span data-stu-id="d6cee-114">Create</span></span>|
|<span data-ttu-id="d6cee-115">Чтение</span><span class="sxs-lookup"><span data-stu-id="d6cee-115">Read</span></span>|<span data-ttu-id="d6cee-116">Запрос</span><span class="sxs-lookup"><span data-stu-id="d6cee-116">Query</span></span>|
|<span data-ttu-id="d6cee-117">Обновление:</span><span class="sxs-lookup"><span data-stu-id="d6cee-117">Update</span></span>|<span data-ttu-id="d6cee-118">Обновление:</span><span class="sxs-lookup"><span data-stu-id="d6cee-118">Update</span></span>|
|<span data-ttu-id="d6cee-119">Удалить</span><span class="sxs-lookup"><span data-stu-id="d6cee-119">Delete</span></span>|<span data-ttu-id="d6cee-120">Удалить</span><span class="sxs-lookup"><span data-stu-id="d6cee-120">Delete</span></span>|

<span data-ttu-id="d6cee-121">В следующем примере показаны сопоставления для операций создания, чтения и обновления в ресурсе `Service`.</span><span class="sxs-lookup"><span data-stu-id="d6cee-121">The following example shows the mappings for the Create, Read, and Update operations on the `Service` resource.</span></span>

```xml
<ClassImplementations>
        <Class>
            <Name>PswsTest_Service</Name>
            <CmdletImplementation>
                <Query>
                    <Cmdlet>Get-Service</Cmdlet>
                        <FieldParameterMap>
                            <Field>
                                <FieldName>ServiceName</FieldName>
                                <ParameterName>Name</ParameterName>
                            </Field>
                        </FieldParameterMap>
                        <ParameterSets>
                            <ParameterSet>
                                <Name>Default</Name>
                                <Parameter><Name>Name</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Include</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Exclude</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ErrorVariable</Name></Parameter>
                                <Parameter><Name>WarningVariable</Name></Parameter>
                                <Parameter><Name>OutVariable</Name></Parameter>
                                <Parameter><Name>OutBuffer</Name></Parameter>
                            </ParameterSet>
                            <ParameterSet>
                                <Name>DisplayName</Name>
                                <Parameter><Name>DisplayName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Include</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Exclude</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ErrorVariable</Name></Parameter>
                                <Parameter><Name>WarningVariable</Name></Parameter>
                                <Parameter><Name>OutVariable</Name></Parameter>
                                <Parameter><Name>OutBuffer</Name></Parameter>
                            </ParameterSet>
                            <ParameterSet>
                                <Name>InputObject</Name>
                                <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Include</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>Exclude</Name><Type>System.String[]</Type></Parameter>
                                <Parameter><Name>ErrorVariable</Name></Parameter>
                                <Parameter><Name>WarningVariable</Name></Parameter>
                                <Parameter><Name>OutVariable</Name></Parameter>
                                <Parameter><Name>OutBuffer</Name></Parameter>
                        </ParameterSet>
                    </ParameterSets>
                </Query>
                <Update>
                    <Cmdlet>Set-Service</Cmdlet>
                    <FieldParameterMap>
                        <Field>
                            <FieldName>ServiceName</FieldName>
                            <ParameterName>Name</ParameterName>
                        </Field>
                    </FieldParameterMap>
                    <ParameterSets>
                        <ParameterSet>
                            <Name>Name</Name>
                            <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                            <Parameter><Name>Name</Name></Parameter>
                            <Parameter><Name>DisplayName</Name></Parameter>
                            <Parameter><Name>Description</Name></Parameter>
                            <Parameter><Name>Status</Name></Parameter>
                            <Parameter><Name>ErrorVariable</Name></Parameter>
                            <Parameter><Name>WarningVariable</Name></Parameter>
                            <Parameter><Name>OutVariable</Name></Parameter>
                            <Parameter><Name>OutBuffer</Name></Parameter>
                        </ParameterSet>
                        <ParameterSet>
                            <Name>InputObject</Name>
                            <Parameter><Name>ComputerName</Name><Type>System.String[]</Type></Parameter>
                            <Parameter><Name>DisplayName</Name></Parameter>
                            <Parameter><Name>Description</Name></Parameter>
                        </ParameterSet>
                    </ParameterSets>
                </Update>
                <Create>
                    <Cmdlet>New-Service</Cmdlet>
                    <FieldParameterMap>
                        <Field>
                            <FieldName>ServiceName</FieldName>
                            <ParameterName>Name</ParameterName>
                        </Field>
                    </FieldParameterMap>
                    <ParameterSets>
                        <ParameterSet>
                            <Name>__AllParameterSets</Name>
                            <Parameter><Name>BinaryPathName</Name></Parameter>
                            <Parameter><Name>Name</Name></Parameter>
                            <Parameter><Name>DisplayName</Name></Parameter>
                            <Parameter><Name>Description</Name></Parameter>
                            <Parameter><Name>DependsOn</Name></Parameter>
                            <Parameter><Name>ErrorVariable</Name></Parameter>
                            <Parameter><Name>WarningVariable</Name></Parameter>
                            <Parameter><Name>OutVariable</Name></Parameter>
                            <Parameter><Name>OutBuffer</Name></Parameter>
                        </ParameterSet>
                    </ParameterSets>
                </Create>
            </CmdletImplementation>
        </Class>
```

## <a name="see-also"></a><span data-ttu-id="d6cee-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6cee-122">See Also</span></span>

[<span data-ttu-id="d6cee-123">Создание файла схемы MOF для веб-службы OData управления</span><span class="sxs-lookup"><span data-stu-id="d6cee-123">Authoring the MOF schema file for a Management OData web service</span></span>](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[<span data-ttu-id="d6cee-124">Схема сопоставления ресурсов</span><span class="sxs-lookup"><span data-stu-id="d6cee-124">Resource Mapping Schema</span></span>](./resource-mapping-schema.md)

[<span data-ttu-id="d6cee-125">Создание веб-службы OData для управления</span><span class="sxs-lookup"><span data-stu-id="d6cee-125">Creating a Management OData Web Service</span></span>](./creating-a-management-odata-web-service.md)