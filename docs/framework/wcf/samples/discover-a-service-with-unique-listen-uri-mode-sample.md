---
title: Discover a Service with Unique Listen Uri Mode 샘플
ms.date: 03/30/2017
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
ms.openlocfilehash: e6129594df6170f94a06caa08a9f16e4770bbfd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501457"
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="a71be-102">Discover a Service with Unique Listen Uri Mode 샘플</span><span class="sxs-lookup"><span data-stu-id="a71be-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="a71be-103">이 샘플에서는 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성이 <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정된 서비스를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="a71be-104"><xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성이 <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정된 경우 포트를 고유하게 설정하거나 경로를 고유하게 하기 위해 GUID를 추가하는 방법으로 ListenUri를 고유하게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="a71be-105">서비스의 기능</span><span class="sxs-lookup"><span data-stu-id="a71be-105">Features on the Service</span></span>  
 <span data-ttu-id="a71be-106">TCP 끝점에 대해 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성을  <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="a71be-107">그런 다음 서비스를 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 끝점을 통해 검색할 수 있게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="a71be-108">클라이언트의 기능</span><span class="sxs-lookup"><span data-stu-id="a71be-108">Features on the Client</span></span>  
 <span data-ttu-id="a71be-109">이 클라이언트는 `Via.Uri` 메서드를 사용하여 올바른 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>를 사용하는 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="a71be-110">그런 다음 메서드에서 반환되는 <xref:System.ServiceModel.Discovery.FindResponse>를 쿼리하여 올바른 <xref:System.ServiceModel.Endpoint.ListenUri%2A>가 들어 있는지 여부와 이 URI가 `Address.Uri`와 다른지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="a71be-111">그 다음에는 적절한 정보가 `InvokeCalculatorService` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="a71be-112">`InvokeCalculatorService` 메서드에서 <xref:System.ServiceModel.Endpoint.ListenUri%2A>는 호출자가 전달한 것이며, 올바른 `ClientViaBehavior`가 있는 `Via.Uri`가 클라이언트의 끝점에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="a71be-113">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a71be-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="a71be-114">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 UniqueListenUriMode.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="a71be-115">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a71be-116">[solution base directory]\service\bin\debug에 생성된 서비스 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="a71be-117">[solution base directory]\Client\bin\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="a71be-118">클라이언트가 실행 중인 서비스를 찾고 서비스의 끝점에서 게시한 메타데이터를 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a71be-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a71be-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a71be-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a71be-121">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="a71be-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a71be-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a71be-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="a71be-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a71be-123">See Also</span></span>
