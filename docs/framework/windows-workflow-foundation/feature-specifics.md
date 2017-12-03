---
title: "Windows Workflow Foundation 기능 특성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 369c8738addeb083b42063161957cf9f97e2cd1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="windows-workflow-foundation-feature-specifics"></a><span data-ttu-id="d26e8-102">Windows Workflow Foundation 기능 특성</span><span class="sxs-lookup"><span data-stu-id="d26e8-102">Windows Workflow Foundation Feature Specifics</span></span>
[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]<span data-ttu-id="d26e8-103">에서는 Windows Workflow Foundation에 많은 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-103"> adds a number of features to Windows Workflow Foundation.</span></span> <span data-ttu-id="d26e8-104">이 문서에서는 여러 새로운 기능을 설명하고 이러한 기능이 유용할 수 있는 시나리오에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-104">This document describes a number of the new features, and gives details about scenarios in which they may be useful.</span></span>  
  
## <a name="messaging-activities"></a><span data-ttu-id="d26e8-105">메시징 활동</span><span class="sxs-lookup"><span data-stu-id="d26e8-105">Messaging Activities</span></span>  
 <span data-ttu-id="d26e8-106">메시징 활동 (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) 보내고 받는 데 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 워크플로와에서 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-106">The messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) are used to send and receive [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] messages from your workflow.</span></span>  <span data-ttu-id="d26e8-107"><xref:System.ServiceModel.Activities.Receive>및 <xref:System.ServiceModel.Activities.SendReply> 작업 양식에 사용 되는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 표준와 마찬가지로 WSDL을 통해 노출 되는 작업 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 웹 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-107"><xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities are used to form a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service operation that is exposed via WSDL just like standard [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] web services.</span></span>  <span data-ttu-id="d26e8-108"><xref:System.ServiceModel.Activities.Send>및 <xref:System.ServiceModel.Activities.ReceiveReply> WCF와 유사한 웹 서비스를 사용 하는 데 사용 됩니다 <xref:System.ServiceModel.ChannelFactory>; **서비스 참조 추가** 미리 구성 된 활동을 생성 하는 Workflow Foundation에 대 한 환경도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-108"><xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> are used to consume a web service similar to a WCF <xref:System.ServiceModel.ChannelFactory>; an **Add Service Reference** experience also exists for Workflow Foundation that generates pre-configured activities.</span></span>  
  
### <a name="getting-started-with-messaging-activities"></a><span data-ttu-id="d26e8-109">메시징 작업 시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-109">Getting Started with Messaging Activities</span></span>  
  
-   <span data-ttu-id="d26e8-110">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 WCF 워크플로 서비스 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-110">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="d26e8-111"><xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 쌍이 캔버스에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-111">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas.</span></span>  
  
-   <span data-ttu-id="d26e8-112">선택한 프로젝트를 마우스 오른쪽 단추로 클릭 **서비스 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-112">Right-click on the project and select **Add Service Reference**.</span></span>  <span data-ttu-id="d26e8-113">기존 WSDL 웹 서비스를 가리키고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-113">Point to an existing web service WSDL and click **OK**.</span></span>  <span data-ttu-id="d26e8-114">생성 된 활동이 표시 프로젝트를 빌드합니다 (사용 하 여 구현 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply>) 도구 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-114">Build your project to show the generated activities (implemented using <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply>) in your toolbox.</span></span>  
  
-   <span data-ttu-id="d26e8-115">이러한 작업에 대한 샘플은 다음 단원에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-115">Samples for these activities can be found in the following sections:</span></span>  
  
    -   <span data-ttu-id="d26e8-116">Basic: [서비스](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-116">Basic: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="d26e8-117">시나리오: [서비스](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-117">Scenarios: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
-   [<span data-ttu-id="d26e8-118">개념 설명서</span><span class="sxs-lookup"><span data-stu-id="d26e8-118">Conceptual documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204801)  
  
-   [<span data-ttu-id="d26e8-119">메시징 활동 디자이너 문서</span><span class="sxs-lookup"><span data-stu-id="d26e8-119">Messaging activities designer documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204802)  
  
### <a name="messaging-activities-example-scenario"></a><span data-ttu-id="d26e8-120">메시징 작업 예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-120">Messaging Activities Example Scenario</span></span>  
 <span data-ttu-id="d26e8-121">A `BestPriceFinder` 특정 경로 대 한 최상의 티켓 가격을 검색 하기 위해 여러 airline 서비스 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-121">A `BestPriceFinder` service calls out to multiple airline services to find the best ticket price for a particular route.</span></span>  <span data-ttu-id="d26e8-122">이 시나리오를 구현 가격 요청을 받고, 가격 백 엔드 서비스에서 검색 한 가격이 가격 요청에 회신 하 메시지 활동을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-122">Implementing this scenario would require you to use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>  <span data-ttu-id="d26e8-123">또한 해야 최상의 가격을 계산 하기 위한 비즈니스 논리를 만드는 다른 기본 제공 활동을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-123">It would also require you to use other out-of-box activities to create the business logic for calculating the best price.</span></span>  
  
## <a name="workflowservicehost"></a><span data-ttu-id="d26e8-124">WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="d26e8-124">WorkflowServiceHost</span></span>  
 <span data-ttu-id="d26e8-125"><xref:System.ServiceModel.WorkflowServiceHost> 는 여러 인스턴스를 지 원하는 기본 제공 워크플로 호스트 구성 및 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 메시징 (워크플로가 호스팅되기 위해 메시징을 사용할 요구 하지 않음) 하지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-125">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-box workflow host that supports multiple instances, configuration, and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="d26e8-126">서비스 동작의 집합을 통해 지속성, 추적 및 인스턴스 제어와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-126">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="d26e8-127">마찬가지로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 <xref:System.ServiceModel.ServiceHost>, <xref:System.ServiceModel.WorkflowServiceHost> 콘솔/WinForms/WPF 응용 프로그램 또는 Windows 서비스에서 자체 호스트 되거나 (.xamlx 파일로) 웹 호스트 될 수 IIS 또는 WAS에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-127">Just like [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in a console/WinForms/WPF application or Windows service, or web-hosted (as a .xamlx file) in IIS or WAS.</span></span>  
  
### <a name="getting-started-with-workflow-service-host"></a><span data-ttu-id="d26e8-128">워크플로 서비스 호스트 시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-128">Getting Started with Workflow Service Host</span></span>  
  
-   <span data-ttu-id="d26e8-129">Visual Studio 2010에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 워크플로 서비스 응용 프로그램 프로젝트를 만듭니다. 이 프로젝트는 웹 호스트 환경에서 <xref:System.ServiceModel.WorkflowServiceHost>를 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-129">In Visual Studio 2010, create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Workflow Service Application project: this project will be set up to use <xref:System.ServiceModel.WorkflowServiceHost> in a web-host environment.</span></span>  
  
-   <span data-ttu-id="d26e8-130">메시징이 아닌 워크플로를 호스트하려면 메시지를 기반으로 하는 인스턴스를 만들 사용자 지정 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-130">In order to host a non-messaging workflow, add a custom <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> that will create the instance based on a message.</span></span>  
  
-   <span data-ttu-id="d26e8-131"><xref:System.ServiceModel.Activities.WorkflowControlEndpoint>에 <xref:System.ServiceModel.WorkflowServiceHost>를 추가한 다음 <xref:System.ServiceModel.Activities.WorkflowControlClient>를 사용하여 워크플로 인스턴스를 제어(예: 일시 중단 또는 종료)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-131">Workflow instances can be controlled (e.g. suspended or terminated) by adding a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> to the <xref:System.ServiceModel.WorkflowServiceHost> and then using a <xref:System.ServiceModel.Activities.WorkflowControlClient>.</span></span>  
  
-   <span data-ttu-id="d26e8-132"><xref:System.ServiceModel.WorkflowServiceHost>에 대한 샘플은 다음 단원에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-132">Samples for the <xref:System.ServiceModel.WorkflowServiceHost> can be found in the following sections:</span></span>  
  
    -   [<span data-ttu-id="d26e8-133">실행</span><span class="sxs-lookup"><span data-stu-id="d26e8-133">Execution</span></span>](../../../docs/framework/windows-workflow-foundation/samples/execution.md)  
  
    -   <span data-ttu-id="d26e8-134">Basic: [서비스](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-134">Basic: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="d26e8-135">시나리오: [서비스](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-135">Scenarios: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="d26e8-136">응용 프로그램: [인스턴스 관리를 일시 중단](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-136">Application: [Suspended Instance Management](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)</span></span>  
  
-   [<span data-ttu-id="d26e8-137">WorkflowServiceHost 개념 문서</span><span class="sxs-lookup"><span data-stu-id="d26e8-137">WorkflowServiceHost Conceptual Documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204807)  
  
### <a name="workflowservicehost-scenario"></a><span data-ttu-id="d26e8-138">WorkflowServiceHost 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-138">WorkflowServiceHost Scenario</span></span>  
 <span data-ttu-id="d26e8-139">BestPriceFinder 서비스 특정 경로 대 한 최상의 티켓 가격을 검색 하려면 여러 airline 서비스 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-139">A BestPriceFinder service calls out to multiple airline services to find the best ticket price for a particular route.</span></span>  <span data-ttu-id="d26e8-140">이 시나리오를 구현 해야 합니다에서 워크플로 호스팅 <xref:System.ServiceModel.WorkflowServiceHost>합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-140">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  <span data-ttu-id="d26e8-141">메시지 활동 가격 요청을 수신 하 고 백 엔드 서비스에서 가격을 검색 한 다음이 가격이 가격 요청에 회신을 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-141">It would also use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>  
  
## <a name="correlation"></a><span data-ttu-id="d26e8-142">상관 관계</span><span class="sxs-lookup"><span data-stu-id="d26e8-142">Correlation</span></span>  
 <span data-ttu-id="d26e8-143">상관 관계는 다음 두 가지 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-143">A correlation is one of two things:</span></span>  
  
-   <span data-ttu-id="d26e8-144">메시지를 그룹화하는 방법(즉, 요청 메시지와 회신 간의 관계)</span><span class="sxs-lookup"><span data-stu-id="d26e8-144">A way of grouping messages together; that is, the relationship between a request message and its reply.</span></span>  
  
-   <span data-ttu-id="d26e8-145">데이터를 서비스 인스턴스에 매핑하는 방법</span><span class="sxs-lookup"><span data-stu-id="d26e8-145">A way of mapping a piece of data to a service instance</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-146">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-146">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-147">상관 관계를 시작하려면 Visual Studio에서 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-147">To get started with correlation, create a new project in Visual Studio.</span></span> <span data-ttu-id="d26e8-148"><xref:System.ServiceModel.Activities.CorrelationHandle> 형식의 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-148">Create a variable of type <xref:System.ServiceModel.Activities.CorrelationHandle>.</span></span>  
  
-   <span data-ttu-id="d26e8-149">메시지를 그룹화하는 데 사용되는 상관 관계의 예로 메시지를 그룹화하는 요청-회신 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-149">An example of correlation used to group messages together is a Request-Reply correlation that groups messages together.</span></span>  
  
    -   <span data-ttu-id="d26e8-150"><xref:System.ServiceModel.Activities.Receive> 작업에서 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 속성을 클릭하고 위의 첫 번째 단계에서 만든 CorrelationHandle을 사용하여 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-150">On a <xref:System.ServiceModel.Activities.Receive> activity, click on the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> property and add a a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> using the CorrelationHandle created in the first step above.</span></span>  
  
    -   <span data-ttu-id="d26e8-151">만들기는 <xref:System.ServiceModel.Activities.SendReply> 마우스 오른쪽 단추로 클릭 하 여 활동의 <xref:System.ServiceModel.Activities.Receive> "SendReply 만들기"를 클릭 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-151">Create a <xref:System.ServiceModel.Activities.SendReply> activity by right-clicking on the <xref:System.ServiceModel.Activities.Receive> and clicking "Create SendReply".</span></span> <span data-ttu-id="d26e8-152">워크플로에서 <xref:System.ServiceModel.Activities.Receive> 작업 뒤에 이 작업을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-152">Paste it into your workflow after the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>  
  
-   <span data-ttu-id="d26e8-153">데이터를 서비스 인스턴스에 매핑하는 예로 데이터(예: 주문 ID)를 특정 워크플로 인스턴스에 매핑하는 콘텐츠 기반 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-153">An example of mapping a piece of data to a service instance is content-based correlation which maps a piece of data (for example, an order ID) to a particular workflow instance.</span></span>  
  
    -   <span data-ttu-id="d26e8-154">아무 메시징 작업에서나 `CorrelationInitializers` 속성을 클릭하고 위에서 만든 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 변수를 사용하여 <xref:System.ServiceModel.Activities.CorrelationHandle>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-154">On any messaging activity, click on the `CorrelationInitializers` property and add a <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> using the <xref:System.ServiceModel.Activities.CorrelationHandle> variable created above.</span></span> <span data-ttu-id="d26e8-155">드롭다운 메뉴에서 원하는 메시지 속성(예: OrderID)을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-155">Double-click on the desired property on the message (e.g. OrderID) from the drop-down menu.</span></span> <span data-ttu-id="d26e8-156">`CorrelatesWith` 속성을 위에서 사용한 <xref:System.ServiceModel.Activities.CorrelationHandle> 변수로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-156">Set the `CorrelatesWith` property to the <xref:System.ServiceModel.Activities.CorrelationHandle> variable used above.</span></span>  
  
-   <span data-ttu-id="d26e8-157">샘플:</span><span class="sxs-lookup"><span data-stu-id="d26e8-157">Samples:</span></span>  
  
    -   <span data-ttu-id="d26e8-158">Basic: [서비스](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-158">Basic: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="d26e8-159">시나리오: [서비스](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-159">Scenarios: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   [<span data-ttu-id="d26e8-160">상관 관계 개념 문서</span><span class="sxs-lookup"><span data-stu-id="d26e8-160">Correlation Conceptual Documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204939)  
  
### <a name="correlation-scenario"></a><span data-ttu-id="d26e8-161">상관 관계 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-161">Correlation Scenario</span></span>  
 <span data-ttu-id="d26e8-162">주문 처리 워크플로의 새 주문 만들기 및 프로세스에 있는 기존 주문 업데이트를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-162">An order-processing workflow is used to handle new order creation and updating existing orders that are in process.</span></span>  <span data-ttu-id="d26e8-163">이 시나리오를 구현 해야 합니다에서 워크플로 호스팅 <xref:System.ServiceModel.WorkflowServiceHost> 메시징 활동을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-163">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost> and use the messaging activities.</span></span>  <span data-ttu-id="d26e8-164">또한 필요에 따라 상관 관계는 `orderId` 에 업데이트를 올바른 워크플로에 내용이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-164">It would also require correlation based on the `orderId` to ensure that updates are made to the correct workflow.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="d26e8-165">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="d26e8-165">Simplified Configuration</span></span>  
 <span data-ttu-id="d26e8-166">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 구성 스키마는 복잡하며 찾기 어려운 많은 기능을 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-166">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration schema is complex and provides users with many hard to find features.</span></span> <span data-ttu-id="d26e8-167">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 사용자가 다음 기능을 통해 서비스를 구성할 수 있도록 지원하는 데 중점을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-167">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], we have focused on helping [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] users configure their services with the following features:</span></span>  
  
-   <span data-ttu-id="d26e8-168">서비스별 명시적 구성의 필요성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-168">Removing the need for explicit per-service configuration.</span></span> <span data-ttu-id="d26e8-169">구성 하지 않으면 \<서비스 > 끝점 집합이 서비스 계약 및 서비스 기준 주소 하나에 자동으로 추가 됩니다 한 다음 모든 끝점에 프로그래밍 방식으로 서비스 및 서비스에 대 한 요소를 정의 하지 않습니다 서비스에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-169">If you do not configure any \<service> elements for your service, and your service does not define programmatically any endpoint, then a set of endpoints will be automatically added to your service, one per service base address and per contract implemented by your service.</span></span>  
  
-   <span data-ttu-id="d26e8-170">사용자가 명시적 구성 없이 서비스에 적용될 WCF 바인딩 및 동작의 기본값을 정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-170">Enables the user to define default values for WCF bindings and behaviors, which will be applied to services with no explicit configuration.</span></span>  
  
-   <span data-ttu-id="d26e8-171">표준 끝점은 하나 이상의 끝점 속성(주소, 바인딩 및 계약)에 대한 고정 값이 있는 미리 구성된 다시 사용 가능 끝점을 정의하며 사용자 지정 속성 정의를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-171">Standard endpoints define reusable preconfigured endpoints, which have fixed values for one or more of the endpoint properties (address, binding and contract), and allow defining custom properties.</span></span>  
  
-   <span data-ttu-id="d26e8-172">마지막으로, <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>를 사용하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 구성을 중앙에서 관리할 수 있으며, 응용 프로그램 도메인 로드 시간 후에 구성이 선택되거나 변경되는 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-172">Finally, the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows you to do central management of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client configuration, useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-173">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-173">Getting Started</span></span>  
  
-   [<span data-ttu-id="d26e8-174">Wcf 4.0 개발자 가이드</span><span class="sxs-lookup"><span data-stu-id="d26e8-174">A Developer's Guide to WCF 4.0</span></span>](http://go.microsoft.com/fwlink/?LinkId=204940)  
  
-   [<span data-ttu-id="d26e8-175">구성 채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="d26e8-175">Configuration Channel Factory</span></span>](http://go.microsoft.com/fwlink/?LinkId=204941)  
  
-   [<span data-ttu-id="d26e8-176">표준 끝점 요소</span><span class="sxs-lookup"><span data-stu-id="d26e8-176">Standard Endpoint Element</span></span>](http://go.microsoft.com/fwlink/?LinkId=204942)  
  
-   [<span data-ttu-id="d26e8-177">향상 된 서비스 구성에서.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="d26e8-177">Service configuration improvements in .Net Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkId=204943)  
  
-   [<span data-ttu-id="d26e8-178">.NET 4의에서 일반적인 사용자 실수: WF/WCF 서비스 구성 이름 입력 오류</span><span class="sxs-lookup"><span data-stu-id="d26e8-178">Common User Mistake in .NET 4: Mistyping the WF/WCF Service Configuration Name</span></span>](http://go.microsoft.com/fwlink/?LinkId=204944)  
  
### <a name="simplified-configuration-scenarios"></a><span data-ttu-id="d26e8-179">단순화된 구성 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-179">Simplified Configuration Scenarios</span></span>  
  
-   <span data-ttu-id="d26e8-180">숙련된 ASMX 개발자가 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 사용을 시작하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-180">An experienced ASMX developer wants to start using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="d26e8-181">하지만 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 너무 복잡한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-181">However, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] seems way too complicated!</span></span> <span data-ttu-id="d26e8-182">구성 파일을 작성하는 데 필요한 모든 정보는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d26e8-182">What is all that information that I need to write in a configuration file?</span></span> <span data-ttu-id="d26e8-183">.NET 4에서는 구성 파일을 전혀 사용하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-183">In .NET 4, you can even decide to not have a configuration file at all.</span></span>  
  
-   <span data-ttu-id="d26e8-184">기존의 WCF 서비스 집합은 구성 및 유지 관리가 매우 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-184">An existing set of WCF services are very difficult to configure and maintain.</span></span> <span data-ttu-id="d26e8-185">구성 파일에는 수천 줄의 XML 코드가 있으며 수정하는 것이 매우 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-185">The configuration file has thousands of lines of XML code that are extremely dangerous to touch.</span></span> <span data-ttu-id="d26e8-186">관리하기 쉽도록 코드 양을 줄이기 위한 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-186">Help is needed to reduce that amount of code to something more manageable.</span></span>  
  
## <a name="data-contract-resolver"></a><span data-ttu-id="d26e8-187">데이터 계약 확인자</span><span class="sxs-lookup"><span data-stu-id="d26e8-187">Data Contract Resolver</span></span>  
 <span data-ttu-id="d26e8-188">.NET 3.5의 알려진 형식 디자인에는 몇 가지 제한이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-188">In .NET 3.5, there were a few limitations in the design of known types:</span></span>  
  
-   <span data-ttu-id="d26e8-189">serialization 및 deserialization 중에 알려진 형식을 동적으로 추가할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-189">Adding known types dynamically, during serialization or deserialization, was not possible.</span></span>  
  
-   <span data-ttu-id="d26e8-190">직렬 변환기에서 알 수 없는 xsi:type 정보를 처리할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-190">Serializers could not deal with unknown xsi:type information.</span></span>  
  
-   <span data-ttu-id="d26e8-191">사용자가 회선의 serialization 인스턴스 크기를 더 작게 만들기 위해 회선에 표시할 xsi:type을 지정할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-191">It was not possible for users to specify what xsi:type they would like to have appear on the wire to, for instance, make the size of a serialization instance on the wire smaller.</span></span>  
  
 <span data-ttu-id="d26e8-192">[DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) .NET 4.5에서 이러한 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-192">The [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) solves these issues in .NET 4.5.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-193">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-193">Getting Started</span></span>  
  
-   [<span data-ttu-id="d26e8-194">데이터 계약 확인자 API 설명서</span><span class="sxs-lookup"><span data-stu-id="d26e8-194">Data Contract Resolver API documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204946)  
  
-   [<span data-ttu-id="d26e8-195">데이터 계약 확인자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-195">Introducing the Data Contract Resolver</span></span>](http://go.microsoft.com/fwlink/?LinkId=204947)  
  
-   <span data-ttu-id="d26e8-196">샘플:</span><span class="sxs-lookup"><span data-stu-id="d26e8-196">Samples:</span></span>  
  
    -   [<span data-ttu-id="d26e8-197">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="d26e8-197">DataContractResolver</span></span>](../../../docs/framework/wcf/samples/datacontractresolver.md)  
  
    -   [<span data-ttu-id="d26e8-198">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="d26e8-198">KnownAssemblyAttribute</span></span>](../../../docs/framework/wcf/samples/knownassemblyattribute.md)  
  
### <a name="data-contract-resolver-scenarios"></a><span data-ttu-id="d26e8-199">데이터 계약 확인자 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-199">Data Contract Resolver Scenarios</span></span>  
  
-   <span data-ttu-id="d26e8-200">서비스에서 수십 개의 <xref:System.Runtime.Serialization.KnownTypeAttribute> 개체를 선언할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-200">Avoiding having to declare tens of <xref:System.Runtime.Serialization.KnownTypeAttribute> objects in a service.</span></span>  
  
-   <span data-ttu-id="d26e8-201">XML blob의 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-201">Reducing the size of the XML blob.</span></span>  
  
## <a name="flowchart"></a><span data-ttu-id="d26e8-202">Flowchart</span><span class="sxs-lookup"><span data-stu-id="d26e8-202">Flowchart</span></span>  
 <span data-ttu-id="d26e8-203">순서도는 도메인 문제를 시각적으로 나타내는 잘 알려진 패러다임입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-203">Flowchart is a well-known paradigm to visually represent domain problems.</span></span> <span data-ttu-id="d26e8-204">.NET 4에서 도입된 새 제어 흐름 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-204">It is a new control flow style we’re introducing in .NET 4.</span></span> <span data-ttu-id="d26e8-205">순서도의 핵심 특성은 주어진 시간에 항상 작업 한 개만 실행된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-205">A core characteristic of Flowchart is that only one activity is executed at any given time.</span></span> <span data-ttu-id="d26e8-206">순서도는 루프 및 대체 결과를 표현할 수 있지만 여러 노드의 동시 실행은 기본적으로 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-206">Flowcharts can express loops and alternative outcomes, but cannot natively express concurrent execution of multiple nodes.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-207">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-207">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-208">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-208">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="d26e8-209">Workflow Designer에서 순서도를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-209">Add a Flowchart in the workflow designer.</span></span>  
  
-   <span data-ttu-id="d26e8-210">순서도 기능은 다음 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-210">The flowchart feature uses the following classes:</span></span>  
  
    -   <xref:System.Activities.Statements.Flowchart>  
  
    -   <xref:System.Activities.Statements.FlowNode>  
  
    -   <xref:System.Activities.Statements.FlowDecision>  
  
    -   <xref:System.Activities.Statements.FlowStep>  
  
    -   <xref:System.Activities.Statements.FlowSwitch%601>  
  
-   <span data-ttu-id="d26e8-211">샘플:</span><span class="sxs-lookup"><span data-stu-id="d26e8-211">Samples:</span></span>  
  
    -   [<span data-ttu-id="d26e8-212">오류 TryCatch를 사용 하 여 Flowchart 활동에서 처리</span><span class="sxs-lookup"><span data-stu-id="d26e8-212">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    -   [<span data-ttu-id="d26e8-213">FlowChart와 Pick을 함께 사용 하는 StateMachine 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-213">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>](../../../docs/framework/windows-workflow-foundation/samples/statemachine-scenario-using-a-combination-of-flowchart-and-pick.md)  
  
    -   [<span data-ttu-id="d26e8-214">채용 프로세스</span><span class="sxs-lookup"><span data-stu-id="d26e8-214">Hiring Process</span></span>](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
-   <span data-ttu-id="d26e8-215">디자이너 설명서:</span><span class="sxs-lookup"><span data-stu-id="d26e8-215">Designer Documentation:</span></span>  
  
    -   [<span data-ttu-id="d26e8-216">순서도 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="d26e8-216">Flowchart Activity Designers</span></span>](/visualstudio/workflow-designer/flowchart-activity-designers)  
  
### <a name="flowchart-scenarios"></a><span data-ttu-id="d26e8-217">순서도 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-217">Flowchart Scenarios</span></span>  
 <span data-ttu-id="d26e8-218">순서도 작업을 사용하여 추측 게임을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-218">A flowchart activity can be used to implement a guessing game.</span></span> <span data-ttu-id="d26e8-219">추측 게임은 매우 단순합니다. 컴퓨터가 임의 숫자를 선택하고 플레이어가 해당 숫자를 추측해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-219">The guessing game is very simple: the computer selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="d26e8-220">플레이어가 각 추측을 제출, 그 컴퓨터에는 힌트 (예: "시도 낮은 수치로") 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-220">When the player submits each guess, the computer shows him a hint (i.e. "try a lower number").</span></span> <span data-ttu-id="d26e8-221">플레이어가 7회 미만의 시도에서 숫자를 찾으면 컴퓨터에서 특별한 축하 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-221">If the player finds the number in less than 7 attempts, he receives a special congratulation from the computer.</span></span> <span data-ttu-id="d26e8-222">다음 절차 작업의 조합을 통해 이 게임을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-222">This game can be implemented with a combination of the following procedural activities:</span></span>  
  
-   <xref:System.Activities.Statements.Sequence>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.TryCatch>  
  
-   <xref:System.Activities.Statements.Assign%601>  
  
-   <xref:System.Activities.Statements.If>  
  
## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a><span data-ttu-id="d26e8-223">절차 작업(Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span><span class="sxs-lookup"><span data-stu-id="d26e8-223">Procedural activities (Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span></span>  
 <span data-ttu-id="d26e8-224">절차 작업은 프로그래머에게 익숙한 개념을 사용하여 순차 제어 흐름을 모델링하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-224">Procedural activities provide a mechanism to model sequential control flow using concepts that are familiar to programmers.</span></span> <span data-ttu-id="d26e8-225">이러한 작업은 일반적으로 구조적 프로그래밍 언어 구문을 활성화하며, 해당하는 경우 C#/VB와 같은 일반적인 절차 언어를 언어 패리티에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-225">These activities enable traditionally structured programming language constructs and, when appropriate, provide language parity with common procedural languages such as C#/VB.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-226">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-226">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-227">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-227">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="d26e8-228">Workflow Designer에서 절차 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-228">Add procedural activities in the workflow designer.</span></span>  
  
-   <span data-ttu-id="d26e8-229">샘플:</span><span class="sxs-lookup"><span data-stu-id="d26e8-229">Samples:</span></span>  
  
    -   [<span data-ttu-id="d26e8-230">채용 프로세스</span><span class="sxs-lookup"><span data-stu-id="d26e8-230">Hiring Process</span></span>](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
    -   [<span data-ttu-id="d26e8-231">기업 구매 프로세스</span><span class="sxs-lookup"><span data-stu-id="d26e8-231">Corporate Purchase Process</span></span>](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)  
  
-   <span data-ttu-id="d26e8-232">디자이너 설명서:</span><span class="sxs-lookup"><span data-stu-id="d26e8-232">Designer Documentation:</span></span>  
  
    -   [<span data-ttu-id="d26e8-233">Parallel 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="d26e8-233">Parallel Activity Designer</span></span>](/visualstudio/workflow-designer/parallel-activity-designer)  
  
    -   [<span data-ttu-id="d26e8-234">ParallelForEach\<T > 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="d26e8-234">ParallelForEach\<T> Activity Designer</span></span>](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)  
  
### <a name="procedural-activity-scenarios"></a><span data-ttu-id="d26e8-235">절차 작업 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-235">Procedural Activity Scenarios</span></span>  
  
-   <span data-ttu-id="d26e8-236"><xref:System.Activities.Statements.Parallel>: 인트라넷 문서 관리 시스템에 문서 승인 워크플로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-236"><xref:System.Activities.Statements.Parallel>: An intranet document management system has a document approval workflow.</span></span> <span data-ttu-id="d26e8-237">여러 부서의 사용자가 문서를 승인해야 인트라넷에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-237">Documents need to be approved by people in several departments before they can be published to the intranet.</span></span> <span data-ttu-id="d26e8-238">승인;에 대 한 설정 된 주문 하지 않으므로 문서가 "승인 보류 중" 단계에 있는 동안 언제 든 지 수행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-238">There isn’t an established order for the approvals; they can occur at any time while the document is in the "approval pending" phase.</span></span> <span data-ttu-id="d26e8-239">사용자가 검토를 위해 문서를 전송하면 직속 관리자, 인트라넷 관리자 및 내부 통신 관리자가 문서를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-239">When a user submits a document for review it must be approved by her direct manager, the intranet administrator, and the internal communications manager.</span></span>  
  
-   <span data-ttu-id="d26e8-240"><xref:System.Activities.Statements.ParallelForEach%601>: WF 응용 프로그램이 대기업 내의 회사 구매를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-240"><xref:System.Activities.Statements.ParallelForEach%601>: A WF application manages corporate buys within a large company.</span></span> <span data-ttu-id="d26e8-241">회사 규칙은 모든 구매 작업을 계획하기 전에 3개 공급업체를 평가하도록 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-241">The corporate rules dictate that before planning any purchase operation, the valuations of three different vendors is required.</span></span> <span data-ttu-id="d26e8-242">구매 부서의 직원이 회사 공급업체 목록에서 3개 공급업체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-242">An employee from the buying department selects three vendors from the company’s vendor list.</span></span> <span data-ttu-id="d26e8-243">공급업체를 선택하고 알린 후 회사는 합리적 제안서를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-243">After these vendors have been selected and notified, the company will wait for their economic proposals.</span></span> <span data-ttu-id="d26e8-244">제안서는 임의 순서로 도착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-244">The proposals can come in any order.</span></span> <span data-ttu-id="d26e8-245">WF에서 이 시나리오를 구현하기 위해 공급업체 컬렉션을 반복하고 합리적 제안서를 요청하는 <xref:System.Activities.Statements.ParallelForEach%601>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-245">To implement this scenario in WF, we use a <xref:System.Activities.Statements.ParallelForEach%601> that will iterate through our collection of vendors and ask for their economic proposals.</span></span> <span data-ttu-id="d26e8-246">모든 제안이 수집된 후 최상의 제안이 선택되고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-246">After all offers are gathered, the best one is selected and displayed.</span></span>  
  
## <a name="invokemethod"></a><span data-ttu-id="d26e8-247">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d26e8-247">InvokeMethod</span></span>  
 <span data-ttu-id="d26e8-248"><xref:System.Activities.Statements.InvokeMethod> 작업을 사용하면 범위 내의 개체나 형식에서 공용 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-248">The <xref:System.Activities.Statements.InvokeMethod> activity allows invoking public methods in objects or types in scope.</span></span> <span data-ttu-id="d26e8-249">이 작업은 매개 변수(매개 변수 배열 포함)를 사용하거나 사용하지 않는 인스턴스 및 정적 메서드 호출과 제네릭 메서드 호출을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-249">It supports invoking instance and static methods with or without parameters (including parameter arrays), and generic methods.</span></span> <span data-ttu-id="d26e8-250">동기 및 비동기로 메서드를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-250">It also allows executing method synchronously and asynchronously.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-251">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-251">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-252">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-252">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="d26e8-253">Workflow Designer에서 <xref:System.Activities.Statements.InvokeMethod> 작업을 추가하고 정적 및 인스턴스 메서드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-253">Add an <xref:System.Activities.Statements.InvokeMethod> activity in the workflow designer, and configure static and instance methods on it.</span></span>  
  
-   <span data-ttu-id="d26e8-254">샘플:</span><span class="sxs-lookup"><span data-stu-id="d26e8-254">Samples:</span></span>  
  
    -   [<span data-ttu-id="d26e8-255">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="d26e8-255">InvokeMethod</span></span>](../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
  
-   <span data-ttu-id="d26e8-256">디자이너 설명서: [InvokeMethod 활동 디자이너](/visualstudio/workflow-designer/invokemethod-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="d26e8-256">Designer Documentation: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)</span></span>  
  
### <a name="invokemethod-scenarios"></a><span data-ttu-id="d26e8-257">InvokeMethod 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-257">InvokeMethod Scenarios</span></span>  
  
-   <span data-ttu-id="d26e8-258">범위 내의 개체에서 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-258">A method in an object in scope needs to be invoked.</span></span> <span data-ttu-id="d26e8-259">예를 들어, 사전에 값을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-259">For example, a value needs to be added to a dictionary.</span></span> <span data-ttu-id="d26e8-260">사전 인스턴스의 Add 메서드가 호출되고 키와 값이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-260">The Add method of the instance of the dictionary is invoked, and the key and value are provided.</span></span>  
  
-   <span data-ttu-id="d26e8-261">레거시 CLR 개체에서 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-261">A method needs to be invoked on a legacy CLR object.</span></span> <span data-ttu-id="d26e8-262">레거시 클래스 호출을 래핑할 사용자 지정 작업을 만드는 대신 워크플로 실행 중에 범위 내에 있는 경우 <xref:System.Activities.Statements.InvokeMethod>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-262">Instead of creating a custom activity to wrap the call to that legacy class, if it is in scope during the workflow execution, <xref:System.Activities.Statements.InvokeMethod> can be used.</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="d26e8-263">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="d26e8-263">Error handling activities</span></span>  
 <span data-ttu-id="d26e8-264"><xref:System.Activities.Statements.TryCatch> 작업은 일련의 포함된 작업을 실행하는 동안 발생하는 예외를 catch하기 위한 메커니즘을 제공합니다(C#/VB의 Try/Catch 구문과 유사함).</span><span class="sxs-lookup"><span data-stu-id="d26e8-264">The <xref:System.Activities.Statements.TryCatch> activity provides a mechanism for catching exceptions that occur during the execution of a set of contained activities (similar to the Try/Catch construct in C#/VB).</span></span> <span data-ttu-id="d26e8-265"><xref:System.Activities.Statements.TryCatch>는 워크플로 수준에서 예외 처리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-265"><xref:System.Activities.Statements.TryCatch> provides exception handling at the workflow level.</span></span> <span data-ttu-id="d26e8-266">처리되지 않은 예외가 throw되면 워크플로가 중단되고 Finally 블록이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-266">When an unhandled exception is thrown, the workflow is aborted and the Finally block won’t be executed.</span></span> <span data-ttu-id="d26e8-267">이 동작은 C#과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-267">This behavior is consistent with C#.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-268">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-268">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-269">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-269">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="d26e8-270">Workflow Designer에서 <xref:System.Activities.Statements.TryCatch> 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-270">Add a <xref:System.Activities.Statements.TryCatch> activity in the workflow designer.</span></span>  
  
-   <span data-ttu-id="d26e8-271">샘플:</span><span class="sxs-lookup"><span data-stu-id="d26e8-271">Samples:</span></span>  
  
    1.  [<span data-ttu-id="d26e8-272">오류 TryCatch를 사용 하 여 Flowchart 활동에서 처리</span><span class="sxs-lookup"><span data-stu-id="d26e8-272">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    2.  [<span data-ttu-id="d26e8-273">절차 작업을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d26e8-273">Using Procedural Activities</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
  
-   <span data-ttu-id="d26e8-274">디자이너 설명서: [오류 처리 활동 디자이너](/visualstudio/workflow-designer/error-handling-activity-designers)</span><span class="sxs-lookup"><span data-stu-id="d26e8-274">Designer Documentation: [Error Handling Activity Designers](/visualstudio/workflow-designer/error-handling-activity-designers)</span></span>  
  
### <a name="error-handling-scenarios"></a><span data-ttu-id="d26e8-275">오류 처리 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-275">Error handling scenarios</span></span>  
 <span data-ttu-id="d26e8-276">일련의 작업을 실행해야 하며, 오류가 발생할 경우 특정 논리를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-276">A set of activities needs to be executed, and specific logic needs to be executed when an error occurs.</span></span> <span data-ttu-id="d26e8-277">오류 처리 논리 중에 오류를 복구할 수 없다는 것이 발견되면 예외가 다시 throw되고 부모 작업(또는 호스트)이 문제를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-277">If during that error handling logic it is found that the error is not recoverable, the exception will be rethrown, and the parent activity (or the host) will deal with the problem.</span></span>  
  
## <a name="pick-activity"></a><span data-ttu-id="d26e8-278">Pick 작업</span><span class="sxs-lookup"><span data-stu-id="d26e8-278">Pick activity</span></span>  
 <span data-ttu-id="d26e8-279"><xref:System.Activities.Statements.Pick> 작업은 WF에서 이벤트 기반 제어 흐름 모델링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-279">The <xref:System.Activities.Statements.Pick> Activity provides event-based control flow modeling in WF.</span></span> <span data-ttu-id="d26e8-280"><xref:System.Activities.Statements.Pick>에는 각 분기가 실행되기 전에 특정 이벤트의 발생을 기다리는 많은 분기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-280"><xref:System.Activities.Statements.Pick> contains many branches where each branch waits for a particular event to occur before running.</span></span> <span data-ttu-id="d26e8-281">이 설치에서 <xref:System.Activities.Statements.Pick>은 작업이 수신 대기 중인 이벤트 집합 중 하나만 실행하는 <xref:System.Activities.Statements.Switch%601>와 유사하게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-281">In this setup, a <xref:System.Activities.Statements.Pick> behaves similar to a <xref:System.Activities.Statements.Switch%601> to which the Activity will execute only one of the set of events it is listening.</span></span> <span data-ttu-id="d26e8-282">각 분기는 이벤트 구동 방식이며 처음 발생하는 이벤트는 해당 분기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-282">Each branch is event driven and the event that occurs runs the corresponding branch first.</span></span> <span data-ttu-id="d26e8-283">다른 분기는 모두 이벤트 수신 대기를 취소하고 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-283">All other branches cancel and stop listening for events.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-284">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-284">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-285">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-285">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="d26e8-286">Workflow Designer에서 <xref:System.Activities.Statements.Pick> 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-286">Add a <xref:System.Activities.Statements.Pick> activity in the workflow designer.</span></span>  
  
-   <span data-ttu-id="d26e8-287">샘플: [Pick 활동 사용](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-287">Sample: [Using the Pick Activity](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)</span></span>  
  
-   <span data-ttu-id="d26e8-288">디자이너 설명서: [Pick 활동 디자이너](/visualstudio/workflow-designer/pick-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="d26e8-288">Designer documentation: [Pick Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)</span></span>  
  
### <a name="pick-scenario"></a><span data-ttu-id="d26e8-289">Pick 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-289">Pick Scenario</span></span>  
 <span data-ttu-id="d26e8-290">사용자에게 입력을 요청하는 메시지를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-290">A user needs to be prompted for input.</span></span> <span data-ttu-id="d26e8-291">정상적인 상황에서는 개발자가 <xref:System.Console.ReadLine%2A>과 같은 메서드 호출을 사용하여 사용자 입력을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-291">Under normal circumstances, the developer would use a method call like <xref:System.Console.ReadLine%2A> to prompt for a user’s input.</span></span> <span data-ttu-id="d26e8-292">이 설치와 관련된 문제는 사용자가 입력할 때까지 프로그램이 기다린다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-292">The problem with this setup is that the program waits until the user enters something.</span></span> <span data-ttu-id="d26e8-293">이 시나리오에서는 차단 작업의 차단을 해제하기 위해 시간 제한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-293">In this scenario, a time-out is needed to unblock a blocking activity.</span></span> <span data-ttu-id="d26e8-294">일반적인 시나리오에서는 지정된 기간 내에 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-294">A common scenario is one that requires a task to be completed within a given time duration.</span></span> <span data-ttu-id="d26e8-295">차단 작업 시간 초과는 Pick에서 많은 값을 추가하는 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-295">Timing out a blocking activity is a scenario where Pick adds a lot of value.</span></span>  
  
## <a name="wcf-routing-service"></a><span data-ttu-id="d26e8-296">WCF 라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="d26e8-296">WCF Routing Service</span></span>  
 <span data-ttu-id="d26e8-297">라우팅 서비스는 일반 소프트웨어 방법을 제어할 수 있습니다 라우터 하도록 설계 되었습니다 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]클라이언트와 서비스 사이의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-297">The Routing Service is designed to be a generic software Router that allows you to control how [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]messages flow in between your clients and services.</span></span>  <span data-ttu-id="d26e8-298">라우팅 서비스에서 수 있습니다 클라이언트 서비스에서를 분리 하기 위한 구성 측면에서 훨씬 더 자유롭게를 제공 하 지원할 수 있고 있는지 유연성 서비스를 호스트 하는 방법을 고려 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d26e8-298">The Routing Service allows you to decouple your clients from your services, which gives you much more freedom in terms of the configurations that you can support and the flexibility you have when considering how to host your services.</span></span>  <span data-ttu-id="d26e8-299">.NET 3.5에서 클라이언트 및 서비스 된 밀접 하 게; 클라이언트의 모든 통신 하기 위해 필요 하 고 있던 위치 서비스에 대해 알고 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-299">In .NET 3.5, clients and services were tightly coupled; a client had to know about all of the services it needed to talk to and where they were located.</span></span> <span data-ttu-id="d26e8-300">또한 .NET Framework 3.5의 WCF에는 다음과 같은 제한이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-300">In addition, WCF in .Net Framework 3.5 had the following limitations:</span></span>  
  
-   <span data-ttu-id="d26e8-301">이 논리를 클라이언트 프로그램에 하드 코딩해야 했으므로 오류 처리가 복잡했습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-301">Error handling was complex, as this logic had to be hard-coded into the client.</span></span>  
  
-   <span data-ttu-id="d26e8-302">클라이언트와 서비스에서 항상 동일한 바인딩을 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-302">Clients and services had to always use the same bindings.</span></span>  
  
-   <span data-ttu-id="d26e8-303">서비스가 제대로 팩터링되지 않았습니다. 클라이언트가 여러 서비스 중에서 선택하는 대신 모든 기능을 구현하는 서비스 하나에 통신하도록 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-303">Services were rarely well factored: it is easier to have the client talk to one service which implements everything, rather than needing to choose between multiple services.</span></span>  
  
 <span data-ttu-id="d26e8-304">.Net 4의 라우팅 서비스는 이러한 문제를 쉽게 해결할 수 있도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-304">The routing service in .Net 4 is designed to make these problems easier to solve.</span></span> <span data-ttu-id="d26e8-305">새 라우팅 서비스에는 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-305">The new routing service has the following features:</span></span>  
  
1.  <span data-ttu-id="d26e8-306">콘텐츠 기반 라우팅(<xref:System.ServiceModel.Dispatcher.MessageFilter> 개체가 메시지를 검사하여 보낼 위치를 결정함)</span><span class="sxs-lookup"><span data-stu-id="d26e8-306">Content based routing (<xref:System.ServiceModel.Dispatcher.MessageFilter> objects examine a message to determine where it should be sent.)</span></span>  
  
2.  <span data-ttu-id="d26e8-307">프로토콜 브리징(전송 및 메시지)</span><span class="sxs-lookup"><span data-stu-id="d26e8-307">Protocol bridging (transport & message)</span></span>  
  
3.  <span data-ttu-id="d26e8-308">오류 처리(라우터가 통신 예외를 catch하고 백업 끝점으로 장애 조치됨)</span><span class="sxs-lookup"><span data-stu-id="d26e8-308">Error handling (the router catches communication exceptions and fails over to backup endpoints)</span></span>  
  
4.  <span data-ttu-id="d26e8-309"><xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> 및 라우팅 구성의 동적(메모리 내) 업데이트</span><span class="sxs-lookup"><span data-stu-id="d26e8-309">Dynamic (in memory) update of <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> and Routing Configuration.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-310">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-310">Getting Started</span></span>  
  
1.  <span data-ttu-id="d26e8-311">설명서: [라우팅](../../../docs/framework/wcf/feature-details/routing.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-311">Documentation: [Routing](../../../docs/framework/wcf/feature-details/routing.md)</span></span>  
  
2.  <span data-ttu-id="d26e8-312">샘플: [라우팅 서비스 &#91; WCF 샘플 &#93;](../../../docs/framework/wcf/samples/routing-services.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-312">Samples: [Routing Services &#91;WCF Samples&#93;](../../../docs/framework/wcf/samples/routing-services.md)</span></span>  
  
3.  <span data-ttu-id="d26e8-313">블로그: [라우팅 규칙!](http://go.microsoft.com/fwlink/?LinkId=204956)</span><span class="sxs-lookup"><span data-stu-id="d26e8-313">Blog: [Routing Rules!](http://go.microsoft.com/fwlink/?LinkId=204956)</span></span>  
  
### <a name="routing-scenarios"></a><span data-ttu-id="d26e8-314">라우팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-314">Routing Scenarios</span></span>  
 <span data-ttu-id="d26e8-315">라우팅 서비스는 다음과 같은 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-315">The routing service is useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="d26e8-316">클라이언트가 직접 주소를 모두 지정하지 않고 여러 서비스에 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-316">Clients can talk to multiple services without having to address them all directly.</span></span>  
  
-   <span data-ttu-id="d26e8-317">클라이언트가 클라이언트 요청에서 추가 논리를 수행하여 라우팅 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-317">Clients can perform additional logic on a client request to determine where to route it</span></span>  
  
-   <span data-ttu-id="d26e8-318">클라이언트를 리팩터링하지 않고 클라이언트가 수행하는 작업을 여러 서비스 구현으로 분해합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-318">Decompose the operations a client performs into multiple service implementations without refactoring the client.</span></span>  
  
-   <span data-ttu-id="d26e8-319">클라이언트와 서비스가 서로 다른 보안 설정으로 서로 다른 바인딩을 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-319">Clients and services can speak different bindings with different security settings.</span></span>  
  
-   <span data-ttu-id="d26e8-320">클라이언트가 서비스를 사용할 수 없는 경우나 오류에 대해 보다 강력하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-320">Clients can be enabled to be more robust against failure or the unavailability of services.</span></span>  
  
## <a name="wcf-discovery"></a><span data-ttu-id="d26e8-321">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="d26e8-321">WCF Discovery</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="d26e8-322"> Discovery는 검색 메커니즘을 응용 프로그램 인프라에 통합할 수 있는 프레임워크 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-322"> Discovery is a framework technology that allows you to incorporate a discovery mechanism to your application infrastructure.</span></span> <span data-ttu-id="d26e8-323">이 기술을 사용하여 서비스를 검색 가능하게 만들고 서비스를 검색하도록 클라이언트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-323">You can use this to make your service discoverable, and configure your clients to search for services.</span></span> <span data-ttu-id="d26e8-324">끝점을 사용하여 클라이언트를 더 이상 하드 코딩할 필요가 없으므로 응용 프로그램의 견고성과 내결함성이 강화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-324">Clients no longer need to be hard coded with endpoint, making your application more robust and fault tolerant.</span></span> <span data-ttu-id="d26e8-325">Discovery는 자동 구성 기능을 응용 프로그램에 빌드하는 완벽한 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-325">Discovery is the perfect platform to build auto-configuration capabilities into your application.</span></span>  
  
 <span data-ttu-id="d26e8-326">이 제품은 WS-Discovery 표준을 기반으로 하며</span><span class="sxs-lookup"><span data-stu-id="d26e8-326">The product is built on top of the WS-Discovery standard.</span></span> <span data-ttu-id="d26e8-327">상호 운용 및 확장 가능한 제네릭으로 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-327">It’s designed to be interoperable, extensible, and generic.</span></span> <span data-ttu-id="d26e8-328">이 제품에서는 다음 두 가지 작업 모드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-328">The product supports two modes of operation:</span></span>  
  
1.  <span data-ttu-id="d26e8-329">관리: 네트워크에 기존 서비스에 대해 알고 있는 엔터티가 있는 경우 클라이언트가 직접 정보를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-329">Managed: where there is an entity on the network knowledgeable about existing services, clients query it directly for information.</span></span> <span data-ttu-id="d26e8-330">이것은 Active Directory와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-330">This is analogous to Active Directory.</span></span>  
  
2.  <span data-ttu-id="d26e8-331">임시: 클라이언트가 멀티캐스트 메시지를 사용하여 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-331">Ad-hoc: where clients use multicast messages to locate services.</span></span>  
  
 <span data-ttu-id="d26e8-332">또한 검색 메시지는 네트워크 프로토콜에 관계없이 작동하므로 모드 요구 사항을 지원하는 모든 프로토콜에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-332">Furthermore, discovery messages are network protocol agnostic; you can use them on top any protocol that supports the mode requirements.</span></span> <span data-ttu-id="d26e8-333">예를 들어 검색 UDP 채널 또는 멀티 캐스트 메시징 지 원하는 다른 네트워크를 통해 멀티 캐스트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-333">For example, discovery multicast messages can be sent over the UDP channel or any other network that supports multicast messaging.</span></span>  <span data-ttu-id="d26e8-334">이러한 디자인 포인트를 검색 솔루션을 구체적으로 적용할 수 있도록 기능 유연성과 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-334">These design points, combined with feature flexibility, allow you to adapt the discovery specifically to your solution.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-335">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-335">Getting Started</span></span>  
  
-   <span data-ttu-id="d26e8-336">설명서: [WCF 검색](../../../docs/framework/wcf/feature-details/wcf-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-336">Documentation: [WCF Discovery](../../../docs/framework/wcf/feature-details/wcf-discovery.md)</span></span>  
  
-   <span data-ttu-id="d26e8-337">샘플: [검색 (샘플)](../../../docs/framework/wcf/samples/discovery-samples.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-337">Samples: [Discovery (Samples)](../../../docs/framework/wcf/samples/discovery-samples.md)</span></span>  
  
### <a name="discovery-scenarios"></a><span data-ttu-id="d26e8-338">Discovery 시나리오</span><span class="sxs-lookup"><span data-stu-id="d26e8-338">Discovery Scenarios</span></span>  
 <span data-ttu-id="d26e8-339">서비스를 사용할 수 있게 될 시기를 알 수 없기 때문에 개발자가 끝점을 하드 코딩하는 대신</span><span class="sxs-lookup"><span data-stu-id="d26e8-339">A developer doesn't want to hard code endpoints, since it is unknown when my service will be available.</span></span> <span data-ttu-id="d26e8-340">런타임에 서비스를 선택하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-340">Instead, the developer wants to choose a service at runtime.</span></span> <span data-ttu-id="d26e8-341">응용 프로그램 구성 요소 간에 분리, 견고성 및 자동 구성이 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-341">More decoupling, robustness, and auto-configuration is needed between the components in the application.</span></span>  
  
## <a name="tracking"></a><span data-ttu-id="d26e8-342">추적</span><span class="sxs-lookup"><span data-stu-id="d26e8-342">Tracking</span></span>  
 <span data-ttu-id="d26e8-343">워크플로 추적 된 워크플로 인스턴스 실행에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-343">Workflow tracking provides insight into the execution of a workflow instance.</span></span>  <span data-ttu-id="d26e8-344">추적 이벤트는 워크플로에서 워크플로 내의 작업을 실행할 때와 워크플로 인스턴스 수준에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-344">The tracking events are emitted from a workflow at the workflow instance level and when activities within the workflow execute.</span></span> <span data-ttu-id="d26e8-345">추적 레코드를 구독하려면 워크플로 추적 참가자를 워크플로 호스트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-345">A workflow tracking participant needs to be added to the workflow host to subscribe to tracking records.</span></span> <span data-ttu-id="d26e8-346">추적 레코드는 추적 프로필을 사용하여 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-346">The tracking records are filtered using a tracking profile.</span></span> <span data-ttu-id="d26e8-347">.NET Framework에서는 ETW(Windows용 이벤트 추적) 추적 참가자를 제공하며 machine.config 파일에 기본 프로필이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-347">The .Net Framework provides an ETW (Event Tracing for Windows) tracking participant, and a basic profile is installed in the machine.config file.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-348">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-348">Getting Started</span></span>  
  
1.  <span data-ttu-id="d26e8-349">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]에서 WCF 워크플로 서비스 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-349">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="d26e8-350">먼저 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 쌍이 캔버스에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-350">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas to start.</span></span>  
  
2.  <span data-ttu-id="d26e8-351">web.config를 열고 프로필 없이 ETW 추적 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-351">Open the web.config and add an ETW tracking behavior with no profile.</span></span>  
  
    1.  <span data-ttu-id="d26e8-352">기본 프로필이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-352">The default profile is used.</span></span>  
  
    2.  <span data-ttu-id="d26e8-353">이벤트 뷰어를 열고 다음 노드에서 분석 채널을 사용 하도록 설정: **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows** , **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-353">Open event viewer and enable the analytic channel in the following node: **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="d26e8-354">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-354">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
    3.  <span data-ttu-id="d26e8-355">워크플로 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-355">Run the workflow service.</span></span>  
  
    4.  <span data-ttu-id="d26e8-356">이벤트 뷰어에서 워크플로 추적 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-356">Observe the workflow tracking events in event viewer.</span></span>  
  
3.  <span data-ttu-id="d26e8-357">샘플: [추적](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-357">Samples: [Tracking](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)</span></span>  
  
4.  <span data-ttu-id="d26e8-358">개념 설명서: [워크플로 추적 및 트레이싱](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-358">Conceptual documentation: [Workflow Tracking and Tracing](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)</span></span>  
  
## <a name="sql-workflow-instance-store"></a><span data-ttu-id="d26e8-359">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="d26e8-359">SQL Workflow Instance Store</span></span>  
 <span data-ttu-id="d26e8-360"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>는 인스턴스 저장소의 SQL Server 기반 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-360">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is a SQL Server-based implementation of an instance store.</span></span> <span data-ttu-id="d26e8-361">인스턴스 저장소는 해당 인스턴스를 로드하고 다시 시작하는 데 필요한 모든 데이터와 함께 실행 중인 인스턴스의 상태를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-361">An instance store stores the state of a running instance together with all data necessary to load and resume that instance.</span></span> <span data-ttu-id="d26e8-362">서비스 호스트는 워크플로가 유지되는 경우 인스턴스 상태를 저장하도록 인스턴스 저장소에 지시하고, 해당 인스턴스에 대한 메시지가 도착하거나 지연 작업이 만료되면 인스턴스 상태를 로드하도록 인스턴스 저장소에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-362">The service host instructs the instance store to save the instance state if the workflow persists, and it instructs the instance store to load the instance state when a message arrives for that instance or a delay activity expires.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="d26e8-363">시작</span><span class="sxs-lookup"><span data-stu-id="d26e8-363">Getting Started</span></span>  
  
1.  <span data-ttu-id="d26e8-364">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 암시적 또는 명시적 <xref:System.Activities.Statements.Persist> 작업이 포함된 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-364">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a Workflow that contains an implicit or explicit <xref:System.Activities.Statements.Persist> activity.</span></span> <span data-ttu-id="d26e8-365">워크플로 서비스 호스트에 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-365">Add the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> behavior to your workflow service host.</span></span> <span data-ttu-id="d26e8-366">이 작업은 코드나 응용 프로그램 구성 파일에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-366">This can be done in code or in the application configuration file.</span></span>  
  
2.  <span data-ttu-id="d26e8-367">샘플: [지 속성](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)</span><span class="sxs-lookup"><span data-stu-id="d26e8-367">Samples: [Persistence](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)</span></span>  
  
3.  <span data-ttu-id="d26e8-368">개념 설명서: [SQL 워크플로 인스턴스 저장소](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d26e8-368">Conceptual documentation: [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>
