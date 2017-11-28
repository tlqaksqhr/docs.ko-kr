---
title: "사용자 지정 데이터 서비스 공급자(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 90e837739edc74ee469f42720f52789ee1c8f6fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a><span data-ttu-id="ca2c1-102">사용자 지정 데이터 서비스 공급자(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ca2c1-102">Custom Data Service Providers (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ca2c1-103">에 포함된 공급자 집합을 사용하면 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-103"> includes a set of providers that enables you to define a data model based on late-bound data types.</span></span>  
  
|<span data-ttu-id="ca2c1-104">공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-104">Provider</span></span>|<span data-ttu-id="ca2c1-105">설명</span><span class="sxs-lookup"><span data-stu-id="ca2c1-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ca2c1-106">메타데이터 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-106">Metadata provider</span></span>|<span data-ttu-id="ca2c1-107">이 공급자는 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 구현하여 런타임에 사용자 지정 데이터 모델을 정의할 수 있도록 하는 핵심 사용자 지정 데이터 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-107">This is the core custom data service provider that enables you to define a custom data model at runtime by implementing the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span>|  
|<span data-ttu-id="ca2c1-108">쿼리 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-108">Query provider</span></span>|<span data-ttu-id="ca2c1-109">이 공급자를 사용하면 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 사용하여 정의된 사용자 지정 데이터 모델에 대해 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-109">This provider enables you to execute queries against a custom data model that is defined by using the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span> <span data-ttu-id="ca2c1-110">쿼리 공급자는 <xref:System.Data.Services.Providers.IDataServiceQueryProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-110">The query provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceQueryProvider> interface.</span></span>|  
|<span data-ttu-id="ca2c1-111">업데이트 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-111">Update provider</span></span>|<span data-ttu-id="ca2c1-112">이 공급자를 사용하면 사용자 지정 데이터 서비스 공급자에 노출된 형식을 업데이트하고 동시성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-112">This provider enables you to make updates to types that are exposed in a custom data service provider and to manage concurrency.</span></span> <span data-ttu-id="ca2c1-113">업데이트 공급자는 <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-113">An update provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> interface</span></span>|  
|<span data-ttu-id="ca2c1-114">페이징 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-114">Paging provider</span></span>|<span data-ttu-id="ca2c1-115">이 공급자는 사용자 지정 데이터 서비스 공급자와 함께 사용되어 서버 기반 페이징 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-115">This provider is used with the custom data service provider to enable server-driven paging support.</span></span> <span data-ttu-id="ca2c1-116">사용자 지정 데이터 서비스용 페이징 공급자는 <xref:System.Data.Services.Providers.IDataServicePagingProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-116">A paging provider for a custom data service is created by implementing the <xref:System.Data.Services.Providers.IDataServicePagingProvider> interface.</span></span>|  
|<span data-ttu-id="ca2c1-117">스트리밍 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-117">Streaming provider</span></span>|<span data-ttu-id="ca2c1-118">이 공급자를 사용하면 BLOB(Binary Large Object) 데이터 형식을 스트림으로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-118">This provider enables you to expose binary large object data types as a stream.</span></span> <span data-ttu-id="ca2c1-119">스트리밍 공급자는 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-119">A streaming provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceStreamProvider> interface.</span></span> <span data-ttu-id="ca2c1-120">스트리밍 공급자는 Entity Framework 및 리플렉션 데이터 소스 공급자와 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-120">The streaming provider can also be used with Entity Framework and reflection data source providers.</span></span> <span data-ttu-id="ca2c1-121">자세한 내용은 참조 [스트리밍 공급자](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-121">For more information, see [Streaming Provider](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).</span></span>|  
  
 <span data-ttu-id="ca2c1-122">자세한 내용은 문서 참조 [사용자 지정 데이터 서비스 공급자](http://go.microsoft.com/fwlink/?LinkID=186850) 및 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 공급자 도구 키트는 [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2c1-122">For more information, see the article [Custom Data Service Providers](http://go.microsoft.com/fwlink/?LinkID=186850) and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Provider Toolkit in the [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2c1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca2c1-123">See Also</span></span>  
 [<span data-ttu-id="ca2c1-124">데이터 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-124">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="ca2c1-125">Entity Framework 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-125">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [<span data-ttu-id="ca2c1-126">리플렉션 공급자</span><span class="sxs-lookup"><span data-stu-id="ca2c1-126">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
