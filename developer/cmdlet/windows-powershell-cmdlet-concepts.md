---
title: Основные понятия Windows PowerShell командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b3ef3f4-c626-4679-884f-406a37412b3e
caps.latest.revision: 16
ms.openlocfilehash: 2f84c57da7429462c69b2a020d9f8ac04f8d0f35
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067085"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="ff169-102">Основные понятия, связанные с командлетами Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff169-102">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="ff169-103">В этом разделе описывается, как работают командлеты.</span><span class="sxs-lookup"><span data-stu-id="ff169-103">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff169-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="ff169-104">In This Section</span></span>

<span data-ttu-id="ff169-105">Этот раздел содержит следующие темы.</span><span class="sxs-lookup"><span data-stu-id="ff169-105">This section includes the following topics.</span></span>

<span data-ttu-id="ff169-106">[Рекомендации по разработке командлет](./cmdlet-development-guidelines.md) этот раздел содержит рекомендации по разработке, которые могут использоваться для создания правильного командлетов.</span><span class="sxs-lookup"><span data-stu-id="ff169-106">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="ff169-107">[Объявление класса командлет](./cmdlet-class-declaration.md) в этом разделе описывается объявление класса командлета.</span><span class="sxs-lookup"><span data-stu-id="ff169-107">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="ff169-108">[Утвержденные глаголы для Windows PowerShell команд](./approved-verbs-for-windows-powershell-commands.md) в этом разделе перечислены стандартные командлет команд, которые можно использовать при объявлении класса cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ff169-108">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="ff169-109">[Методы ввода обработки командлета](./cmdlet-input-processing-methods.md) в этом разделе описываются методы, позволяющие командлету, чтобы выполнять операции предварительной обработки, операции обработки ввода и публиковать операции обработки.</span><span class="sxs-lookup"><span data-stu-id="ff169-109">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="ff169-110">[Параметры командлета](./cmdlet-parameters.md) в этом разделе описываются различные типы параметров, которые можно добавить в командлетах.</span><span class="sxs-lookup"><span data-stu-id="ff169-110">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="ff169-111">[Атрибуты командлета](./cmdlet-attributes.md) в этом разделе описываются атрибуты, которые используются для объявления классов .NET Framework как командлеты, для объявления поля, что параметры командлета и объявить правила проверки входных данных для параметров.</span><span class="sxs-lookup"><span data-stu-id="ff169-111">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="ff169-112">[Псевдонимы командлетов](./cmdlet-aliases.md) в этом разделе описываются псевдонимы командлетов.</span><span class="sxs-lookup"><span data-stu-id="ff169-112">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="ff169-113">[Выходные данные командлета](./cmdlet-output.md) в этом разделе описывается тип выходных данных, который может возвращать командлеты и способы определения и отображения объектов, возвращаемых командлетами.</span><span class="sxs-lookup"><span data-stu-id="ff169-113">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="ff169-114">[Регистрация командлетов](./modules-and-snap-ins.md) в этом разделе описывается регистрация командлетов с помощью модулей и оснасток.</span><span class="sxs-lookup"><span data-stu-id="ff169-114">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="ff169-115">[Запрос на подтверждение](./requesting-confirmation-from-cmdlets.md) в этом разделе описывается, как командлеты запросит подтверждение от пользователя, перед внесением изменений в систему.</span><span class="sxs-lookup"><span data-stu-id="ff169-115">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="ff169-116">[Отчеты об ошибках Windows PowerShell](./error-reporting-concepts.md) в этом разделе описывается, как командлеты сообщают прерывающие ошибки и устранимые ошибки, и он описывает способ интерпретации записи об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ff169-116">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="ff169-117">[Фоновые задания](./background-jobs.md) в этом разделе описывается, как командлеты можно выполнять свою работу в рамках фоновых заданий, которые не конфликтуют с помощью команд, которые выполняются в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ff169-117">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="ff169-118">[Вызов командлетов и скриптов в командлет](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) в этом разделе описывается, каким образом командлеты можно вызывать другие командлеты и сценарии изнутри свои методы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="ff169-118">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="ff169-119">[Командлет задает](./cmdlet-sets.md) в этом разделе описывается использование базовых классов для создания наборов командлетов.</span><span class="sxs-lookup"><span data-stu-id="ff169-119">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="ff169-120">[Состояние сеанса Windows PowerShell](./windows-powershell-session-state.md) в этом разделе описаны состояния сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff169-120">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
