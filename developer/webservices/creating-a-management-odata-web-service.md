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
# <a name="creating-a-management-odata-web-service"></a>Создание веб-службы управления OData

Расширение IIS ODATA для управления — это инфраструктура для создания ASP.NET web конечной точки службы, предоставляющей данные управления, через командлеты Windows PowerShell и сценариев, как сущности службы веб-OData. Он делает это путем обработки запросов OData и преобразовывая их в вызове в Windows PowerShell. Группы разработки продуктов можно создавать на основе этой инфраструктуры для создания конечных точек, которые предоставляют определенные наборы данных управления.

Скачайте и установите [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) образца. Следуйте инструкциям для развертывания веб-службы. Этот веб-служба предоставляет служб и процессов с помощью операций создания, чтения, обновления и удаления (CRUD). CRUD, запросы к веб-службы вызова команд Windows PowerShell, выполнения запрошенных операций. Сопоставление операции CRUD и базовые команды Windows PowerShell реализуется файлы две схемы, schema.mof и schema.xml. Schema.MOF-файл использует [Distributed Management Task Force](https://www.dmtf.org/) standard (DMTF) управляемого объекта (MOF). Файл schema.xml использует схему XML, описанной в [схема сопоставления ресурсов](./resource-mapping-schema.md).

> [!IMPORTANT]
> Прежде чем включить расширение IIS ODATA для управления на Windows Server 2008 R2 SP1 необходимо включить следующие функции.
>
> 1.  IIS-WebServerRole
> 2.  IIS-WebServer
> 3.  IIS-HttpTracing
> 4.  IIS ManagementOData

## <a name="steps-for-creating-a-management-odata-web-service"></a>Инструкции по созданию веб-службы OData для управления

Следующие разделы описывают создание и развертывание веб-службы OData для управления.

- [Добавление ресурсов в OData веб-службы управления](./adding-resources-to-a-management-odata-web-service.md)

- [Авторизация на настраиваемый веб-службы OData для управления](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [Реализация Конфигурациясеанса OData для управления веб-службы](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [Создание схемы MOF-файл для веб-службы OData для управления](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [Создание файла схемы XML для веб-службы OData для управления](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [Создание файла Web.config для веб-службы OData для управления](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [Развертывание веб-службы OData для управления](./deploying-a-management-odata-web-service.md)

- [Связывание сущностей OData для управления](./associating-management-odata-entities.md)

## <a name="see-also"></a>См. также

[Схема расширения ODATA IIS для управления файлами](./management-odata-iis-extension-schema-files.md)
