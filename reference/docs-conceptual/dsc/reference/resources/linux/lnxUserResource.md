---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс nxUser в DSC для Linux
ms.openlocfilehash: 6d7b52809741813af7fa80b1c6372b267aff4777
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954801"
---
# <a name="dsc-for-linux-nxuser-resource"></a><span data-ttu-id="62105-103">Ресурс nxUser в DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="62105-103">DSC for Linux nxUser Resource</span></span>

<span data-ttu-id="62105-104">Ресурс **nxUser** в DSC PowerShell предоставляет механизм управления локальными пользователями на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="62105-104">The **nxUser** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local users on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="62105-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62105-105">Syntax</span></span>

```Syntax
nxUser <string> #ResourceName
{
    UserName = <string>
    [ FullName = <string> ]
    [ Description = <string> ]
    [ Password = <string> ]
    [ Disabled = <bool> ]
    [ PasswordChangeRequired = <bool> ]
    [ HomeDirectory = <string> ]
    [ GroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="62105-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="62105-106">Properties</span></span>

|<span data-ttu-id="62105-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="62105-107">Property</span></span> |<span data-ttu-id="62105-108">Указывает имя учетной записи, для которой требуется обеспечить определенное состояние.</span><span class="sxs-lookup"><span data-stu-id="62105-108">Indicates the account name for which you want to ensure a specific state.</span></span> |
|---|---|
|<span data-ttu-id="62105-109">UserName</span><span class="sxs-lookup"><span data-stu-id="62105-109">UserName</span></span> |<span data-ttu-id="62105-110">Указывает, в каком расположении нужно проверить состояние файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="62105-110">Specifies the location where you want to ensure the state for a file or directory.</span></span> |
|<span data-ttu-id="62105-111">FullName</span><span class="sxs-lookup"><span data-stu-id="62105-111">FullName</span></span> |<span data-ttu-id="62105-112">Строка, содержащая полное имя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="62105-112">A string that contains the full name to use for the user account.</span></span> |
|<span data-ttu-id="62105-113">Описание</span><span class="sxs-lookup"><span data-stu-id="62105-113">Description</span></span> |<span data-ttu-id="62105-114">Описание учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="62105-114">The description for the user account.</span></span> |
|<span data-ttu-id="62105-115">Пароль</span><span class="sxs-lookup"><span data-stu-id="62105-115">Password</span></span> |<span data-ttu-id="62105-116">Хэш пароля пользователя в соответствующей форме для компьютера с Linux.</span><span class="sxs-lookup"><span data-stu-id="62105-116">The hash of the users password in the appropriate form for the Linux computer.</span></span> <span data-ttu-id="62105-117">Обычно это защищенный хэш SHA-256 или SHA-512.</span><span class="sxs-lookup"><span data-stu-id="62105-117">Typically, this is a salted SHA-256, or SHA-512 hash.</span></span> <span data-ttu-id="62105-118">В Debian и Ubuntu Linux это значение можно создать с помощью команды `mkpasswd`.</span><span class="sxs-lookup"><span data-stu-id="62105-118">On Debian and Ubuntu Linux, this value can be generated with the `mkpasswd` command.</span></span> <span data-ttu-id="62105-119">В других дистрибутивах Linux для создания хеша можно использовать метод шифрования криптографической библиотеки Python.</span><span class="sxs-lookup"><span data-stu-id="62105-119">For other Linux distros, the crypt method of Python's Crypt library can be used to generate the hash.</span></span> |
|<span data-ttu-id="62105-120">Отключен</span><span class="sxs-lookup"><span data-stu-id="62105-120">Disabled</span></span> |<span data-ttu-id="62105-121">Указывает, включено ли правило.</span><span class="sxs-lookup"><span data-stu-id="62105-121">Indicates whether the account is enabled.</span></span> <span data-ttu-id="62105-122">Присвойте этому свойству значение `$true`, чтобы отключить учетную запись, и `$false`, чтобы включить ее.</span><span class="sxs-lookup"><span data-stu-id="62105-122">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="62105-123">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="62105-123">PasswordChangeRequired</span></span> |<span data-ttu-id="62105-124">Указывает, может ли пользователь изменить пароль.</span><span class="sxs-lookup"><span data-stu-id="62105-124">Indicates whether the user can change the password.</span></span> <span data-ttu-id="62105-125">Присвойте этому свойству значение `$true`, чтобы пользователь не мог изменить пароль, и `$false`, чтобы мог.</span><span class="sxs-lookup"><span data-stu-id="62105-125">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="62105-126">Значение по умолчанию: `$false`.</span><span class="sxs-lookup"><span data-stu-id="62105-126">The default value is `$false`.</span></span> <span data-ttu-id="62105-127">Это свойство применяется только в том случае, если учетная запись пользователя ранее не существовала и находится в процессе создания.</span><span class="sxs-lookup"><span data-stu-id="62105-127">This property is only evaluated if the user account did not exist previously and is being created.</span></span> |
|<span data-ttu-id="62105-128">HomeDirectory</span><span class="sxs-lookup"><span data-stu-id="62105-128">HomeDirectory</span></span> |<span data-ttu-id="62105-129">Домашний каталог пользователя.</span><span class="sxs-lookup"><span data-stu-id="62105-129">The home directory for the user.</span></span> |
|<span data-ttu-id="62105-130">GroupID</span><span class="sxs-lookup"><span data-stu-id="62105-130">GroupID</span></span> |<span data-ttu-id="62105-131">ИД основной группы пользователя.</span><span class="sxs-lookup"><span data-stu-id="62105-131">The primary group ID for the user.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="62105-132">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="62105-132">Common properties</span></span>

|<span data-ttu-id="62105-133">Свойство</span><span class="sxs-lookup"><span data-stu-id="62105-133">Property</span></span> |<span data-ttu-id="62105-134">Описание</span><span class="sxs-lookup"><span data-stu-id="62105-134">Description</span></span> |
|---|---|
|<span data-ttu-id="62105-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="62105-135">DependsOn</span></span> |<span data-ttu-id="62105-136">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="62105-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="62105-137">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="62105-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="62105-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="62105-138">Ensure</span></span> |<span data-ttu-id="62105-139">Указывает, существует ли учетная запись.</span><span class="sxs-lookup"><span data-stu-id="62105-139">Specifies whether the account exists.</span></span> <span data-ttu-id="62105-140">Присвойте этому свойству значение **Present**, чтобы гарантировать, что учетная запись существует, и **Absent** в противном случае.</span><span class="sxs-lookup"><span data-stu-id="62105-140">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> |

## <a name="example"></a><span data-ttu-id="62105-141">Пример</span><span class="sxs-lookup"><span data-stu-id="62105-141">Example</span></span>

<span data-ttu-id="62105-142">В следующем примере проверяется, что пользователь monuser существует и является членом группы DBusers.</span><span class="sxs-lookup"><span data-stu-id="62105-142">The following example ensures that the user "monuser" exists and is a member of the group "DBusers".</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
   nxUser UserExample{
      UserName = "monuser"
      Description = "Monitoring user"
      Password  =    '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
      Ensure = "Present"
      HomeDirectory = "/home/monuser"
   }

   nxGroup GroupExample{
      GroupName = "DBusers"
      Ensure = "Present"
      MembersToInclude = "monuser"
      DependsOn = "[nxUser]UserExample"
   }
}
```