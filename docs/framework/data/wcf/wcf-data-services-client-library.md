---
title: "WCF Data Services 클라이언트 라이브러리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 65b02945aa81fdf18ad328a833f8f85744035871
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="00579-102">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="00579-102">WCF Data Services Client Library</span></span>
<span data-ttu-id="00579-103">HTTP 요청을 보내고 데이터 서비스에서 반환하는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드를 처리할 수 있는 응용 프로그램은 모두 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 데이터 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00579-103">Any application can interact with an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]-based data service if it can send an HTTP request and process the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that a data service returns.</span></span> <span data-ttu-id="00579-104">이 상호 운용성을 통해 광범위한 웹 사용 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00579-104">This interoperability enables you to access [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based services from a broad range of Web-enabled applications.</span></span> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="00579-105">사용할 때 다양 한 프로그래밍 환경을 제공 하는 클라이언트 라이브러리가 포함 되어 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] .NET Framework 또는 Silverlight 기반 응용 프로그램에서 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="00579-105"> includes client libraries that provide a richer programming experience when you consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="00579-106">클라이언트 라이브러리의 두 가지 주요 클래스는 <xref:System.Data.Services.Client.DataServiceContext> 클래스와 <xref:System.Data.Services.Client.DataServiceQuery%601> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="00579-106">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="00579-107"><xref:System.Data.Services.Client.DataServiceContext> 클래스는 지정한 데이터 서비스에 대해 지원되는 작업을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-107">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="00579-108">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스는 상태 비저장 특성을 갖지만 컨텍스트는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00579-108">Although [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] services are stateless, the context is not.</span></span> <span data-ttu-id="00579-109">따라서 사용할 수는 <xref:System.Data.Services.Client.DataServiceContext> 변경 관리 등의 기능을 지원 하기 위해 데이터 서비스와의 상호 작용 간에 클라이언트에서 상태를 유지 관리 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="00579-109">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="00579-110">또한 이 클래스는 ID를 관리하고 변경 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-110">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="00579-111"><xref:System.Data.Services.Client.DataServiceQuery%601> 클래스는 특정 엔터티 집합에 대한 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00579-111">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="00579-112">이 단원에서는 클라이언트 라이브러리를 사용하여 .NET Framework 클라이언트 응용 프로그램에서 데이터에 액세스하고 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-112">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="00579-113">사용 하는 방법에 대 한 자세한 내용은 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Silverlight 기반 응용 프로그램의 경우 클라이언트 라이브러리 참조 [WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=186016)합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-113">For more information about how to use the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=186016).</span></span> <span data-ttu-id="00579-114">다른 클라이언트 라이브러리를 사용할 수 있도록 하는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 다른 종류의 응용 프로그램에서 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="00579-114">Other client libraries are available that enable you to consume an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in other kinds of applications.</span></span> <span data-ttu-id="00579-115">자세한 내용은 참조는 [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796)합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-115">For more information, see the [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00579-116">단원 내용</span><span class="sxs-lookup"><span data-stu-id="00579-116">In This Section</span></span>  
 [<span data-ttu-id="00579-117">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="00579-117">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="00579-118">클라이언트 라이브러리와 기반으로 하는 클라이언트 데이터 서비스 클래스를 생성 하는 방법에 설명 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="00579-118">Describes how to generate a client library and client data service classes that are based on [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="00579-119">데이터 서비스 쿼리</span><span class="sxs-lookup"><span data-stu-id="00579-119">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="00579-120">클라이언트 라이브러리를 사용하여 .NET Framework 기반 응용 프로그램에서 데이터 서비스를 쿼리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-120">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="00579-121">지연 콘텐츠 로드</span><span class="sxs-lookup"><span data-stu-id="00579-121">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="00579-122">초기 쿼리 응답에 포함되지 않은 추가 콘텐츠를 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-122">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="00579-123">데이터 서비스 업데이트</span><span class="sxs-lookup"><span data-stu-id="00579-123">Updating the Data Service</span></span>](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="00579-124">클라이언트 라이브러리를 사용하여 엔터티와 관계를 만들고 수정 및 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-124">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="00579-125">비동기 작업</span><span class="sxs-lookup"><span data-stu-id="00579-125">Asynchronous Operations</span></span>](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="00579-126">비동기 방식으로 데이터 서비스와 작업할 수 있도록 클라이언트 라이브러리에서 제공하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-126">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="00579-127">일괄 처리 작업</span><span class="sxs-lookup"><span data-stu-id="00579-127">Batching Operations</span></span>](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 <span data-ttu-id="00579-128">클라이언트 라이브러리를 사용하여 여러 요청을 데이터 서비스에 단일 일괄 처리로 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-128">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="00579-129">컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="00579-129">Binding Data to Controls</span></span>](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="00579-130">컨트롤에 바인딩하는 방법에 설명 된 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 데이터 서비스에서 반환 된 피드의 합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-130">Describes how to bind controls to a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="00579-131">서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="00579-131">Calling Service Operations</span></span>](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="00579-132">클라이언트 라이브러리를 사용하여 서비스 작업을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-132">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="00579-133">데이터 서비스 컨텍스트 관리</span><span class="sxs-lookup"><span data-stu-id="00579-133">Managing the Data Service Context</span></span>](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="00579-134">클라이언트 라이브러리의 동작을 관리하는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-134">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="00579-135">이진 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="00579-135">Working with Binary Data</span></span>](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="00579-136">데이터 서비스에서 데이터 스트림으로 반환하는 이진 데이터에 액세스하고 해당 데이터를 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00579-136">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00579-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00579-137">See Also</span></span>  
 [<span data-ttu-id="00579-138">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="00579-138">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="00579-139">시작</span><span class="sxs-lookup"><span data-stu-id="00579-139">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
