---
title: "WCF Data Services 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e66c26c12f3f62ee61e02e16318e747793ff927
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="d84e4-102">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="d84e4-102">Defining WCF Data Services</span></span>
<span data-ttu-id="d84e4-103">이 섹션을 만들고 구성 하는 방법을 설명 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 으로 데이터를 노출 하는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-103">This section describes how to create and configure [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d84e4-104">참조 데이터 서비스를 만드는 데 필요한 기본 단계 [서비스로 데이터 노출](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-104"> the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d84e4-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="d84e4-105">In This Section</span></span>  
 [<span data-ttu-id="d84e4-106">데이터 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="d84e4-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="d84e4-107">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 제공하는 데이터 서비스 구성 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-107">Describes the data service configuration options provided by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="d84e4-108">데이터 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="d84e4-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 <span data-ttu-id="d84e4-109">데이터를 데이터 서비스로 노출하기 위한 공급자 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-109">Describes the provider models for exposing data as a data service.</span></span>  
  
 [<span data-ttu-id="d84e4-110">서비스 작업</span><span class="sxs-lookup"><span data-stu-id="d84e4-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)  
 <span data-ttu-id="d84e4-111">서버에서 메서드를 노출하는 서비스 작업을 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-111">Describes how to define service operations that expose methods on the server.</span></span>  
  
 [<span data-ttu-id="d84e4-112">피드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d84e4-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)  
 <span data-ttu-id="d84e4-113">데이터 서비스 공급자에 의해 정의된 데이터 모델의 엔터티 및 데이터 피드의 요소 간에 매핑을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>  
  
 [<span data-ttu-id="d84e4-114">인터셉터</span><span class="sxs-lookup"><span data-stu-id="d84e4-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)  
 <span data-ttu-id="d84e4-115">데이터 서비스에 대한 요청에서 사용자 지정 비즈니스 논리를 수행하는 인터셉터 메서드를 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>  
  
 [<span data-ttu-id="d84e4-116">개발 및 WCF Data Services 배포</span><span class="sxs-lookup"><span data-stu-id="d84e4-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 <span data-ttu-id="d84e4-117">Visual Studio를 사용하여 데이터 서비스를 개발 및 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>  
  
 [<span data-ttu-id="d84e4-118">WCF Data Services 보안</span><span class="sxs-lookup"><span data-stu-id="d84e4-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 <span data-ttu-id="d84e4-119">데이터 서비스에 대한 인증 및 권한 부여와 기타 보안 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-119">Describes authentication and authorization for the data service and other security considerations.</span></span>  
  
 [<span data-ttu-id="d84e4-120">데이터 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="d84e4-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="d84e4-121">데이터 서비스용 호스트를 선택하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-121">Describes how to select a host for your data service.</span></span>  
  
 [<span data-ttu-id="d84e4-122">데이터 서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="d84e4-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)  
 <span data-ttu-id="d84e4-123">서로 다른 버전의 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]로 작업하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-123">Describes how to work with different versions of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span>  
  
 [<span data-ttu-id="d84e4-124">WCF Data Services 프로토콜 구현 정보</span><span class="sxs-lookup"><span data-stu-id="d84e4-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)  
 <span data-ttu-id="d84e4-125">현재 WCF Data Services로 구현되지 않은 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 프로토콜의 선택적 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d84e4-125">Describes optional functionalities of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol that are not currently implemented by WCF Data Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84e4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d84e4-126">See Also</span></span>  
 [<span data-ttu-id="d84e4-127">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="d84e4-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="d84e4-128">데이터 서비스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="d84e4-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [<span data-ttu-id="d84e4-129">시작</span><span class="sxs-lookup"><span data-stu-id="d84e4-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
