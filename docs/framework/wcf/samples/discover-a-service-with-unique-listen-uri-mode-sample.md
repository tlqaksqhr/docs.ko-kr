---
title: "Discover a Service with Unique Listen Uri Mode 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48b49def3f8f009eeb4ffa0204e9c616b5acfec7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="03e37-102">Discover a Service with Unique Listen Uri Mode 샘플</span><span class="sxs-lookup"><span data-stu-id="03e37-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="03e37-103">이 샘플에서는 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성이 <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정된 서비스를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="03e37-104"><xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성이 <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정된 경우 포트를 고유하게 설정하거나 경로를 고유하게 하기 위해 GUID를 추가하는 방법으로 ListenUri를 고유하게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="03e37-105">서비스의 기능</span><span class="sxs-lookup"><span data-stu-id="03e37-105">Features on the Service</span></span>  
 <span data-ttu-id="03e37-106">TCP 끝점에 대해 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성을  <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="03e37-107">그런 다음 서비스를 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 끝점을 통해 검색할 수 있게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="03e37-108">클라이언트의 기능</span><span class="sxs-lookup"><span data-stu-id="03e37-108">Features on the Client</span></span>  
 <span data-ttu-id="03e37-109">이 클라이언트는 `Via.Uri` 메서드를 사용하여 올바른 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>를 사용하는 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="03e37-110">그런 다음 메서드에서 반환되는 <xref:System.ServiceModel.Discovery.FindResponse>를 쿼리하여 올바른 <xref:System.ServiceModel.Endpoint.ListenUri%2A>가 들어 있는지 여부와 이 URI가 `Address.Uri`와 다른지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="03e37-111">그 다음에는 적절한 정보가 `InvokeCalculatorService` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="03e37-112">`InvokeCalculatorService` 메서드에서 <xref:System.ServiceModel.Endpoint.ListenUri%2A>는 호출자가 전달한 것이며, 올바른 `ClientViaBehavior`가 있는 `Via.Uri`가 클라이언트의 끝점에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="03e37-113">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="03e37-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="03e37-114">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 UniqueListenUriMode.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="03e37-115">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="03e37-116">[solution base directory]\service\bin\debug에 생성된 서비스 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="03e37-117">[solution base directory]\Client\bin\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="03e37-118">클라이언트가 실행 중인 서비스를 찾고 서비스의 끝점에서 게시한 메타데이터를 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="03e37-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="03e37-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="03e37-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="03e37-121">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="03e37-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03e37-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e37-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="03e37-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03e37-123">See Also</span></span>
