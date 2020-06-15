---
title: Введение
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: c48340b2fa6141d207c3f7948063f81971183780
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438225"
---
# <a name="introduction"></a><span data-ttu-id="ba41f-102">Введение</span><span class="sxs-lookup"><span data-stu-id="ba41f-102">Introduction</span></span>

<table>
  <tr><td>
  <a href="https://leanpub.com/powershell101">
  <img src="media/powershell101-150x194.png" alt="PowerShell 101 (the book)" />
  </a>
  </td>
  <td colspan=2>
<span data-ttu-id="ba41f-103">Этот материал был первоначально опубликован в книге <em>PowerShell 101</em> (Основы PowerShell) Майка Роббинса.</span><span class="sxs-lookup"><span data-stu-id="ba41f-103">This content originally appeared in the book <em>PowerShell 101</em> by Mike F Robbins.</span></span> <span data-ttu-id="ba41f-104">Мы благодарим Майка за возможность использовать его наработки в нашей документации.</span><span class="sxs-lookup"><span data-stu-id="ba41f-104">We thank Mike for granting us permission to reuse his content here.</span></span> <span data-ttu-id="ba41f-105">Содержимое было отредактировано.</span><span class="sxs-lookup"><span data-stu-id="ba41f-105">The content has been edited from the original publication.</span></span> <span data-ttu-id="ba41f-106">Сама книга <a href="https://leanpub.com/powershell101">PowerShell 101</a> доступна на сайте Leanpub.</span><span class="sxs-lookup"><span data-stu-id="ba41f-106">You can still get the original book from Leanpub at <a href="https://leanpub.com/powershell101">PowerShell 101</a>.</span></span>
  </td></tr>
</table>

## <a name="who-is-this-book-for"></a><span data-ttu-id="ba41f-107">Для кого предназначена эта книга?</span><span class="sxs-lookup"><span data-stu-id="ba41f-107">Who is this book for?</span></span>

<span data-ttu-id="ba41f-108">Это книга содержит вводные сведения и предназначена для всех желающих изучать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba41f-108">This is an entry-level book for anyone wanting to learn PowerShell.</span></span>

<span data-ttu-id="ba41f-109">В ней рассматривается оболочка PowerShell версии 5.1, работающая в Windows 10 и Windows Server 2016 в доменной среде Microsoft Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ba41f-109">This book focuses on PowerShell version 5.1 running on Windows 10 and Windows Server 2016 in a Microsoft Active Directory domain environment.</span></span> <span data-ttu-id="ba41f-110">Однако основные понятия применимы ко всем версиям PowerShell, выполняющимся на любой поддерживаемой платформе.</span><span class="sxs-lookup"><span data-stu-id="ba41f-110">However, the basic concepts apply to all versions of PowerShell running on any supported platform.</span></span>

## <a name="about-this-book"></a><span data-ttu-id="ba41f-111">Об этой книге</span><span class="sxs-lookup"><span data-stu-id="ba41f-111">About this book</span></span>

<span data-ttu-id="ba41f-112">В этой книге собрана информация, которую мне хотелось получить, когда я только начал изучать PowerShell, а также приведены советы, подсказки и рекомендации, которые стали мне известны на протяжении последних 10 лет использования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba41f-112">This book is a collection of what I wish someone would have told me when I started learning PowerShell, along with the tips, tricks, and best practices that I've learned while using PowerShell during the past 10 years.</span></span>

<span data-ttu-id="ba41f-113">Здесь нет огромных объемов информации — в этой книге предпринимается попытка предоставить столько данных, сколько будет достаточно для успешного начала работы с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba41f-113">Instead of providing an enormous amount of information, this book attempts to provide a balance of enough information to be successful for someone who is just getting started with PowerShell.</span></span> <span data-ttu-id="ba41f-114">Те, кому нужны более подробные сведения по темам, затрагиваемым в каждой главе, могут воспользоваться ссылками на соответствующие разделы справки.</span><span class="sxs-lookup"><span data-stu-id="ba41f-114">Each chapter contains links to specific help topics for those who want more information about the topics covered in that chapter.</span></span>

## <a name="about-the-author"></a><span data-ttu-id="ba41f-115">Об авторе</span><span class="sxs-lookup"><span data-stu-id="ba41f-115">About the author</span></span>

<span data-ttu-id="ba41f-116">Майк Роббинс — бывший Microsoft MVP, соавтор книг _Windows PowerShell TFM 4th Edition_ и _PowerShell Deep Dives_.</span><span class="sxs-lookup"><span data-stu-id="ba41f-116">Mike F Robbins is a former Microsoft MVP, co-author of _Windows PowerShell TFM 4th Edition_, and a contributing author in the _PowerShell Deep Dives_ book.</span></span> <span data-ttu-id="ba41f-117">Майк был решительным сторонником сообщества PowerShell, а сейчас является ведущим автором материалов по [Azure PowerShell][] в корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ba41f-117">Mike has been a strong supporter of the PowerShell community and is now the lead writer for [Azure PowerShell][] at Microsoft.</span></span> <span data-ttu-id="ba41f-118">Он ведет блоги на сайте [mikefrobbins.com][] и зарегистрирован в Twitter [@mikefrobbins][].</span><span class="sxs-lookup"><span data-stu-id="ba41f-118">He blogs at [mikefrobbins.com][] and can be found on twitter [@mikefrobbins][].</span></span>

## <a name="lab-environment"></a><span data-ttu-id="ba41f-119">Лабораторная среда</span><span class="sxs-lookup"><span data-stu-id="ba41f-119">Lab environment</span></span>

<span data-ttu-id="ba41f-120">Примеры в этой книге были разработаны и протестированы в Windows 10 Anniversary Edition (сборка 1607) и Windows Server 2016 с помощью PowerShell версии 5.1.</span><span class="sxs-lookup"><span data-stu-id="ba41f-120">The examples in this book were designed and tested on Windows 10 Anniversary Edition (build 1607) and Windows Server 2016 using PowerShell version 5.1.</span></span> <span data-ttu-id="ba41f-121">Если вы используете другую версию PowerShell или операционной системы, результаты могут отличаться от приведенных в этой документации.</span><span class="sxs-lookup"><span data-stu-id="ba41f-121">If you're using a different version of PowerShell or operating system, your results may differ from those shown here.</span></span>

<!-- link references -->
[@mikefrobbins]: https://twitter.com/mikefrobbins
[mikefrobbins.com]: http://mikefrobbins.com/
[PowerShell 101]: https://leanpub.com/powershell101
[Azure PowerShell]: /powershell/azure
