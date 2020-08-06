---
title: Основные понятия о командлетах Windows PowerShell | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 8c5462bbebd1be536b83854ca260592b841035fe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787756"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="64109-102">Основные понятия, связанные с командлетами Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64109-102">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="64109-103">В этом разделе описывается работа командлетов.</span><span class="sxs-lookup"><span data-stu-id="64109-103">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="64109-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="64109-104">In This Section</span></span>

<span data-ttu-id="64109-105">Этот раздел содержит следующие темы.</span><span class="sxs-lookup"><span data-stu-id="64109-105">This section includes the following topics.</span></span>

<span data-ttu-id="64109-106">[Рекомендации по разработке командлетов](./cmdlet-development-guidelines.md) В этом разделе приводятся рекомендации по разработке, которые можно использовать для создания командлетов правильного формата.</span><span class="sxs-lookup"><span data-stu-id="64109-106">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="64109-107">[Объявление класса командлета](./cmdlet-class-declaration.md) В этом разделе описывается объявление класса командлета.</span><span class="sxs-lookup"><span data-stu-id="64109-107">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="64109-108">[Утвержденные команды для команд Windows PowerShell](./approved-verbs-for-windows-powershell-commands.md) В этом разделе перечислены предопределенные команды командлета, которые можно использовать при объявлении класса командлета.</span><span class="sxs-lookup"><span data-stu-id="64109-108">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="64109-109">[Методы обработки входных данных командлета](./cmdlet-input-processing-methods.md) В этом разделе описываются методы, позволяющие командлету выполнять операции предварительной обработки, операции обработки входных данных и операции после обработки.</span><span class="sxs-lookup"><span data-stu-id="64109-109">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="64109-110">[Параметры командлета](./cmdlet-parameters.md) В этом разделе описываются различные типы параметров, которые можно добавить в командлеты.</span><span class="sxs-lookup"><span data-stu-id="64109-110">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="64109-111">[Атрибуты командлета](./cmdlet-attributes.md) В этом разделе описываются атрибуты, используемые для объявления классов .NET Framework в качестве командлетов, для объявления полей в качестве параметров командлетов, а также для объявления входных правил проверки для параметров.</span><span class="sxs-lookup"><span data-stu-id="64109-111">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="64109-112">[Псевдонимы командлетов](./cmdlet-aliases.md) В этом разделе описываются псевдонимы командлетов.</span><span class="sxs-lookup"><span data-stu-id="64109-112">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="64109-113">[Выходные данные командлета](./cmdlet-output.md) В этом разделе описывается тип выходных данных, которые могут возвращать командлеты, а также способы определения и отображения объектов, возвращаемых командлетами.</span><span class="sxs-lookup"><span data-stu-id="64109-113">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="64109-114">[Регистрация командлетов](./modules-and-snap-ins.md) В этом разделе описывается регистрация командлетов с помощью модулей и оснасток.</span><span class="sxs-lookup"><span data-stu-id="64109-114">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="64109-115">[Запрос подтверждения](./requesting-confirmation-from-cmdlets.md) В этом разделе описано, как командлеты запрашивают подтверждение от пользователя перед внесением изменений в систему.</span><span class="sxs-lookup"><span data-stu-id="64109-115">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="64109-116">[Отчеты об ошибках Windows PowerShell](./error-reporting-concepts.md) В этом разделе описывается, как командлеты сообщают о завершении ошибок и устранимых ошибках, а также описывает, как интерпретировать записи об ошибках.</span><span class="sxs-lookup"><span data-stu-id="64109-116">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="64109-117">[Фоновые задания](./background-jobs.md) В этом разделе описывается, как командлеты могут выполнять свою работу в фоновых заданиях, не мешающих командам, выполняемым в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="64109-117">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="64109-118">[Вызов командлетов и скриптов в командлете](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) В этом разделе описывается, как командлеты могут вызывать другие командлеты и скрипты из своих методов обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="64109-118">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="64109-119">[Наборы командлетов](./cmdlet-sets.md) В этом разделе описывается использование базовых классов для создания наборов командлетов.</span><span class="sxs-lookup"><span data-stu-id="64109-119">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="64109-120">[Состояние сеанса Windows PowerShell](./windows-powershell-session-state.md) В этом разделе описывается состояние сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64109-120">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
