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
ms.openlocfilehash: f903c99300a34c0dfbed598738e96142588d69d9
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83691489"
---
# <a name="creating-a-management-odata-web-service"></a>Создание веб-службы управления OData

Расширение IIS ODATA для управления — это инфраструктура для создания конечной точки веб-службы ASP.NET, которая предоставляет доступ к данным управления, доступным через командлеты и скрипты Windows PowerShell, как сущности веб-службы OData. Это достигается путем обработки запросов OData и их преобразования в вызов Windows PowerShell. Группы разработчиков продукта могут создавать поверх этой инфраструктуры для создания конечных точек, предоставляющих определенные наборы данных управления.

Скачайте и установите образец [псвсролебаседплугинс](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) . Следуйте инструкциям по развертыванию веб-службы. Эта веб-служба предоставляет службы и процессы с помощью операций создания, чтения, обновления и удаления (CRUD). Запросы CRUD, выполненные в веб-службе, вызывают команды Windows PowerShell, выполняющие запрошенные операции. Сопоставление между операциями CRUD и базовыми командами Windows PowerShell реализуется двумя файлами схемы: schema. mof и Schema. XML. Файл Schema. mof использует стандарт [Distributed Management Task Force](https://www.dmtf.org/) (DMTF) Standard. Файл Schema. XML использует схему XML, описанную в разделе [схема сопоставления ресурсов](./resource-mapping-schema.md).

> [!IMPORTANT]
> Прежде чем включать расширение IIS ODATA для управления в Windows Server 2008 R2 с пакетом обновления 1 (SP1), необходимо включить следующие функции.
>
> 1. IIS — Вебсерверроле
> 2. IIS-WebServer
> 3. IIS-HttpTracing
> 4. IIS — Манажементодата

## <a name="steps-for-creating-a-management-odata-web-service"></a>Действия по созданию веб-службы OData управления

В следующих разделах описывается создание и развертывание веб-службы OData управления.

- [Добавление ресурсов в веб-службу управления OData](./adding-resources-to-a-management-odata-web-service.md)

- [Реализация пользовательской авторизации для веб-службы управления OData](./implementing-custom-authorization-for-a-management-odata-web-service.md)

- [Реализация SessionConfiguration для веб-службы управления OData](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

- [Создание файла схемы MOF для веб-службы управления OData](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

- [Создание файла схемы XML для веб-службы управления OData](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

- [Создание файла Web.config для веб-службы управления OData](./authoring-the-web-config-file-for-a-management-odata-web-service.md)

- [Развертывание веб-службы управления OData](./deploying-a-management-odata-web-service.md)

- [Связывание сущностей управления OData](./associating-management-odata-entities.md)

## <a name="see-also"></a>См. также:

[Файлы схемы расширения IIS ODATA для управления](./management-odata-iis-extension-schema-files.md)
