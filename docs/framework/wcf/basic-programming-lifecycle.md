---
title: "기본 프로그래밍 수명 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f17b37b77c157f1ce3d5ee40fd6464ab378039d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="0c4a8-102">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="0c4a8-102">Basic Programming Lifecycle</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="0c4a8-103">를 사용하면 응용 프로그램들이 같은 컴퓨터에 있든지, 인터넷을 통해 연결되어 있든지 아니면 서로 다른 응용 프로그램 플랫폼에 있든지 상관없이 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-103"> enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="0c4a8-104">이 항목에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램을 빌드하는 데 필요한 작업에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="0c4a8-105">작업 샘플 응용 프로그램에 대 한 참조 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="0c4a8-106">기본 작업</span><span class="sxs-lookup"><span data-stu-id="0c4a8-106">The Basic Tasks</span></span>  
 <span data-ttu-id="0c4a8-107">수행할 기본 작업 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="0c4a8-108">서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-108">Define the service contract.</span></span> <span data-ttu-id="0c4a8-109">서비스 계약은 서비스 서명, 서비스 교환 날짜 및 계약에 필요한 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="0c4a8-110">[서비스 계약을 디자인](../../../docs/framework/wcf/designing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-110"> [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="0c4a8-111">계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-111">Implement the contract.</span></span> <span data-ttu-id="0c4a8-112">서비스 계약을 구현하려면 계약을 구현하는 클래스를 만들고 런타임에 필요한 사용자 지정 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="0c4a8-113">[서비스 계약 구현](../../../docs/framework/wcf/implementing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-113"> [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="0c4a8-114">끝점 및 기타 동작 정보를 지정하여 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-114">Configure the service by specifying endpoints and other behavior information.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="0c4a8-115">[서비스 구성](../../../docs/framework/wcf/configuring-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-115"> [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="0c4a8-116">서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-116">Host the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="0c4a8-117">[호스팅 서비스](../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-117"> [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="0c4a8-118">클라이언트 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-118">Build a client application.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="0c4a8-119">[클라이언트 빌드](../../../docs/framework/wcf/building-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-119"> [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="0c4a8-120">이 단원의 항목은 이 순서를 따르지만 일부 시나리오에서는 첫 번째 단계부터 시작하지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="0c4a8-121">예를 들어 기존 서비스에 대한 클라이언트를 빌드하려면 5단계에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="0c4a8-122">다른 사용자가 사용할 서비스를 빌드하는 경우 5단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="0c4a8-123">읽을 수도 있습니다 개발 하는 서비스 계약에 잘 알고 있다면 [확장성 소개](../../../docs/framework/wcf/introduction-to-extensibility.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="0c4a8-124">서비스에 문제가 있는 경우 확인 [WCF 문제 해결 퀵 스타트](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) 동일 하거나 유사한 문제가 있는 다른 지 여부를 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="0c4a8-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4a8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c4a8-125">See Also</span></span>  
 [<span data-ttu-id="0c4a8-126">서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="0c4a8-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
