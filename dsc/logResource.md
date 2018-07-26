---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс Log в DSC
ms.openlocfilehash: fade94efd8133ae0172737e4bb1aed89fc0f97d9
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093482"
---
# <a name="dsc-log-resource"></a><span data-ttu-id="4bc91-103">Ресурс Log в DSC</span><span class="sxs-lookup"><span data-stu-id="4bc91-103">DSC Log Resource</span></span>

> <span data-ttu-id="4bc91-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="4bc91-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="4bc91-105">Ресурс __Log__ в DSC Windows PowerShell предоставляет механизм записи сообщений в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.</span><span class="sxs-lookup"><span data-stu-id="4bc91-105">The __Log__ resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to write messages to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

> [!NOTE]
> <span data-ttu-id="4bc91-106">По умолчанию включены только операционные журналы DSC.</span><span class="sxs-lookup"><span data-stu-id="4bc91-106">By default only the Operational logs for DSC are enabled.</span></span> <span data-ttu-id="4bc91-107">Чтобы журнал аналитики стал доступным или видимым, его необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="4bc91-107">Before the Analytic log will be available or visible, it must be enabled.</span></span> <span data-ttu-id="4bc91-108">См. дополнительные сведения о [расположении журналов событий DSC](https://msdn.microsoft.com/en-us/powershell/dsc/troubleshooting#where-are-dsc-event-logs).</span><span class="sxs-lookup"><span data-stu-id="4bc91-108">For more information, see [Where are DSC Event Logs?](https://msdn.microsoft.com/en-us/powershell/dsc/troubleshooting#where-are-dsc-event-logs).</span></span>

## <a name="properties"></a><span data-ttu-id="4bc91-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="4bc91-109">Properties</span></span>

|  <span data-ttu-id="4bc91-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="4bc91-110">Property</span></span>  |  <span data-ttu-id="4bc91-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4bc91-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="4bc91-112">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4bc91-112">Message</span></span>| <span data-ttu-id="4bc91-113">Указывает сообщение для записи в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.</span><span class="sxs-lookup"><span data-stu-id="4bc91-113">Indicates the message you want to write to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>|
| <span data-ttu-id="4bc91-114">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4bc91-114">DependsOn</span></span> | <span data-ttu-id="4bc91-115">Указывает, что перед записью этого сообщения в журнал необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="4bc91-115">Indicates that the configuration of another resource must run before this log message gets written.</span></span> <span data-ttu-id="4bc91-116">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = '[ResourceType]ResourceName'`.</span><span class="sxs-lookup"><span data-stu-id="4bc91-116">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = '[ResourceType]ResourceName'`.</span></span>|

## <a name="example"></a><span data-ttu-id="4bc91-117">Пример</span><span class="sxs-lookup"><span data-stu-id="4bc91-117">Example</span></span>

<span data-ttu-id="4bc91-118">В следующем примере показано, как добавить сообщение в журнал событий Microsoft-Windows-Desired State Configuration/Analytic.</span><span class="sxs-lookup"><span data-stu-id="4bc91-118">The following example shows how to include a message in the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

> [!NOTE]
> <span data-ttu-id="4bc91-119">Если этот ресурс настроен, при выполнении командлета [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) всегда возвращается значение **$false**.</span><span class="sxs-lookup"><span data-stu-id="4bc91-119">If you run [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) with this resource configured, it will always return **$false**.</span></span>

```powershell
Configuration logResourceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost
    {
        Log LogExample
        {
            Message = 'This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log.'
        }
    }
}
```