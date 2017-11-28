---
title: "방법: 관리되는 응용 프로그램에서 WCF 서비스 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: "42"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca834c097f7e8cea14337fece651b2b3059d06b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-application"></a><span data-ttu-id="88423-102">방법: 관리되는 응용 프로그램에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="88423-102">How to: Host a WCF Service in a Managed Application</span></span>
<span data-ttu-id="88423-103">관리되는 응용 프로그램 내에서 서비스를 호스팅하려면 관리되는 응용 프로그램 코드 내에 서비스에 대한 코드를 포함하고, 코드에서 명령적으로, 구성을 통해 선언적으로 또는 기본 끝점을 사용해 서비스에 대한 끝점을 정의한 다음 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88423-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="88423-104">메시지 받기를 시작하려면 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="88423-105">이렇게 하면 서비스에 대한 수신기가 만들어지고 열립니다.</span><span class="sxs-lookup"><span data-stu-id="88423-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="88423-106">관리되는 응용 프로그램이 호스팅 작업을 직접 수행하므로 이런 방식으로 서비스를 호스팅하는 것을 "자체 호스팅"이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="88423-107">서비스를 닫으려면 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ServiceHost>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="88423-108">서비스는 관리되는 Windows 서비스, IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 호스팅될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88423-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="88423-109">호스팅 서비스에 대 한 옵션, 참조 [호스팅 서비스](../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-109"> hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
 <span data-ttu-id="88423-110">관리되는 응용 프로그램에서 서비스를 호스팅할 경우 최소한의 배포 인프라를 필요로 하기 때문에 가장 유연한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="88423-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="88423-111">관리 되는 응용 프로그램에서 서비스를 호스팅, 참조 [관리 되는 응용 프로그램에서 호스팅](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-111"> hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="88423-112">다음 절차에서는 콘솔 응용 프로그램에서 자체 호스팅된 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88423-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>  
  
### <a name="to-create-a-self-hosted-service"></a><span data-ttu-id="88423-113">자체 호스팅된 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="88423-113">To create a self-hosted service</span></span>  
  
1.  <span data-ttu-id="88423-114">열기 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택 **새로**, **프로젝트...**  에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="88423-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New**, **Project...** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="88423-115">에 **설치 된 템플릿** 목록에서 **Visual C#**, **Windows** 또는 **Visual Basic**, **Windows**.</span><span class="sxs-lookup"><span data-stu-id="88423-115">In the **Installed Templates** list, select **Visual C#**, **Windows** or **Visual Basic**, **Windows**.</span></span> <span data-ttu-id="88423-116">에 따라 프로그램 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 설정, 하나 또는 둘 다 있을 수 있습니다는 **다른 언어** 에서 노드는 **설치 된 템플릿** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="88423-116">Depending on your [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] settings, one or both of these may be under the **Other Languages** node in the **Installed Templates** list.</span></span>  
  
3.  <span data-ttu-id="88423-117">선택 **콘솔 응용 프로그램** 에서 **Windows** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="88423-117">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="88423-118">형식 `SelfHost` 에 **이름** 상자 한 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-118">Type `SelfHost` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="88423-119">마우스 오른쪽 단추로 클릭 **SelfHost** 에 **솔루션 탐색기** 선택 **참조 추가...** . 선택 **System.ServiceModel** 에서 **.NET** 탭을 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference...**. Select **System.ServiceModel** from the **.NET** tab and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="88423-120">경우는 **솔루션 탐색기** 창이 표시, 선택 되지 않으면 **솔루션 탐색기** 에서 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="88423-120">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="88423-121">두 번 클릭 **Program.cs** 또는 **Module1.vb** 에 **솔루션 탐색기** 열려 있지 않으면 코드 창에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="88423-121">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window if it is not already open.</span></span> <span data-ttu-id="88423-122">파일 맨 위에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-122">Add the following statements at the top of the file.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  <span data-ttu-id="88423-123">서비스 계약을 정의 및 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-123">Define and implement a service contract.</span></span> <span data-ttu-id="88423-124">이 예제에서는 서비스에 대한 입력을 기준으로 메시지를 반환하는 `HelloWorldService`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-124">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="88423-125">정의 및 서비스 인터페이스를 구현 하 고, 참조 하는 방법 [하는 방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) 및 [하는 방법: 서비스 계약 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-125"> how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>  
  
7.  <span data-ttu-id="88423-126">서비스의 기본 주소를 사용하여 `Main` 메서드 맨 위에 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88423-126">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  <span data-ttu-id="88423-127"><xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들어 서비스 형식 및 기본 주소 URI(Uniform Resource Identifier)를 나타내는 <xref:System.Type>을 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-127">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="88423-128">메타데이터 게시를 사용하도록 설정한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출하여 서비스를 초기화하고 메시지를 받도록 서비스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-128">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]       
  
    > [!NOTE]
    >  <span data-ttu-id="88423-129">이 예제에서는 기본 끝점을 사용하며, 이 서비스에는 구성 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88423-129">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="88423-130">끝점을 구성하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 끝점을 하나씩 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88423-130">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="88423-131">기본 끝점, 참조 [단순화 된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-131"> default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="88423-132">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="to-test-the-service"></a><span data-ttu-id="88423-133">서비스를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="88423-133">To test the service</span></span>  
  
1.  <span data-ttu-id="88423-134">서비스를 실행하려면 Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="88423-134">Press Ctrl + F5 to run the service.</span></span>  
  
2.  <span data-ttu-id="88423-135">열기 **WCF 테스트 클라이언트**합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-135">Open **WCF Test Client**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="88423-136">열려는 **WCF 테스트 클라이언트**개방형는 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 명령 프롬프트를 실행 **WcfTestClient.exe**합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-136">To open **WCF Test Client**, open a [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] command prompt and execute **WcfTestClient.exe**.</span></span>  
  
3.  <span data-ttu-id="88423-137">선택 **서비스 추가...**  에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="88423-137">Select **Add Service...** from the **File** menu.</span></span>  
  
4.  <span data-ttu-id="88423-138">형식 `http://localhost:8080/hello` 클릭 고 주소 상자에 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-138">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="88423-139">서비스가 실행 중인지 확인하십시오. 그렇지 않으면 이 단계는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-139">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="88423-140">코드에서 기본 주소를 변경한 경우에는 이 단계에서 수정된 기본 주소를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="88423-140">If you have changed the base address in the code, then use the modified base address in this step.</span></span>  
  
5.  <span data-ttu-id="88423-141">두 번 클릭 **SayHello** 아래는 **내 서비스 프로젝트** 노드.</span><span class="sxs-lookup"><span data-stu-id="88423-141">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="88423-142">사용자 이름을 입력 된 **값** 열에는 **요청** 목록으로 이동한 클릭 **Invoke**합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-142">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span> <span data-ttu-id="88423-143">회신 메시지에 표시 된 **응답** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="88423-143">A reply message appears in the **Response** list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88423-144">예제</span><span class="sxs-lookup"><span data-stu-id="88423-144">Example</span></span>  
 <span data-ttu-id="88423-145">다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 개체를 만들어 `HelloWorldService` 형식의 서비스를 호스팅한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="88423-145">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="88423-146">기본 주소는 코드에서 제공되고 메타데이터 게시가 사용하도록 설정되며 기본 끝점이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="88423-146">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="88423-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88423-147">See Also</span></span>  
 <xref:System.Uri>  
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>  
 <xref:System.Configuration.ConfigurationManager>  
 [<span data-ttu-id="88423-148">방법: IIS에서 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="88423-148">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [<span data-ttu-id="88423-149">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="88423-149">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="88423-150">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="88423-150">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="88423-151">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="88423-151">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="88423-152">방법: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="88423-152">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="88423-153">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="88423-153">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="88423-154">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="88423-154">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="88423-155">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="88423-155">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
