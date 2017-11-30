---
title: "Windows XP에 .NET Framework 설치"
description: "Windows XP에서.NET Framework를 설치하는 방법을 알아봅니다."
author: rlander
ms.author: mairaw
keywords: ".Net Framework, 설치"
ms.date: 08/03/2017
ms.topic: article
ms.prod: .net-framework
ms.devlang: dotnet
ms.openlocfilehash: f79ae387b123527b3795a2e12a68bd153b308f81
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="install-the-net-framework-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="a1987-104">Windows XP 및 Windows Server 2003에서.NET Framework를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-104">Install the .NET Framework on Windows XP and Windows Server 2003</span></span>

> [!NOTE]
> <span data-ttu-id="a1987-105">Windows XP는 Microsoft에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-105">Windows XP is no longer supported by Microsoft.</span></span> <span data-ttu-id="a1987-106">.NET Framework의 최신 버전을 포함 하 고 지원 되는 Windows 10으로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-106">We recommend you upgrade to Windows 10, which is supported and includes the latest version of the .NET Framework.</span></span> <span data-ttu-id="a1987-107">이 문서는 유용한 문제 해결 가이드로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-107">This document is provided solely as a helpful troubleshooting guide.</span></span>

<span data-ttu-id="a1987-108">.NET Framework가 Windows에서 많은 응용 프로그램을 실행 하려면 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-108">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="a1987-109">설치 하려면 다음 지침을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-109">You can use the following instructions to install it.</span></span> <span data-ttu-id="a1987-110">응용 프로그램을 실행 하 고 컴퓨터에 다음 대화 상자를 표시 한 후이 페이지에 도달한 메시지가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-110">You may have arrived on this page after trying to run an application and seeing the following dialog on your machine.</span></span>

![이 응용 프로그램을 시작할 수 없습니다.](./media/this-application-could-not-be-started.png)

<span data-ttu-id="a1987-112">이러한 지침은 필요한.NET Framework 버전을 설치 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-112">These instructions will help you install the .NET Framework versions you need.</span></span> <span data-ttu-id="a1987-113">[.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) 은 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-113">The [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) is the latest version.</span></span> <span data-ttu-id="a1987-114">Windows XP 및 Windows Server 2003에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-114">It is not supported on Windows XP and Windows Server 2003.</span></span> <span data-ttu-id="a1987-115">에 포함 되어는 [Windows 10 년 작성자 업데이트](https://www.microsoft.com/software-download/windows10) 및 [Windows Server 2016 버전 1709](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-115">It is included with the [Windows 10 Fall Creators Update](https://www.microsoft.com/software-download/windows10) and [Windows Server 2016 Version 1709](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709).</span></span>

## <a name="net-framework-403"></a><span data-ttu-id="a1987-116">.NET Framework 4.0.3</span><span class="sxs-lookup"><span data-stu-id="a1987-116">.NET Framework 4.0.3</span></span>

<span data-ttu-id="a1987-117">[.NET Framework 4.0.3](http://go.microsoft.com/fwlink/?LinkID=213834) 최신 지원 되는 버전이.NET Framework Windows XP 및 Windows Server 2003에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-117">The [.NET Framework 4.0.3](http://go.microsoft.com/fwlink/?LinkID=213834) is the latest supported .NET Framework version on Windows XP and Windows Server 2003.</span></span> <span data-ttu-id="a1987-118">.NET Framework 4.0.3을 사용하려면 먼저 [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-118">The .NET Framework 4.0.3 requires that the [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834) is installed first.</span></span> <span data-ttu-id="a1987-119">이러한 .NET Framework 버전은 둘 다 Microsoft에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-119">Both of these .NET Framework versions are no longer supported by Microsoft.</span></span>

## <a name="net-framework-4"></a><span data-ttu-id="a1987-120">.NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="a1987-120">.NET Framework 4</span></span>

<span data-ttu-id="a1987-121">Windows XP에는 [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-121">You can install the [.NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs) on Windows XP.</span></span> <span data-ttu-id="a1987-122">Microsoft에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-122">It's no longer supported by Microsoft.</span></span>

## <a name="net-framework-35"></a><span data-ttu-id="a1987-123">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="a1987-123">.NET Framework 3.5</span></span>

<span data-ttu-id="a1987-124">Windows XP에는 [.NET Framework 3.5](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-124">You can install the [.NET Framework 3.5](http://go.microsoft.com/fwlink/?LinkID=213834&dotnetdocs) on Windows XP.</span></span>

<span data-ttu-id="a1987-125">.NET Framework 3.5는 .NET Framework 1.0~3.5용으로 빌드된 응용 프로그램을 실행하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-125">The .NET Framework 3.5 can be used to run applications built for .NET Framework 1.0 through 3.5.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1987-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1987-126">See also</span></span>

<span data-ttu-id="a1987-127">[.NET Framework 다운로드](https://www.microsoft.com/net/download/framework?utm_source=ms-docs&utm_medium=referral) </span><span class="sxs-lookup"><span data-stu-id="a1987-127">[Download the .NET Framework](https://www.microsoft.com/net/download/framework?utm_source=ms-docs&utm_medium=referral) </span></span>  
<span data-ttu-id="a1987-128">[차단된 .NET Framework 설치 및 제거 문제 해결](troubleshoot-blocked-installations-and-uninstallations.md) </span><span class="sxs-lookup"><span data-stu-id="a1987-128">[Troubleshoot blocked .NET Framework installations and uninstallations](troubleshoot-blocked-installations-and-uninstallations.md) </span></span>  
[<span data-ttu-id="a1987-129">개발자를 위한.NET Framework를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1987-129">Install the .NET Framework for developers</span></span>](guide-for-developers.md)
