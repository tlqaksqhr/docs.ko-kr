---
title: "WCF 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 14f2aa18b1fba92f5559b463d90dcfb5b34e2a3f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="ea828-102">WCF 배포</span><span class="sxs-lookup"><span data-stu-id="ea828-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ea828-103">에서는 Atom, RSS 또는 기타 사용자 지정 형식의 배포 피드를 쉽게 사용하는 것이 지원되므로 이러한 배포 피드를 읽고 만들 수 있을 뿐만 아니라 서비스 끝점에서 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="ea828-104">이 단원의 항목에서는 배포에 대한 이 프로그래밍 모델에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea828-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ea828-105">In This Section</span></span>  
 [<span data-ttu-id="ea828-106">WCF 배포 개요</span><span class="sxs-lookup"><span data-stu-id="ea828-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="ea828-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 배포 지원에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="ea828-108">배포 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ea828-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="ea828-109">개체 모델의 클래스와 배포 확장성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="ea828-110">WCF 배포 개체 모델을 Atom 및 RSS에 매핑되는 방법을</span><span class="sxs-lookup"><span data-stu-id="ea828-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="ea828-111">피드를 WCF 배포 개체 모델로 등록하는 방법과 RSS 및 Atom 피드로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="ea828-112">방법: 기본 RSS 피드 만들기</span><span class="sxs-lookup"><span data-stu-id="ea828-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="ea828-113">기본 RSS 피드를 사용 가능하도록 지정하는 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="ea828-114">방법: 기본 Atom 피드 만들기</span><span class="sxs-lookup"><span data-stu-id="ea828-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="ea828-115">기본 ATOM 피드를 사용 가능하도록 지정하는 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="ea828-116">방법: 두 Atom로 피드 공개 및 RSS</span><span class="sxs-lookup"><span data-stu-id="ea828-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="ea828-117">ATOM 및 RSS에서 동일한 피드를 사용 가능하도록 지정하는 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="ea828-118">배포 확장성</span><span class="sxs-lookup"><span data-stu-id="ea828-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="ea828-119">사용자 지정 요소와 특성을 배포 피드에 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea828-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ea828-120">참조</span><span class="sxs-lookup"><span data-stu-id="ea828-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ea828-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ea828-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea828-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea828-122">See Also</span></span>  
 [<span data-ttu-id="ea828-123">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="ea828-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="ea828-124">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="ea828-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
