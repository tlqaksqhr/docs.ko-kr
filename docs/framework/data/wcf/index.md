---
title: WCF Data Services 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8a0ab816aa21082cf98462f5f9d7ffd20e4dcfd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="10f03-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="10f03-102">WCF Data Services 4.5</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="10f03-103">(이전의 “ADO.NET Data Services”)는 [REST(Representational State Transfer)](http://go.microsoft.com/fwlink/?LinkId=113919)의 의미 체계를 사용하여 웹 또는 인트라넷을 통해 데이터를 노출하고 사용하기 위해 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]을 사용하는 서비스를 만들 수 있도록 하는 .NET Framework의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-103"> (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="10f03-104">는 URI로 주소를 지정할 수 있는 리소스로 데이터를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-104"> exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="10f03-105">데이터는 표준 HTTP 동사인 GET, PUT, POST 및 DELETE를 사용하여 액세스되고 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="10f03-106">는 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)의 엔터티-관계 규칙을 사용하여 리소스를 연결로 관련된 엔터티 집합으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-106"> uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="10f03-107">는 리소스 주소 지정 및 업데이트를 위해 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-107"> uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="10f03-108">이를 통해 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 지원하는 모든 클라이언트에서 이러한 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="10f03-109">를 사용하면 XML로 데이터를 교환 및 업데이트하기 위한 표준 집합인 Atom, AJAX 응용 프로그램에서 광범위하게 사용되는 텍스트 기반 데이터 교환 형식인 JSON(JavaScript Object Notation) 등 잘 알려진 전송 형식을 사용하여 리소스를 요청하고 리소스에 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-109"> enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="10f03-110">에서는 다양한 원본에서 제공되는 데이터를 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="10f03-111">Visual Studio 도구를 사용하면 ADO.NET Entity Framework 데이터 모델을 사용하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스를 보다 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="10f03-112">또한 CLR(공용 언어 런타임) 클래스와 런타임에 바인딩된 데이터나 형식화되지 않은 데이터를 기반으로 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="10f03-113">에는 일반 .NET Framework 클라이언트 응용 프로그램용 라이브러리와 Silverlight 기반 응용 프로그램용 라이브러리 등 클라이언트 라이브러리 집합도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-113"> also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="10f03-114">이러한 클라이언트 라이브러리는 .NET Framework 및 Silverlight와 같은 환경에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스할 때 개체 기반 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="10f03-115">시작 지점</span><span class="sxs-lookup"><span data-stu-id="10f03-115">Where Should I Start?</span></span>  
 <span data-ttu-id="10f03-116">가장 관심이 있는 항목에 따라 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 대한 다음 항목 중 하나에서 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="10f03-117">바로 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="10f03-118">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-119">시작</span><span class="sxs-lookup"><span data-stu-id="10f03-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-120">Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="10f03-121">Windows Phone 개발을 위한 Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="10f03-122">코드 보기</span><span class="sxs-lookup"><span data-stu-id="10f03-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="10f03-123">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-124">방법: 데이터 서비스 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="10f03-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-125">방법: Windows Presentation Foundation 요소에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="10f03-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="10f03-126">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="10f03-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="10f03-127">백서: OData 소개</span><span class="sxs-lookup"><span data-stu-id="10f03-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="10f03-128">Open Data Protocol 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="10f03-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="10f03-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="10f03-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="10f03-130">OData: 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="10f03-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="10f03-131">비디오 보기</span><span class="sxs-lookup"><span data-stu-id="10f03-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="10f03-132">WCF Data Services 초보자 가이드</span><span class="sxs-lookup"><span data-stu-id="10f03-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="10f03-133">WCF Data Services 개발자 비디오</span><span class="sxs-lookup"><span data-stu-id="10f03-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="10f03-134">OData: 개발자 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="10f03-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="10f03-135">종단 간 샘플</span><span class="sxs-lookup"><span data-stu-id="10f03-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="10f03-136">MSDN 샘플 갤러리의 WCF Data Services 설명서 샘플</span><span class="sxs-lookup"><span data-stu-id="10f03-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="10f03-137">MSDN 샘플 갤러리의 기타 WCF Data Services 샘플</span><span class="sxs-lookup"><span data-stu-id="10f03-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="10f03-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="10f03-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="10f03-139">Visual Studio와의 통합 방식</span><span class="sxs-lookup"><span data-stu-id="10f03-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="10f03-140">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="10f03-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-141">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="10f03-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="10f03-142">Entity Framework 공급자</span><span class="sxs-lookup"><span data-stu-id="10f03-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="10f03-143">수행 가능 작업</span><span class="sxs-lookup"><span data-stu-id="10f03-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="10f03-144">개요</span><span class="sxs-lookup"><span data-stu-id="10f03-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="10f03-145">백서: OData 소개</span><span class="sxs-lookup"><span data-stu-id="10f03-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="10f03-146">응용 프로그램 시나리오</span><span class="sxs-lookup"><span data-stu-id="10f03-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="10f03-147">Silverlight 사용</span><span class="sxs-lookup"><span data-stu-id="10f03-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="10f03-148">Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="10f03-149">WCF Data Services(Silverlight)</span><span class="sxs-lookup"><span data-stu-id="10f03-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="10f03-150">Silverlight 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="10f03-151">Windows Phone 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="10f03-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="10f03-152">Windows Phone 개발을 위한 Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="10f03-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="10f03-153">Windows Phone용 OData(Open Data Protocol) 클라이언트</span><span class="sxs-lookup"><span data-stu-id="10f03-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="10f03-154">LINQ 사용</span><span class="sxs-lookup"><span data-stu-id="10f03-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="10f03-155">데이터 서비스 쿼리</span><span class="sxs-lookup"><span data-stu-id="10f03-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-156">LINQ 고려 사항</span><span class="sxs-lookup"><span data-stu-id="10f03-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="10f03-157">방법: 데이터 서비스 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="10f03-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="10f03-158">추가 정보</span><span class="sxs-lookup"><span data-stu-id="10f03-158">I still need some more information…</span></span>  
 -   [<span data-ttu-id="10f03-159">WCF Data Services 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="10f03-159">WCF Data Services Team Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [<span data-ttu-id="10f03-160">리소스</span><span class="sxs-lookup"><span data-stu-id="10f03-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="10f03-161">WCF Data Services 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="10f03-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="10f03-162">Open Data Protocol 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="10f03-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="10f03-163">단원 내용</span><span class="sxs-lookup"><span data-stu-id="10f03-163">In This Section</span></span>  
 [<span data-ttu-id="10f03-164">개요</span><span class="sxs-lookup"><span data-stu-id="10f03-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="10f03-165">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 사용할 수 있는 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="10f03-166">WCF Data Services의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="10f03-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/en-us/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="10f03-167">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]의 새로운 기능과 새로운 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기능의 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="10f03-168">시작</span><span class="sxs-lookup"><span data-stu-id="10f03-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="10f03-169">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 사용하여 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 피드를 노출하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="10f03-170">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="10f03-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="10f03-171">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 노출하는 데이터 서비스를 만들고 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="10f03-172">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="10f03-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="10f03-173">클라이언트 라이브러리를 통해 .NET Framework 클라이언트 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10f03-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f03-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10f03-174">See Also</span></span>  
 [<span data-ttu-id="10f03-175">REST(Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="10f03-175">Representational State Transfer (REST)</span></span>](http://go.microsoft.com/fwlink/?LinkId=113919)
