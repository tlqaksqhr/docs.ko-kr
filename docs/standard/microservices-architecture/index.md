---
title: ".NET 마이크로 서비스. 컨테이너화된 .NET 응용 프로그램을 위한 아키텍처"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 전문"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f869656be4c211c9b028f8ac574eb3bf2de139e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
![](./media/cover.png)

# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="452cd-105">.NET 마이크로 서비스.</span><span class="sxs-lookup"><span data-stu-id="452cd-105">.NET Microservices.</span></span> <span data-ttu-id="452cd-106">컨테이너화된 .NET 응용 프로그램을 위한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="452cd-106">Architecture for Containerized .NET Applications</span></span>

<span data-ttu-id="452cd-107">다운로드 가능한 위치: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="452cd-107">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="452cd-108">게시자:</span><span class="sxs-lookup"><span data-stu-id="452cd-108">PUBLISHED BY</span></span>

<span data-ttu-id="452cd-109">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-109">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="452cd-110">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="452cd-110">A division of Microsoft Corporation</span></span>

<span data-ttu-id="452cd-111">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="452cd-111">One Microsoft Way</span></span>

<span data-ttu-id="452cd-112">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="452cd-112">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="452cd-113">Copyright © 2017 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="452cd-113">Copyright © 2017 by Microsoft Corporation</span></span>

<span data-ttu-id="452cd-114">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="452cd-114">All rights reserved.</span></span> <span data-ttu-id="452cd-115">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-115">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="452cd-116">이 가이드는 작성자의 견해와 의견을 “있는 그대로” 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-116">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="452cd-117">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-117">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="452cd-118">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-118">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="452cd-119">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-119">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="452cd-120">“상표” 웹 페이지의 http://www.microsoft.com에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-120">Microsoft and the trademarks listed at http://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="452cd-121">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-121">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="452cd-122">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-122">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="452cd-123">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-123">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="452cd-124">공동 작성자:</span><span class="sxs-lookup"><span data-stu-id="452cd-124">Co-Authors:</span></span>

> <span data-ttu-id="452cd-125">**Cesar de la Torre**, 선임 PM, Microsoft Corp. .NET 제품 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-125">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="452cd-126">**Bill Wagner**, 선임 콘텐츠 개발자, Microsoft Corp. C+E</span><span class="sxs-lookup"><span data-stu-id="452cd-126">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="452cd-127">**Mike Rousos**, 수석 소프트웨어 엔지니어, Microsoft DevDiv CAT 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-127">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="452cd-128">편집자:</span><span class="sxs-lookup"><span data-stu-id="452cd-128">Editors:</span></span>

> <span data-ttu-id="452cd-129">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="452cd-129">**Mike Pope**</span></span>
>
> <span data-ttu-id="452cd-130">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="452cd-130">**Steve Hoag**</span></span>

<span data-ttu-id="452cd-131">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="452cd-131">Participants and reviewers:</span></span>

> <span data-ttu-id="452cd-132">**Jeffrey Ritcher**, 파트너 소프트웨어 엔지니어, Microsoft Azure 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-132">**Jeffrey Ritcher**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="452cd-133">**Jimmy Bogard**, 최고 설계자, Headspring</span><span class="sxs-lookup"><span data-stu-id="452cd-133">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="452cd-134">**Udi Dahan**, 창립자 겸 CEO, Particular Software</span><span class="sxs-lookup"><span data-stu-id="452cd-134">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="452cd-135">**Jimmy Nilsson**, 공동 창립자 겸 CEO, Factor10</span><span class="sxs-lookup"><span data-stu-id="452cd-135">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="452cd-136">**Glenn Condron**, 선임 프로그램 관리자, ASP.NET 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-136">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="452cd-137">**Mark Fussell**, 수석 PM 리더, Microsoft Azure Service Fabric 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-137">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="452cd-138">**Diego Vega**, PM 리더, Microsoft Entity Framework 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-138">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="452cd-139">**Barry Dorrans**, 선임 보안 프로그램 관리자</span><span class="sxs-lookup"><span data-stu-id="452cd-139">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="452cd-140">**Rowan Miller**, 선임 프로그램 관리자, Microsoft</span><span class="sxs-lookup"><span data-stu-id="452cd-140">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="452cd-141">**Ankit Asthana**, 수석 PM 관리자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-141">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="452cd-142">**Scott Hunter**, 파트너 PM 책임자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-142">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="452cd-143">**Dylan Reisenberger**, 설계자 겸 개발자 리더, Polly</span><span class="sxs-lookup"><span data-stu-id="452cd-143">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="452cd-144">**Steve Smith**, 소프트웨어 기술자 겸 교육 담당자, ASPSmith Ltd.</span><span class="sxs-lookup"><span data-stu-id="452cd-144">**Steve Smith**, Software Craftsman & Trainer at ASPSmith Ltd.</span></span>
>
> <span data-ttu-id="452cd-145">**Ian Cooper**, 코딩 설계자, Brighter</span><span class="sxs-lookup"><span data-stu-id="452cd-145">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="452cd-146">**Unai Zorrilla**, 설계자 겸 개발자 리더, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="452cd-146">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="452cd-147">**Eduard Tomas**, 개발자 리더, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="452cd-147">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="452cd-148">**Ramon Tomas**, 개발자, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="452cd-148">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="452cd-149">**David Sanz**, 개발자, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="452cd-149">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="452cd-150">**Javier Valero**, 최고 운영 책임자, Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="452cd-150">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="452cd-151">**Pierre Millet**, 선임 컨설턴트, Microsoft</span><span class="sxs-lookup"><span data-stu-id="452cd-151">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="452cd-152">**Michael Friis**, 제품 관리자, Docker Inc</span><span class="sxs-lookup"><span data-stu-id="452cd-152">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="452cd-153">**Charles Lowell**, 소프트웨어 엔지니어, Microsoft VS CAT 팀</span><span class="sxs-lookup"><span data-stu-id="452cd-153">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="452cd-154">소개</span><span class="sxs-lookup"><span data-stu-id="452cd-154">Introduction</span></span>

<span data-ttu-id="452cd-155">기업은 컨테이너를 사용함으로써 점점 더 비용 절감을 실현하고, 배포 문제를 해결하며, DevOps 및 프로덕션 작업을 개선하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-155">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="452cd-156">Microsoft는 Azure Container Service 및 Azure Service Fabric과 같은 제품을 만들고 Docker, Mesosphere 및 Kubernetes와 같은 업계 선두 업체와 협력하여 Windows 및 Linux를 위한 컨테이너 혁신 제품을 출시해왔습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-156">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Container Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="452cd-157">이러한 제품은 기업이 선택한 플랫폼이나 도구와 상관없이 클라우드의 속도 및 규모로 응용 프로그램을 빌드 및 배포할 수 있도록 하는 컨테이너 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-157">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="452cd-158">Windows 및 Linux 에코시스템에서 가장 중요한 공급업체가 지원하는 Docker는 컨테이너 업계의 사실상 표준이 되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-158">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="452cd-159">(Microsoft는 Docker를 지원하는 주요 클라우드 공급업체 중 하나입니다.) 향후에는 아마도 클라우드 또는 온-프레미스의 어떤 데이터 센터에서나 Docker를 아주 흔히 볼 수 있게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-159">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="452cd-160">또한 [마이크로 서비스](https://martinfowler.com/articles/microservices.html) 아키텍처는 중요 업무용 분산 응용 프로그램을 위한 중요한 접근 방식으로 부상하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-160">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="452cd-161">마이크로 서비스 기반 아키텍처에서 응용 프로그램은 독립적으로 개발, 테스트, 배포 및 버전 지정할 수 있는 서비스 컬렉션을 기반으로 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-161">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="452cd-162">이 가이드의 내용</span><span class="sxs-lookup"><span data-stu-id="452cd-162">About this guide</span></span>

<span data-ttu-id="452cd-163">이 가이드는 마이크로 서비스 기반 응용 프로그램을 개발하고 컨테이너를 사용하여 해당 응용프로그램을 관리하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-163">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="452cd-164">또한 .NET Core 및 Docker 컨테이너를 사용하여 아키텍처를 설계 및 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-164">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="452cd-165">컨테이너 및 마이크로 서비스를 더 쉽게 ​​시작할 수 있도록 이 가이드는 탐색 가능한 참조 컨테이너화된 응용 프로그램 및 마이크로 서비스 기반 응용 프로그램에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-165">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="452cd-166">응용 프로그램 예제는 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub 리포지토리에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-166">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="452cd-167">이 가이드는 두 가지 기술 즉, Docker 및 .NET Core에 중점을 둔 개발 환경 수준에서 주로 기본적인 개발 및 아키텍처 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-167">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="452cd-168">이 가이드의 목적은 프로덕션 환경의 인프라(클라우드 또는 온-프레미스)에 집중하지 않고 응용 프로그램 디자인을 고려할 때 정보를 제공하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-168">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="452cd-169">인프라에 대한 결정은 나중에 프로덕션이 준비된 응용 프로그램을 만들 때 내립니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-169">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="452cd-170">따라서 이 가이드는 인프라와 관계없이 개발 환경 중심적으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-170">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="452cd-171">이 가이드를 살펴본 후에는 다음 단계로 Microsoft Azure에서 프로덕션이 준비된 마이크로 서비스에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="452cd-171">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="452cd-172">이 가이드에서 다루지 않는 내용</span><span class="sxs-lookup"><span data-stu-id="452cd-172">What this guide does not cover</span></span>

<span data-ttu-id="452cd-173">이 가이드는 응용 프로그램 수명 주기, DevOps, CI/CD 파이프라인 또는 팀 작업에 중점을 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-173">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="452cd-174">이러한 주제는 상호 보완적인 가이드인 [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook)에서 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-174">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="452cd-175">또한 현재 이 가이드는 특정 Orchestrator에 대한 정보와 같은 Azure 인프라에 대한 구현 세부 정보도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-175">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="452cd-176">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="452cd-176">Additional resources</span></span>

-   <span data-ttu-id="452cd-177">**Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기**(다운로드 가능한 전자책) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="452cd-177">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="452cd-178">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="452cd-178">Who should use this guide</span></span>

<span data-ttu-id="452cd-179">이 가이드는 Docker 기반 응용 프로그램 개발 및 마이크로 서비스 기반 아키텍처를 처음 접하는 개발자 및 솔루션 설계자를 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-179">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="452cd-180">이 가이드는 Microsoft 개발 기술(특히 .NET Core에 중점을 둠) 및 Docker 컨테이너를 사용하여 개념 증명 응용 프로그램을 설계, 디자인 및 구현하는 방법을 알아보려는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-180">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="452cd-181">또한 이 가이드는 새로운 최신 분산 응용 프로그램을 위해 어떤 접근 방식을 선택할지 결정하기 전에 먼저 아키텍처 및 기술에 대해 간략히 알아보려는 기술 의사 결정자(예: 엔터프라이즈 설계자)에게도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-181">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="452cd-182">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="452cd-182">How to use this guide</span></span>

<span data-ttu-id="452cd-183">이 가이드의 첫 번째 부분에서는 Docker 컨테이너를 소개하고, .NET Core와 .NET Framework 중에서 하나를 개발 프레임워크로 선택하는 방법에 대해 설명하고, 마이크로 서비스에 대해 간략하게 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-183">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="452cd-184">이 콘텐츠는 개요를 원하지만, 코드 구현 세부 정보에 집중할 필요가 없는 설계자 및 기술 의사 결정자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-184">This content is for architects and technical decision makers who want an overview but who do not need to focus on code implementation details.</span></span>

<span data-ttu-id="452cd-185">이 가이드의 두 번째 부분은 [Docker 기반 응용 프로그램의 개발 프로세스](#ch_dev_process_for_docker_based_apps) 섹션으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-185">The second part of the guide starts with the [Development process for Docker based applications](#ch_dev_process_for_docker_based_apps) section.</span></span> <span data-ttu-id="452cd-186">이 섹션은 .NET Core 및 Docker를 사용하여 응용 프로그램을 구현하기 위한 개발 및 마이크로 서비스 패턴에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-186">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="452cd-187">이 섹션은 코드와 패턴 및 구현 세부 정보에 중점을 두려는 개발자 및 설계자에게 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-187">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="452cd-188">관련 마이크로 서비스 및 컨테이너 기반 참조 응용 프로그램: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="452cd-188">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="452cd-189">eShopOnContainers 응용 프로그램은 Docker 컨테이너를 사용하여 배포되도록 설계된 .NET Core 및 마이크로 서비스용 참조 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-189">The eShopOnContainers application is a reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="452cd-190">이 응용 프로그램은 몇 가지 온라인 스토어 UI 프런트 엔드(웹앱 및 네이티브 모바일 앱)를 비롯한 여러 하위 시스템으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-190">The application consists of multiple subsystems, including several e-store UI front ends (a Web app and a native mobile app).</span></span> <span data-ttu-id="452cd-191">또한 필요한 모든 서버 쪽 작업을 위한 백 엔드 마이크로 서비스 및 컨테이너를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-191">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="452cd-192">이 마이크로 서비스 및 컨테이너 기반 응용 프로그램 소스 코드는 오픈 소스로, [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub 리포지토리에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-192">This microservice and container-based application source code is open source and available at the [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub repo.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="452cd-193">피드백을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="452cd-193">Send us your feedback!</span></span>

<span data-ttu-id="452cd-194">이 가이드는 .NET에서 컨테이너화된 응용 프로그램 및 마이크로 서비스의 아키텍처를 쉽게 이해할 수 있도록 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="452cd-194">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="452cd-195">가이드 및 관련 참조 응용 프로그램은 계속 발전할 예정이므로, 피드백이 있으시면 언제든지 보내주세요!</span><span class="sxs-lookup"><span data-stu-id="452cd-195">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="452cd-196">이 가이드의 개선 방안에 대한 의견이 있으시면 다음 주소로 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="452cd-196">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

>[!div class="step-by-step"]
<span data-ttu-id="452cd-197">[다음](container-docker-introduction/index.md)</span><span class="sxs-lookup"><span data-stu-id="452cd-197">[Next] (container-docker-introduction/index.md)</span></span>
