---
title: "워크플로 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8eeb446687b2aa75c90ec02995319fc5a0cbebf3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-services"></a><span data-ttu-id="c096f-102">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="c096f-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="c096f-103">에서는 XAML을 사용하여 워크플로 기반 서비스를 선언적으로 자세히 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-103"> allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="c096f-104">즉, XAML을 사용하여 서비스를 구현하는 워크플로를 정의하고 서비스가 노출하는 끝점을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="c096f-105">이 단원의 항목에서는 선언적 방식의 서비스 작성을 지원하는 프로그래밍 모델에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c096f-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c096f-106">In This Section</span></span>  
 [<span data-ttu-id="c096f-107">워크플로 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="c096f-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="c096f-108">워크플로 서비스를 만들고 호스팅하는 데 사용되는 구성 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="c096f-109">메시징 활동</span><span class="sxs-lookup"><span data-stu-id="c096f-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="c096f-110">워크플로에서 메시지를 보내고 받을 수 있는 활동에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="c096f-111">방법: 메시징 작업으로는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c096f-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="c096f-112">메시징 활동을 사용하여 워크플로 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="c096f-113">방법: 워크플로 응용 프로그램에서 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="c096f-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="c096f-114">워크플로 응용 프로그램에서 서비스를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="c096f-115">상관 관계</span><span class="sxs-lookup"><span data-stu-id="c096f-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="c096f-116">상관 관계를 사용하여 메시지를 서로 매핑하거나 인스턴스에 매핑하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="c096f-117">순서가 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="c096f-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="c096f-118">순서가 맞지 않는 메시지를 허용하도록 서비스를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="c096f-119">방법: 다른 워크플로 서비스를 호출 하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c096f-119">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 <span data-ttu-id="c096f-120">다른 워크플로 서비스에서 워크플로 서비스를 동기적으로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-120">Describes how to synchronously call a workflow service from within another workflow service.</span></span>  
  
 [<span data-ttu-id="c096f-121">계약 중심 워크플로 서비스 개발</span><span class="sxs-lookup"><span data-stu-id="c096f-121">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="c096f-122">기존 서비스 계약을 기반으로 워크플로 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-122">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="c096f-123">방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c096f-123">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="c096f-124">기존 서비스 계약을 사용하여 워크플로 서비스를 만드는 방법을 보여 주는 단계별 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-124">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="c096f-125">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="c096f-125">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="c096f-126">워크플로 서비스 호스팅의 여러 측면에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-126">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="c096f-127">워크플로에서 계약 사용</span><span class="sxs-lookup"><span data-stu-id="c096f-127">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="c096f-128">여러 형식의 계약 및 계약 유추에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-128">Describes the different types of contracts and contract inference.</span></span>
