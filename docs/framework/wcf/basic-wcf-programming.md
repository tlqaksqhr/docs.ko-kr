---
title: "기본 WCF 프로그래밍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfcd0a09f247077f299d8b9c14a07bdc667245b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="15acf-102">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="15acf-102">Basic WCF Programming</span></span>
<span data-ttu-id="15acf-103">이 단원에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만들기 위한 기본 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-103">This section presents the fundamentals for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15acf-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="15acf-104">In This Section</span></span>  
 [<span data-ttu-id="15acf-105">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="15acf-105">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 <span data-ttu-id="15acf-106">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 및 클라이언트 응용 프로그램 디자인, 빌드 및 배포에 대한 수명 주기를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-106">Describes the lifecycle of designing, building, and deploying [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and client applications.</span></span>  
  
 [<span data-ttu-id="15acf-107">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="15acf-107">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 <span data-ttu-id="15acf-108">서비스 계약을 디자인 및 구현하고 메시지 교환 패턴을 선택하고 오류 계약 및 기타 서비스 기본 사항을 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>  
  
 [<span data-ttu-id="15acf-109">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="15acf-109">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 <span data-ttu-id="15acf-110">계약 요구 사항을 지원하고 로컬 런타임 동작을 사용자 지정하고 서비스를 게시할 주소를 표시하도록 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-110">Describes how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>  
  
 [<span data-ttu-id="15acf-111">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="15acf-111">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 <span data-ttu-id="15acf-112">응용 프로그램의 기본적인 호스팅 서비스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-112">Describes the basics of hosting services in an application.</span></span>  
  
 [<span data-ttu-id="15acf-113">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="15acf-113">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 <span data-ttu-id="15acf-114">서비스에서 메타데이터를 가져오고 해당 메타데이터를 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 코드로 변환하고 보안 문제를 처리하거나 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 빌드, 구성 및 호스팅하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-114">Describes how to obtain metadata from services, convert that into [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code, handle security issues, and build, configure, and host an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
 [<span data-ttu-id="15acf-115">확장성 소개</span><span class="sxs-lookup"><span data-stu-id="15acf-115">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
 <span data-ttu-id="15acf-116">사용자 지정 해결 방법을 만들기 위해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]를 확장하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-116">Describes how to extend [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] to create custom solutions.</span></span>  
  
 [<span data-ttu-id="15acf-117">WCF 문제 해결 퀵 스타트</span><span class="sxs-lookup"><span data-stu-id="15acf-117">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 <span data-ttu-id="15acf-118">발생하는 가장 일반적인 문제 중 일부, 이러한 문제를 해결하기 위해 수행할 수 있는 작업 및 문제에 대한 자세한 정보가 있는 위치에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>  
  
 [<span data-ttu-id="15acf-119">WCF 및 ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="15acf-119">WCF and ASP.NET Web API</span></span>](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)  
 <span data-ttu-id="15acf-120">두 가지 기술과 이러한 기술의 관계 및 사용 시기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15acf-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="15acf-121">참조</span><span class="sxs-lookup"><span data-stu-id="15acf-121">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="15acf-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="15acf-122">Related Sections</span></span>  
 [<span data-ttu-id="15acf-123">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="15acf-123">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)  
  
 [<span data-ttu-id="15acf-124">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="15acf-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="15acf-125">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="15acf-125">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="15acf-126">지침 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="15acf-126">Guidelines and Best Practices</span></span>](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
  
 [<span data-ttu-id="15acf-127">Windows Communication Foundation 도구</span><span class="sxs-lookup"><span data-stu-id="15acf-127">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
  
 [<span data-ttu-id="15acf-128">Windows Communication Foundation 샘플</span><span class="sxs-lookup"><span data-stu-id="15acf-128">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="15acf-129">시작</span><span class="sxs-lookup"><span data-stu-id="15acf-129">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
  
 [<span data-ttu-id="15acf-130">인라인 코드를 사용한 IIS 호스팅</span><span class="sxs-lookup"><span data-stu-id="15acf-130">IIS Hosting Using Inline Code</span></span>](../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)  
  
 [<span data-ttu-id="15acf-131">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="15acf-131">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
