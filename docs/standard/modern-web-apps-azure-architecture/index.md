---
title: ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계
description: ASP.NET Core 및 Azure를 사용하여 모놀리식 웹 응용 프로그램을 빌드하는 방법에 대한 포괄적인 지침을 제공하는 가이드입니다.
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: e2d2545108b55043c322baffbd609b2422d2743b
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936986"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="982f1-103">ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계</span><span class="sxs-lookup"><span data-stu-id="982f1-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![표지 이미지](./media/cover.png)

<span data-ttu-id="982f1-105">게시자:</span><span class="sxs-lookup"><span data-stu-id="982f1-105">PUBLISHED BY</span></span>

<span data-ttu-id="982f1-106">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="982f1-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="982f1-107">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="982f1-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="982f1-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="982f1-108">One Microsoft Way</span></span>

<span data-ttu-id="982f1-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="982f1-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="982f1-110">Copyright © 2018 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="982f1-110">Copyright © 2018 by Microsoft Corporation</span></span>

<span data-ttu-id="982f1-111">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="982f1-111">All rights reserved.</span></span> <span data-ttu-id="982f1-112">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="982f1-113">이 가이드는 작성자의 견해와 의견을 “있는 그대로” 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="982f1-114">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="982f1-115">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="982f1-116">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="982f1-117">“상표” 웹 페이지의 https://www.microsoft.com에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="982f1-118">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="982f1-119">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="982f1-120">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="982f1-121">만든 이:</span><span class="sxs-lookup"><span data-stu-id="982f1-121">Author:</span></span>

> <span data-ttu-id="982f1-122">**Steve Smith(@ardalis)**, 소프트웨어 아키텍처 관리자, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="982f1-122">**Steve Smith (@ardalis)**, Software Architecture Advisor, [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="982f1-123">편집자:</span><span class="sxs-lookup"><span data-stu-id="982f1-123">Editors:</span></span>

> <span data-ttu-id="982f1-124">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="982f1-124">**Maira Wenzel**</span></span>

## <a name="introduction"></a><span data-ttu-id="982f1-125">소개</span><span class="sxs-lookup"><span data-stu-id="982f1-125">Introduction</span></span>

<span data-ttu-id="982f1-126">.NET core 및 ASP.NET Core는 기존의.NET 개발에 비해 여러 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-126">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="982f1-127">다음 중 일부 또는 전부가 응용 프로그램의 성공에 중요한 경우 서버 응용 프로그램에 .NET Core를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-127">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="982f1-128">플랫폼 간 지원</span><span class="sxs-lookup"><span data-stu-id="982f1-128">Cross-platform support.</span></span>

- <span data-ttu-id="982f1-129">마이크로 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="982f1-129">Use of microservices.</span></span>

- <span data-ttu-id="982f1-130">Docker 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="982f1-130">Use of Docker containers.</span></span>

- <span data-ttu-id="982f1-131">고성능 및 확장성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="982f1-131">High performance and scalability requirements.</span></span>

- <span data-ttu-id="982f1-132">동일한 서버의 응용 프로그램에서 .NET 버전 병렬 관리</span><span class="sxs-lookup"><span data-stu-id="982f1-132">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="982f1-133">기존 .NET 응용 프로그램은 이러한 요구 사항을 지원할 수 있지만 ASP.NET Core 및 .NET Core는 위의 시나리오에 대한 향상된 지원을 제공하도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-133">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="982f1-134">점점 더 많은 조직에서 Microsoft Azure 같은 서비스를 사용하는 클라우드에 웹 응용 프로그램을 호스팅하기로 선택하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-134">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="982f1-135">응용 프로그램 또는 조직에 다음 사항이 중요한 경우 클라우드에서 응용 프로그램을 호스팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-135">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="982f1-136">데이터 센터 비용에 대한 투자 감소(하드웨어, 소프트웨어, 공간, 유틸리티 등)</span><span class="sxs-lookup"><span data-stu-id="982f1-136">Reduced investment in data center costs (hardware, software, space, utilities, etc.)</span></span>

- <span data-ttu-id="982f1-137">유동적인 가격 책정(유휴 용량이 아닌 사용량을 기준으로 지불)</span><span class="sxs-lookup"><span data-stu-id="982f1-137">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="982f1-138">매우 뛰어난 안정성</span><span class="sxs-lookup"><span data-stu-id="982f1-138">Extreme reliability.</span></span>

- <span data-ttu-id="982f1-139">향상된 앱 이동성: 앱의 배포 위치와 방법을 쉽게 변경</span><span class="sxs-lookup"><span data-stu-id="982f1-139">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="982f1-140">유동적인 용량: 실제 요구 사항에 따라 규모 확장 또는 축소</span><span class="sxs-lookup"><span data-stu-id="982f1-140">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="982f1-141">Azure에서 호스팅되는 ASP.NET Core를 사용하여 웹 응용 프로그램을 빌드하면 기존의 대안보다 많은 경쟁적 이점을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-141">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="982f1-142">ASP.NET Core는 현대식 웹 응용 프로그램 개발 사례 및 클라우드 호스팅 시나리오에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-142">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="982f1-143">이 가이드에서는 이러한 기능을 최대한 활용할 수 있도록 ASP.NET Core 응용 프로그램을 설계하는 방법에 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-143">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="982f1-144">용도</span><span class="sxs-lookup"><span data-stu-id="982f1-144">Purpose</span></span>

<span data-ttu-id="982f1-145">이 가이드에서는 ASP.NET Core 및 Azure를 사용하는 모놀리식 웹 응용 프로그램을 구축하는 방법에 대한 포괄적인 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-145">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="982f1-146">이 가이드는 ["_.NET 마이크로 서비스를 보완합니다. 컨테이너화된 .NET 응용 프로그램_"](../microservices-architecture/index.md)의 아키텍처는 엔터프라이즈 응용 프로그램을 호스팅하는 Docker, 마이크로 서비스 및 컨테이너의 배포에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-146">This guide is complementary to the ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices-architecture/index.md) which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="982f1-147">.NET 마이크로 서비스.</span><span class="sxs-lookup"><span data-stu-id="982f1-147">.NET Microservices.</span></span> <span data-ttu-id="982f1-148">컨테이너화된 .NET 응용 프로그램을 위한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="982f1-148">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="982f1-149">**전자책**</span><span class="sxs-lookup"><span data-stu-id="982f1-149">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="982f1-150">**예제 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="982f1-150">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="982f1-151">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="982f1-151">Who should use this guide</span></span>

<span data-ttu-id="982f1-152">이 가이드의 주요 대상 사용자는 클라우드에서 Microsoft 기술 및 서비스를 사용하여 현대식 웹 응용 프로그램을 구축하는 데 관심 있는 개발자, 개발 책임자 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-152">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="982f1-153">이차적인 대상 사용자는 이미 ASP.NET 또는 Azure에 익숙하고 신규 또는 기존 프로젝트를 위해 ASP.NET Core를 업그레이드하는 것이 적절한지에 관한 정보를 찾고 있는 기술 의사 결정권자입니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-153">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="982f1-154">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="982f1-154">How you can use this guide</span></span>

<span data-ttu-id="982f1-155">이 가이드는 현대식 .NET 기술 및 Windows Azure로 웹 응용 프로그램을 구축하는 방법에 중점을 둔, 비교적 작은 문서로 압축되었습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-155">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="982f1-156">따라서 전제적으로 읽어보면 이러한 응용 프로그램 및 해당 기술 고려 사항의 이해를 위한 기반을 마련할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-156">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="982f1-157">이 가이드와 응용 프로그램 예제는 출발점이나 참고 자료 역할도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-157">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="982f1-158">관련 응용 프로그램 예제를 자신의 응용 프로그램을 위한 템플릿으로 사용하거나 응용 프로그램의 구성 요소 부분을 구성하는 방법을 알아보는 용도로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="982f1-158">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="982f1-159">자신의 응용 프로그램을 위한 옵션을 저울질할 때는 가이드의 원칙과 아키텍처 및 기술 옵션, 의사 결정 고려 사항에 대한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="982f1-159">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="982f1-160">이 가이드를 팀에게 자유롭게 전달하여 이러한 고려 사항 및 기회에 대한 공통적인 이해를 도모하세요.</span><span class="sxs-lookup"><span data-stu-id="982f1-160">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="982f1-161">모든 사람이 공통적인 용어 집합과 기본 원칙으로 작업하도록 하면 아키텍처 패턴과 방법의 일관적인 적용을 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="982f1-161">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="982f1-162">참조</span><span class="sxs-lookup"><span data-stu-id="982f1-162">References</span></span>

- <span data-ttu-id="982f1-163">**서버 앱에 대해 .NET Core와 .NET Framework 중에 선택**</span><span class="sxs-lookup"><span data-stu-id="982f1-163">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
[<span data-ttu-id="982f1-164">다음</span><span class="sxs-lookup"><span data-stu-id="982f1-164">Next</span></span>](modern-web-applications-characteristics.md)
