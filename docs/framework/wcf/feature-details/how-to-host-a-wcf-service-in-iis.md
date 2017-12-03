---
title: "방법: IIS에서의 WCF 서비스 호스팅"
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
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 934b5d16cdea7026e0e7874cf04ab53c8fbdf58e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="d3ad3-102">방법: IIS에서의 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="d3ad3-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="d3ad3-103">이 항목에서는 IIS(인터넷 정보 서비스)에서 호스팅되는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 만드는 데 필요한 기본 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="d3ad3-104">이 항목에서는 사용자가 IIS에 대해 잘 알고 있으며 IIS 관리 도구를 사용해 IIS 응용 프로그램을 만들고 관리하는 방법을 이해하고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d3ad3-105">IIS 참조 [인터넷 정보 서비스](http://go.microsoft.com/fwlink/?LinkId=132449)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-105"> IIS see [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="d3ad3-106">IIS 환경에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 프로세스 재활용, 유휴 상태이면 종료, 프로세스 상태 모니터링 및 메시지 기반 활성화 같은 모든 IIS 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-106">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="d3ad3-107">이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 응용 프로그램의 일부로 작성하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="d3ad3-108">HTTP 전송을 사용하는 경우에만 IIS 호스팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d3ad3-109">어떻게 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 상호 작용을 참조 하십시오. [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-109"> how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d3ad3-110">보안을 구성을 참조 [보안](../../../../docs/framework/wcf/feature-details/security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-110"> configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="d3ad3-111">이 예의 원본 사본을 참조 [IIS 호스팅를 사용 하 여 인라인 코드](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="d3ad3-112">IIS에 의해 호스팅되는 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d3ad3-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="d3ad3-113">IIS가 컴퓨터에 설치되어 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-113">Confirm that IIS is installed and running on your computer.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d3ad3-114">IIS 설치 및 구성 참조 [IIS 7.0 구성 및 설치](http://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="d3ad3-114"> installing and configuring IIS see [Installing and Configuring IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="d3ad3-115">응용 프로그램 파일의 새 폴더("IISHostedCalcService")를 만들고, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]이 폴더 내용에 대한 액세스 권한을 가지고 있는지 확인하고, IIS 관리 도구를 사용하여 실제로 이 응용 프로그램 디렉터리에 있는 새 IIS 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="d3ad3-116">응용 프로그램 디렉터리의 별칭을 만들 때는 “IISHostedCalc”를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="d3ad3-117">응용 프로그램 디렉터리에 “service.svc”라는 새 파일을 만든 다음</span><span class="sxs-lookup"><span data-stu-id="d3ad3-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="d3ad3-118">다음을 추가 하 여이 파일을 편집 @ServiceHost 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="d3ad3-119">응용 프로그램 디렉터리 내에 App_Code 하위 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="d3ad3-120">App_Code subdirectory에 Service.cs라는 코드 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="d3ad3-121">Service.cs 파일의 맨 위에 다음의 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="d3ad3-122">using 문 뒤에 다음 네임스페이스 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="d3ad3-123">다음 코드와 같이 네임스페이스 선언 내에 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="d3ad3-124">다음 코드와 같이 서비스 계약 정의 뒤에서 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="d3ad3-125">응용 프로그램 디렉터리에 “Web.config”라는 파일을 만들고 다음 구성 코드를 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="d3ad3-126">런타임에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라에서는 이 정보를 사용하여 클라이언트 응용 프로그램이 통신할 수 있는 끝점을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-126">At runtime, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="d3ad3-127">다음 예제에서는 구성 파일의 끝점을 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="d3ad3-128">서비스에 끝점을 추가하지 않으면 런타임에서 기본 끝점을 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d3ad3-129">기본 끝점, 바인딩 및 동작 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-129"> default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="d3ad3-130">서비스가 올바르게 호스팅되는지 확인하려면 Internet Explorer 인스턴스를 열고 서비스 URL인 `http://localhost/IISHostedCalc/Service.svc`로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3ad3-131">예제</span><span class="sxs-lookup"><span data-stu-id="d3ad3-131">Example</span></span>  
 <span data-ttu-id="d3ad3-132">다음은 IIS에서 호스팅되는 계산기 서비스에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad3-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="d3ad3-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3ad3-133">See Also</span></span>  
 [<span data-ttu-id="d3ad3-134">인터넷 정보 서비스에서 호스팅</span><span class="sxs-lookup"><span data-stu-id="d3ad3-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="d3ad3-135">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="d3ad3-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="d3ad3-136">WCF 서비스 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d3ad3-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [<span data-ttu-id="d3ad3-137">보안</span><span class="sxs-lookup"><span data-stu-id="d3ad3-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 [<span data-ttu-id="d3ad3-138">Windows Server App Fabric 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="d3ad3-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
