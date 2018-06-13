---
title: ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계
description: ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계 | 소개
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.openlocfilehash: 57c2a598e48f855dd540b96c7ebdb522b4197b91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580265"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="d7645-103">ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계</span><span class="sxs-lookup"><span data-stu-id="d7645-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![표지 이미지](./media/cover.jpg)


<span data-ttu-id="d7645-105">.NET core 및 ASP.NET Core는 기존의.NET 개발에 비해 여러 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-105">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="d7645-106">다음 중 일부 또는 전부가 응용 프로그램의 성공에 중요한 경우 서버 응용 프로그램에 .NET Core를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-106">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="d7645-107">플랫폼 간 지원</span><span class="sxs-lookup"><span data-stu-id="d7645-107">Cross-platform support</span></span>

-   <span data-ttu-id="d7645-108">마이크로 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="d7645-108">Use of microservices</span></span>

-   <span data-ttu-id="d7645-109">Docker 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="d7645-109">Use of Docker containers</span></span>

-   <span data-ttu-id="d7645-110">고성능 및 확장성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7645-110">High performance and scalability requirements</span></span>

-   <span data-ttu-id="d7645-111">동일한 서버의 응용 프로그램에서 .NET 버전 병렬 관리</span><span class="sxs-lookup"><span data-stu-id="d7645-111">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="d7645-112">기존 .NET 응용 프로그램은 이러한 요구 사항을 지원할 수 있지만 ASP.NET Core 및 .NET Core는 위의 시나리오에 대한 향상된 지원을 제공하도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-112">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="d7645-113">점점 더 많은 조직에서 Microsoft Azure 같은 서비스를 사용하는 클라우드에 웹 응용 프로그램을 호스팅하기로 선택하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-113">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="d7645-114">응용 프로그램 또는 조직에 다음 사항이 중요한 경우 클라우드에서 응용 프로그램을 호스팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-114">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="d7645-115">데이터 센터 비용에 대한 투자 감소(하드웨어, 소프트웨어, 공간, 유틸리티 등)</span><span class="sxs-lookup"><span data-stu-id="d7645-115">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="d7645-116">유동적인 가격 책정(유휴 용량이 아닌 사용량을 기준으로 지불)</span><span class="sxs-lookup"><span data-stu-id="d7645-116">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="d7645-117">매우 뛰어난 안정성</span><span class="sxs-lookup"><span data-stu-id="d7645-117">Extreme reliability</span></span>

-   <span data-ttu-id="d7645-118">향상된 앱 이동성: 앱의 배포 위치와 방법을 쉽게 변경</span><span class="sxs-lookup"><span data-stu-id="d7645-118">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="d7645-119">유동적인 용량: 실제 요구 사항에 따라 규모 확장 또는 축소</span><span class="sxs-lookup"><span data-stu-id="d7645-119">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="d7645-120">Microsoft Azure에서 호스팅되는 ASP.NET Core 지원 웹 응용 프로그램을 구축하면 기존의 대안보다 수많은 경쟁적 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-120">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="d7645-121">ASP.NET Core는 현대식 웹 응용 프로그램 개발 사례 및 클라우드 호스팅 시나리오에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-121">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="d7645-122">이 가이드에서는 이러한 기능을 최대한 활용할 수 있도록 ASP.NET Core 응용 프로그램을 설계하는 방법에 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-122">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="d7645-123">용도</span><span class="sxs-lookup"><span data-stu-id="d7645-123">Purpose</span></span>

<span data-ttu-id="d7645-124">이 가이드에서는 ASP.NET Core 및 Azure를 사용하는 모놀리식 웹 응용 프로그램을 구축하는 방법에 대한 포괄적인 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-124">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="d7645-125">이 가이드는 기업 응용 프로그램을 호스팅하는 Docker, 마이크로 서비스 및 컨테이너 배포에 더욱 중점을 둔 "*Architecting and Developing Containerized and Microservice-based Applications with .NET*"(.NET을 사용하여 컨테이너화된, 마이크로 서비스 기반 응용 프로그램 설계 및 개발)을 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-125">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="d7645-126">.NET에서 컨테이너화된, 마이크로 서비스 기반 앱 설계 및 개발</span><span class="sxs-lookup"><span data-stu-id="d7645-126">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="d7645-127">**전자책**</span><span class="sxs-lookup"><span data-stu-id="d7645-127">**e-book**</span></span>  
> <http://aka.ms/MicroservicesEbook>
> - <span data-ttu-id="d7645-128">**예제 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="d7645-128">**Sample Application**</span></span>  
> <http://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="d7645-129">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="d7645-129">Who should use this guide</span></span>

<span data-ttu-id="d7645-130">이 가이드의 주요 대상 사용자는 클라우드에서 Microsoft 기술 및 서비스를 사용하여 현대식 웹 응용 프로그램을 구축하는 데 관심 있는 개발자, 개발 책임자 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-130">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="d7645-131">이차적인 대상 사용자는 이미 ASP.NET 및/또는 Azure에 익숙하고 신규 또는 기존 프로젝트를 위해 ASP.NET Core를 업그레이드하는 것이 적절한지에 관한 정보를 찾고 있는 기술 의사 결정권자입니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-131">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="d7645-132">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="d7645-132">How you can use this guide</span></span>

<span data-ttu-id="d7645-133">이 가이드는 현대식 .NET 기술 및 Windows Azure로 웹 응용 프로그램을 구축하는 방법에 중점을 둔, 비교적 작은 문서로 압축되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-133">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="d7645-134">따라서 전제적으로 읽어보면 이러한 응용 프로그램 및 해당 기술 고려 사항의 이해를 위한 기반을 마련할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-134">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="d7645-135">이 가이드와 응용 프로그램 예제는 출발점이나 참고 자료 역할도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-135">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="d7645-136">관련 응용 프로그램 예제를 자신의 응용 프로그램을 위한 템플릿으로 사용하거나 응용 프로그램의 구성 요소 부분을 구성하는 방법을 알아보는 용도로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d7645-136">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="d7645-137">자신의 응용 프로그램을 위한 옵션을 저울질할 때는 가이드의 원칙과 아키텍처 및 기술 옵션, 의사 결정 고려 사항에 대한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7645-137">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="d7645-138">이 가이드를 팀에게 자유롭게 전달하여 이러한 고려 사항 및 기회에 대한 공통적인 이해를 도모하세요.</span><span class="sxs-lookup"><span data-stu-id="d7645-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="d7645-139">모든 사람이 공통적인 용어 집합과 기본 원칙으로 작업하도록 하면 아키텍처 패턴과 방법의 일관적인 적용을 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7645-139">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="d7645-140">참조</span><span class="sxs-lookup"><span data-stu-id="d7645-140">References</span></span>
- <span data-ttu-id="d7645-141">**서버 앱에 대해 .NET Core와 .NET Framework 중에 선택**</span><span class="sxs-lookup"><span data-stu-id="d7645-141">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
<span data-ttu-id="d7645-142">[다음] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="d7645-142">[Next] (modern-web-applications-characteristics.md)</span></span>
