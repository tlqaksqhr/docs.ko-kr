---
title: "워크플로 서비스 호스팅 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0f473de9f16203d1b47ac227a1614b972b09e2f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="8d1db-102">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="8d1db-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="8d1db-103">워크플로 서비스를 실행하려면 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="8d1db-104"><xref:System.ServiceModel.WorkflowServiceHost>는 여러 인스턴스, 구성 및 WCF 메시징(워크플로가 호스팅되기 위해 메시징을 사용할 필요는 없지만)을 지원하는 즉시 사용 가능한 워크플로 호스트로,</span><span class="sxs-lookup"><span data-stu-id="8d1db-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="8d1db-105">서비스 동작의 집합을 통해 지속성, 추적 및 인스턴스 제어와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="8d1db-106">WCF의 <xref:System.ServiceModel.ServiceHost>와 마찬가지로 <xref:System.ServiceModel.WorkflowServiceHost>는 모든 관리되는 .NET 응용 프로그램에서 자체 호스팅되거나 IIS/WAS에서 .xamlx 파일로 웹 호스팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="8d1db-107">이 단원의 항목에서는 워크플로 서비스를 호스팅하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d1db-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="8d1db-108">In This Section</span></span>  
 [<span data-ttu-id="8d1db-109">워크플로 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="8d1db-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="8d1db-110">워크플로 서비스 호스팅에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="8d1db-111">워크플로 서비스 호스트 내부 기능</span><span class="sxs-lookup"><span data-stu-id="8d1db-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="8d1db-112"><xref:System.ServiceModel.WorkflowServiceHost>가 들어오는 메시지를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="8d1db-113">워크플로 서비스 호스트 확장</span><span class="sxs-lookup"><span data-stu-id="8d1db-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="8d1db-114">워크플로 서비스 호스트의 기능을 확장하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="8d1db-115">워크플로 제어 끝점</span><span class="sxs-lookup"><span data-stu-id="8d1db-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="8d1db-116">워크플로 인스턴스를 만들 수 있는 끝점을 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>  
  
 [<span data-ttu-id="8d1db-117">방법: IIS에서 서비스가 아닌 워크플로 호스팅</span><span class="sxs-lookup"><span data-stu-id="8d1db-117">How to: Host a non-service workflow in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 <span data-ttu-id="8d1db-118">IIS에서 워크플로 서비스가 아닌 워크플로를 호스팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-118">Demonstrates hosting a workflow that is not a workflow service in IIS.</span></span>  
  
 [<span data-ttu-id="8d1db-119">방법: Windows Server App Fabric로 워크플로 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="8d1db-119">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="8d1db-120">Windows Server AppFabric에서 기존 워크플로 서비스를 호스팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-120">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="8d1db-121">WorkflowServiceHost 구성</span><span class="sxs-lookup"><span data-stu-id="8d1db-121">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="8d1db-122">지속성, 추적, 유휴 상태 및 처리되지 않은 예외 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1db-122">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8d1db-123">참조</span><span class="sxs-lookup"><span data-stu-id="8d1db-123">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="8d1db-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8d1db-124">Related Sections</span></span>  
 [<span data-ttu-id="8d1db-125">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="8d1db-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
