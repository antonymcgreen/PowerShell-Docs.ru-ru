---
ms.date: 07/17/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxSshAuthorizedKeys в DSC для Linux
ms.openlocfilehash: 3a62bb7a3dbdebae4f0ca6084db1624c1b76ab1f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464474"
---
# <a name="dsc-for-linux-nxsshauthorizedkeys-resource"></a><span data-ttu-id="1bfb7-103">Ресурс nxSshAuthorizedKeys в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="1bfb7-103">DSC for Linux nxSshAuthorizedKeys Resource</span></span>

<span data-ttu-id="1bfb7-104">Ресурс **NxAuthorizedKeys** в DSC PowerShell обеспечивает механизм управления авторизованными SSH-ключами для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-104">The **nxAuthorizedKeys** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage authorized ssh keys for a specified user.</span></span>

## <a name="syntax"></a><span data-ttu-id="1bfb7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bfb7-105">Syntax</span></span>

```Syntax
nxAuthorizedKeys <string> #ResourceName
{
    KeyComment = <string>
    [ Username = <string> ]
    [ Key = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="1bfb7-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="1bfb7-106">Properties</span></span>

|<span data-ttu-id="1bfb7-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="1bfb7-107">Property</span></span> |<span data-ttu-id="1bfb7-108">Description</span><span class="sxs-lookup"><span data-stu-id="1bfb7-108">Description</span></span> |
|---|---|
|<span data-ttu-id="1bfb7-109">KeyComment</span><span class="sxs-lookup"><span data-stu-id="1bfb7-109">KeyComment</span></span> |<span data-ttu-id="1bfb7-110">Уникальный комментарий к ключу.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-110">A unique comment for the key.</span></span> <span data-ttu-id="1bfb7-111">Используется для уникальной идентификации ключей.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-111">This is used to uniquely identify keys.</span></span> |
|<span data-ttu-id="1bfb7-112">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="1bfb7-112">Username</span></span> |<span data-ttu-id="1bfb7-113">Указывает, для какого пользователя осуществляется управление авторизованными SSH-ключами.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-113">The username to manage ssh authorized keys for.</span></span> <span data-ttu-id="1bfb7-114">Если свойство не определено, пользователь по умолчанию — **root**.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-114">If not defined, the default user is **root**.</span></span> |
|<span data-ttu-id="1bfb7-115">Клавиши</span><span class="sxs-lookup"><span data-stu-id="1bfb7-115">Key</span></span> |<span data-ttu-id="1bfb7-116">Указывает содержимое ключа</span><span class="sxs-lookup"><span data-stu-id="1bfb7-116">The contents of the key.</span></span> <span data-ttu-id="1bfb7-117">Требуется, если свойство **Ensure** имеет значение **Present**.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-117">This is required if **Ensure** is set to **Present**.</span></span>|

## <a name="common-properties"></a><span data-ttu-id="1bfb7-118">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="1bfb7-118">Common properties</span></span>

|<span data-ttu-id="1bfb7-119">Свойство</span><span class="sxs-lookup"><span data-stu-id="1bfb7-119">Property</span></span> |<span data-ttu-id="1bfb7-120">Description</span><span class="sxs-lookup"><span data-stu-id="1bfb7-120">Description</span></span> |
|---|---|
|<span data-ttu-id="1bfb7-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1bfb7-121">DependsOn</span></span> |<span data-ttu-id="1bfb7-122">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1bfb7-123">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1bfb7-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="1bfb7-124">Ensure</span></span> |<span data-ttu-id="1bfb7-125">Указывает, определен ли ключ.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-125">Specifies whether the key is defined.</span></span> <span data-ttu-id="1bfb7-126">Если это свойство имеет значение **Absent**, обеспечивается отсутствие ключа в файле авторизованных ключей пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-126">Set this property to **Absent** to ensure the key does not exist in the user's authorized keys file.</span></span> <span data-ttu-id="1bfb7-127">Если это свойство имеет значение **Present**, обеспечивается наличие определения ключа в файле авторизованных ключей пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-127">Set it to **Present** to ensure the key is defined in the user's authorized key file.</span></span> |

## <a name="example"></a><span data-ttu-id="1bfb7-128">Пример</span><span class="sxs-lookup"><span data-stu-id="1bfb7-128">Example</span></span>

<span data-ttu-id="1bfb7-129">В следующем примере определяется общедоступный авторизованный SSH-ключ для пользователя monuser.</span><span class="sxs-lookup"><span data-stu-id="1bfb7-129">The following example defines a public ssh authorized key for the user "monuser".</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxSshAuthorizedKeys myKey
    {
        KeyComment = "myKey"
        Ensure = "Present"
        Key = 'ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEA0b+0xSd07QXRifm3FXj7Pn/DblA6QI5VAkDm6OivFzj3U6qGD1VJ6AAxWPCyMl/qhtpRtxZJDu/TxD8AyZNgc8aN2CljN1hOMbBRvH2q5QPf/nCnnJRaGsrxIqZjyZdYo9ZEEzjZUuMDM5HI1LA9B99k/K6PK2Bc1NLivpu7nbtVG2tLOQs+GefsnHuetsRMwo/+c3LtwYm9M0XfkGjYVCLO4CoFuSQpvX6AB3TedUy6NZ0iuxC0kRGg1rIQTwSRcw+McLhslF0drs33fw6tYdzlLBnnzimShMuiDWiT37WqCRovRGYrGCaEFGTG2e0CN8Co8nryXkyWc6NSDNpMzw== rsa-key-20150401'
        UserName = "monuser"
    }
}
```
